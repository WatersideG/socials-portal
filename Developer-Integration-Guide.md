# Waterside Marketing Portal — Third-Party Integration Guide for Developers

**Version 1.0 · July 2026.** How to connect every data source behind the portal, manage credentials and quotas, and add a new brand or feed without breaking reporting. Companion documents: `Waterside-Marketing-Dashboard-Spec-v2.md` (metrics and formulas) and `research/additional-sources.md` (evaluated future integrations).

---

## 1. Architecture

```
Source APIs ──► ETL layer (Supermetrics or Funnel.io; direct API for GBP/Toast) ──► BigQuery (warehouse)
GA4  ────────► native BigQuery export (free ≤1M events/day) ─────────────────────┘
GSC  ────────► native bulk export to BigQuery (free) ─────────────────────────────┘
P&L  ────────► monthly CSV upload → validation → warehouse ───────────────────────┘
                                    BigQuery ──► portal front end (this prototype, productionized)
                                             └─► weekly AI insight job (precomputed metrics → LLM interprets → evidence stored)
```

Principles: the warehouse owns history (platforms retain 14–37 months; we keep everything); the portal reads only from the warehouse, never live APIs (quota isolation); every table carries `brand_id`, `source`, `sync_ts`, and a schema version; a broken pull raises a freshness alert — stale data must never render as current.

## 2. Source-by-source connection reference

| Source | Auth | Token lifetime | Key quotas / gotchas |
|---|---|---|---|
| **GA4 Data API** | Service account (add SA email as property Viewer) | Non-expiring key | Token-based quotas per property; prefer the BigQuery export for anything historical; ~10 concurrent requests/property |
| **GA4 BigQuery export** | Property setting, no code | — | Free daily export ≤1M events/day; streaming ~$0.05/GB; set up per property once |
| **Search Console API** | Service account (add as property user) | Non-expiring key | 25K rows/request; ~1,200 QPM/site; data lags ~2 days; use the new bulk export for scale; split branded vs non-branded via the Nov 2025 filter |
| **Meta Graph API (v25.0+)** | **Business system user token** via Business Manager | Non-expiring (system user) | Never ship personal user tokens (60-day expiry). Business Use Case rate limits; ~200 calls/hr per IG account; watch `X-App-Usage` headers; versions sunset ~every 2 years; impressions fields removed Nov 2025 — build on views/reach |
| **YouTube Analytics API** | OAuth2 consent from the channel owner (no SA option) | Refresh token | One-time owner consent per channel; Data API 10K units/day default (search = 100 units — avoid in loops) |
| **TikTok Business API** | OAuth2 + app review | Refresh cycle | New apps start sandboxed; plan 2–6 weeks for audited production access |
| **Google Ads API** | Developer token + OAuth2 | Refresh token | Basic access 15K operations/day; apply for Standard; token application process updated Feb 2026 |
| **HubSpot** | Private app token (single portal) | Static | 190 req/10s burst (Pro+); rotate on staff changes |
| **Google Business Profile APIs** | OAuth2 + approved GCP project (free application) | Refresh token | Split into 5 APIs; Performance API `fetchMultiDailyMetricsTimeSeries` for daily calls/directions/keyword impressions per location |
| **Toast partner API** | Partner program credentials (application-gated) | Per program | Checks carry a revenue-center dimension — map Toast revenue centers 1:1 to portal centers; webhooks available for near-real-time sales |
| **Yelp Fusion** | API key | Static | Paid-only: ~$7.99–14.99 per 1,000 calls; budget per-brand monthly pulls |
| **TripAdvisor Content API** | API key | Static | 5,000 calls/month free tier; own + competitor location review data |
| **Google/Apple/Bing local** | GBP above; Apple Business Connect and Bing Webmaster Tools are free dashboards/APIs | — | Apple Maps is the iPhone default; Bing feeds ChatGPT's local answers — claim all properties |
| **Weather (Open-Meteo / NWS)** | None (free, keyless) | — | Forecast pulls Mon–Tue drive the weekend content triggers |

## 3. Credential and secret management

One registry (Google Secret Manager or equivalent) holding every credential with: owner, scope, created/rotated date, expiry, refresh procedure, and the brand(s) it covers. Rules: no tokens in front-end code, sheets, or dashboards; one service account per environment (dev/prod), least-privilege grants; Meta system-user tokens and HubSpot private-app tokens rotate on staff departure; a quarterly credential audit is a calendar event, not an intention.

## 4. Scheduling and quota budgeting

Nightly batch per brand (overnight ET), staggered by source to stay under burst limits; exponential backoff on 429/5xx with jitter; per-source freshness SLA recorded in a `sync_log` table — the portal's Data Status panel reads from it. GA4/GSC history comes from the exports, not the APIs. Real-time surfaces (Toast sales today) use webhooks, not polling.

## 5. Monthly P&L import

- **Format:** CSV, UTF-8, one file per brand per month: `period (YYYY-MM), revenue_center, revenue, cogs, labor` (extra columns preserved but unmapped).
- **Validation on upload:** period must be a closed month; revenue_center matched against the brand's configured centers (fuzzy match ≥0.85 auto-maps; below that the line is queued for human mapping — never silently dropped or guessed); totals reconciled against the prior upload's trailing values with a ±40% sanity flag.
- **Effect:** actuals replace estimates in the Revenue Centers module; the Revenue Index recomputes; the demand-weight calibration job re-runs quarterly against actuals (the correct Demand Index weights are the ones that predict next-quarter revenue movement).
- **Audit:** every upload stored immutably with uploader, timestamp, and a diff against the previous version.

## 6. Data contracts

Each source lands in a versioned schema (`meta_posts_v2`, …). Breaking platform changes (the Nov 2025 Meta impressions removal is the canonical example) get a new schema version plus a mapping view, so historical queries keep working and time-series breaks are annotated in the portal rather than papered over.

## 7. Adding a new brand — checklist

1. Register brand in the registry (name, segment, locations, competitor set).
2. GA4 property + GTM container from the standard template (shared event taxonomy + UTM convention).
3. GSC property verified; both added to the service account.
4. Meta assets attached to Business Manager; system-user token scoped.
5. GBP location(s) linked; Apple Business Connect + Bing claimed.
6. Toast revenue-center mapping (dining) or P&L template issued (non-POS).
7. Revenue centers configured in Admin; competitor set confirmed with the on-site team.
8. First-sync verification: every Data Status row green before the brand appears in the owner's exception table.

## 8. Front-end integration notes

The prototype (`waterside-dashboard.html`) is a single self-contained file: brand registry, benchmark tables, and all render functions are plainly separated, and every sample-data generator (`brandDataRaw`, `campaigns`, `revData`, `mentionData`, `demoData`) has the exact shape the warehouse queries should return — replacing generators with fetch calls against warehouse views is the intended production path. Config edits (revenue centers) are in-memory in the prototype; production persists them with permissions and an audit trail. The portal ships mobile-first; keep any new component inside the existing grid classes and it inherits the responsive behavior.

## 9. Planned integrations (evaluated July 2026)

Ranked evaluation with pricing and access models in `research/additional-sources.md`. Highest-value next connections: Google Hotel free booking links (free), Apple Business Connect + Bing (free), Dockwa Insights (marina pacing), reservation-pacing exports (Resy/OpenTable/SevenRooms), PriceLabs market data ($9.99/mo/market), Census building permits (free), STR STAR report (hotel), AirDNA, TripAdvisor Content API, and the free demand-calendar layer (Visit NH, school vacations, pass-sales signals). The skip list (Placer.ai, card-spend products, PredictHQ, and others) is documented with reasons in the same file.
