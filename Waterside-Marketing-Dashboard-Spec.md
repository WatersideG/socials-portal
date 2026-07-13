# Waterside Group Marketing Performance Dashboard
## Build Specification & Research Brief

**Prepared:** July 12, 2026
**Scope:** All Waterside Group brands and affiliates
**Deliverables:** This specification + interactive dashboard prototype (`waterside-dashboard.html`)

---

## 1. Purpose

A single dashboard that answers two questions for every Waterside Group brand: *Is our marketing working?* and *What content should we make more of?* It serves two audiences from one interface: an executive scorecard for ownership (trends, ROI, wins, gaps) and a channel-level drill-down for the marketing team (diagnostics, benchmarks, content performance).

---

## 2. Company Scope

Confirmed from [watersidegroup.com](https://watersidegroup.com/) (July 2026). The company dropdown includes a **Portfolio Rollup** view plus each brand, grouped by segment because benchmarks differ by industry:

| Segment | Brands |
|---|---|
| Dining & Nightlife | Flying Bridge Restaurant, Timber Wood Fired (Lincoln + Falmouth), Timber Axe Bar & Bowl, Basecamp Brewing, Snowfish Sushi, Bluebird Martini Bar, Little Blue, South Peak Coffee Cart, Newport Creamery |
| Hospitality & Resort | South Peak Resort, Tides Hotel, Three Suns Captiva, Harbor Lights, The Mills Marketplace |
| Real Estate & Home | Longfellow Design Build, Lighthouse Station, Mountain Furniture Co. |
| Marine | Flying Bridge Marina, Flying Bridge Service Center |
| Retail | The Shop at South Peak |
| Affiliates (optional tier) | Vineyard Home, Whale's Tale Waterpark, Alpine Adventures |

**Design implication:** every metric is benchmarked against its segment (restaurant vs. hotel vs. real estate), never against a single portfolio-wide standard. A 0.40% Instagram engagement rate is at-median for a restaurant and above-median for a real estate brand.

---

## 3. Dashboard Structure

**Global controls:** Company dropdown (Portfolio Rollup + 20 brands + affiliates) · Date range with prior-period and prior-year comparison · Segment benchmark toggle.

**View 1 — Executive Scorecard** (default)
One screen, no scrolling required on desktop: composite health score, follower change, total engagements, website sessions and key events, email revenue/clicks, paid ROAS, AI/SEO visibility, and the month's top three AI-generated insights. Every KPI shows value, period-over-period delta, and a benchmark status color (above / at / below segment median).

**View 2 — Channel Drill-Down** (tabs: Facebook · Instagram · YouTube · TikTok · Email · Website · Blog · Search & AIO · Paid)
Full metric tables, trend charts, best-performing content list, and per-post diagnostics.

**View 3 — AI Insights & Content Ideas**
Generated insights (Section 8) with the data evidence behind each one, plus a ranked content idea queue.

---

## 4. Metrics Framework

### 4.1 Measurement principles (2025–26 standards)

These rules come out of the current benchmark literature and platform changes; they govern every metric below.

1. **Match the formula before comparing to any benchmark.** Engagement rate per-follower (Rival IQ/Quid method) and per-post-average (Hootsuite method) differ 6–14x on identical data ([Apaya cross-source comparison](https://apaya.com/blog/social-media-benchmarks)). This dashboard uses **per-follower ER for competitive benchmarking** and **per-view (reach-based) ER for content diagnostics** — both displayed, clearly labeled.
2. **Follower count is a vanity metric; follower *change* is a health signal.** The 2025 Sprout Social Index reports marketing leaders now weight engagement roughly 3x over follower counts ([Sprout Social](https://sproutsocial.com/insights/social-media-metrics/)). We show +/- followers as a trend indicator, not a headline KPI.
3. **Weight interactions by value.** Platforms weight saves and shares far above likes. Dashboard uses a weighted engagement score: shares/sends ×4, saves ×3, comments ×2, likes ×0.5 ([InfluenceFlow 2025](https://influenceflow.io/resources/engagement-rate-and-reach-metrics-the-complete-2025-guide-for-creators-and-brands/)) — consistent with Instagram's confirmed top ranking signals (watch time, likes per reach, **sends per reach**; [Buffer](https://buffer.com/resources/instagram-algorithms/)).
4. **Email opens are unreliable.** Apple Mail Privacy Protection auto-fires open pixels; opens are inflated 15–35% ([beehiiv](https://www.beehiiv.com/blog/apple-mpp-open-rate)). Primary email KPIs are **click rate, click-to-open, conversion, and revenue per email**; opens are shown as directional only.
5. **Meta broke the time series in 2025.** "Views" replaced impressions (April 2025) and the impressions/page-fans API fields were deprecated November 15, 2025 ([Meta for Developers](https://developers.facebook.com/blog/post/2025/08/15/page-insights-api-updates/)). All Meta metrics are built on views/reach; YoY comparisons across April 2025 carry a footnote.
6. **Watch time is the universal video currency.** TikTok, Reels, YouTube, and Facebook (all video now classified as Reels) rank on watch time and completion. Hook rate (3-sec plays ÷ impressions) and hold rate (15-sec ÷ 3-sec plays) are the two diagnostic ratios ([Benly](https://benly.ai/learn/ad-creative/hold-rate-explained)).

### 4.2 Channel metrics, formulas, and current benchmarks

Benchmarks below are the most recent published medians; segment column indicates which Waterside segment they apply to. All are directional guardrails — the primary comparison is each brand's own trailing 12-month performance.

**Facebook (organic)**

| Metric | Formula | Benchmark |
|---|---|---|
| +/- Followers | net follower change | trend only |
| Posts | published count/period | median 3/week ([Quid/Rival IQ 2026](https://www.quid.com/knowledge-hub/resource-library/blog/2026-social-media-industry-benchmark-report)) |
| Engagement rate (benchmark) | interactions ÷ followers | Travel 0.06% · Food & Bev 0.03% (Rival IQ 2025) |
| Engagement rate (content) | interactions ÷ reach | Dining/hospitality avg ~1.3% ([Hootsuite 2025](https://blog.hootsuite.com/average-engagement-rate/)) |
| Video watch time | total minutes; hold rate 15s÷3s | narrative structure lifts hold ~42% |
| Link CTR | link clicks ÷ views | track vs. own trailing avg |

**Instagram (feed + Reels + Stories)**

| Metric | Formula | Benchmark |
|---|---|---|
| Engagement rate (benchmark) | interactions ÷ followers | All-industry median 0.30%; Travel 0.34%; Food & Bev 0.40% (Rival IQ) |
| Sends per reach | shares ÷ reach | top Mosseri-confirmed growth signal |
| Reels watch time | avg. watch time; 3-sec hook rate | first 3 seconds heavily weighted |
| Stories completion | completions ÷ starts | ~70% avg ([Dash Social](https://www.dashsocial.com/blog/every-instagram-stories-performance-benchmark-you-need-to-know)) |
| Stories exit by frame | exits ÷ views per frame | 23.8% exit on frame 1; reach peaks frames 6–13 ([Socialinsider](https://www.socialinsider.io/social-media-benchmarks/instagram-stories-benchmarks)) |
| # Stories | frames/period | reach builds mid-sequence — 6+ frames outperform 1–3 |
| Format mix | carousel vs Reel vs static ER | carousels earn up to +109% more engagement than Reels ([Buffer 52M-post study](https://apaya.com/blog/social-media-benchmarks)) |

**YouTube**

| Metric | Formula | Benchmark |
|---|---|---|
| Engagement rate | interactions ÷ subscribers | median 0.21% (Quid 2026) |
| Thumbnail CTR | impressions clicks ÷ impressions | 3–4% avg; 4–6% good; 6%+ excellent ([Humble & Brag 2026](https://humbleandbrag.com/blog/youtube-ctr-benchmarks)) |
| Avg. % viewed | watch time ÷ (views × length) | 65–75% for <5-min videos; overall avg retention ~23.7%; 55% of viewers gone by 0:60 ([Retention Rabbit 2025](https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report)) |
| Watch time (hrs) | total | +10 pts retention ≈ +25% algorithmic impressions |

**TikTok**

| Metric | Formula | Benchmark |
|---|---|---|
| Engagement rate (benchmark) | interactions ÷ followers | median 2.01% all-industry; Travel 2.73%; Food & Bev 2.04% (Rival IQ/Quid) |
| Engagement rate (by views) | interactions ÷ views | 4.20% avg 2025 ([Socialinsider](https://www.socialinsider.io/social-media-benchmarks/tiktok)) |
| Completion rate | full watches ÷ views | 60%+ good; 80%+ precedes viral distribution ([Shortimize](https://www.shortimize.com/blog/what-is-a-good-view-rate-for-tiktok)) |
| Watch time | avg. per video | heaviest ranking signal with completion |

**Email**

| Metric | Formula | Benchmark |
|---|---|---|
| Click rate | unique clicks ÷ delivered | all-industry 2.09%; restaurants 1.06% (lowest tracked); real estate ~2.5% ([MailerLite 2025](https://www.mailerlite.com/blog/compare-your-email-performance-metrics-industry-benchmarks), [Luxury Presence](https://www.luxurypresence.com/blogs/email-marketing-performance-metrics-real-estate/)) |
| Click-to-open | clicks ÷ opens | 6.81% all-industry; restaurants 3.28% |
| Open rate (directional) | opens ÷ delivered | travel 30.1% — MPP-inflated, do not segment on it |
| Conversion / revenue per email | orders or bookings ÷ delivered; revenue ÷ delivered | RPE ≥ $0.12 beats Klaviyo 2025 median |
| List growth & unsubscribe | net adds; unsubs ÷ delivered | unsub ≤ 0.22% |

**Website (GA4)**

| Metric | Formula | Benchmark |
|---|---|---|
| Engagement rate | engaged sessions ÷ sessions (Google definition: >10s, or a key event, or 2+ pageviews) | GA4-native ([Google](https://support.google.com/analytics/answer/12195621?hl=en)) |
| Session key event rate | sessions with key event ÷ sessions | avg site converts ~2.35%; real estate & travel ~2.8% visitor-to-lead ([Ruler Analytics 2026](https://www.ruleranalytics.com/blog/insight/conversion-rate-by-industry/)) |
| Booking conversion (hotel brands) | bookings ÷ sessions | travel booking avg ~0.2%; top decile 3.4%; mobile converts 5x worse than desktop ([Obvlo](https://obvlo.com/resources/travel-website-conversion-benchmarks/)) |
| Website performance score | composite: Core Web Vitals (Lighthouse/CrUX), engagement rate, key event rate — weighted 40/30/30 | displayed 0–100 |
| Traffic mix | sessions by default channel group | paid search converts best at 5.4% (Ruler) |

**Blog**

| Metric | Formula | Notes |
|---|---|---|
| Organic entrances | GA4 landing-page sessions, organic | primary blog KPI |
| Engaged time & scroll depth | GA4 avg engagement time; 90% scroll event via GTM | replaces pageviews |
| Assisted key events | key events with blog page in path | connects content to leads |
| AI citation count | blog URLs cited in AI answers | via AIO tool (Section 7) |

**Search & AIO (GSC + AI visibility tool)**

| Metric | Formula | Benchmark / note |
|---|---|---|
| Clicks, impressions, CTR, avg position | GSC Performance API | Position-1 CTR fell 28% → 19% in 2025 ([GrowthSRC](https://growthsrc.com/google-organic-ctr-study/)) |
| Click/impression decoupling | impressions trend vs clicks trend | AI Overviews appear on ~31–48% of SERPs; AIO queries show up to 83% zero-click |
| AI share of voice | brand citations ÷ category citations | the core normalized AIO KPI ([Search Engine Land](https://searchengineland.com/geo-metrics-to-track-476642)) |
| AI mention & citation rate | % of tracked prompts where brand appears, per engine | engines barely overlap (~11% ChatGPT–Perplexity domain overlap) — track per engine |
| AIO presence bonus | cited vs not cited in AI Overview | being cited: +35% organic, +91% paid clicks ([Seer Interactive 2025](https://www.seerinteractive.com/insights/aio-impact-on-google-ctr-september-2025-update)) |

**Paid campaigns (Google Ads + Meta Ads)**

| Metric | 2025 benchmark (US) |
|---|---|
| Google Search CTR / CPC / conv. rate | Travel 8.73% / $2.12 / 5.75% · Restaurants 7.58% / $2.05 / 7.09% · Real estate 8.43% / $2.53 / 3.28% ([WordStream 2025](https://www.wordstream.com/blog/2025-google-ads-benchmarks)) |
| Meta traffic CTR / CPC | Travel 2.76% / $0.51 · Real estate 1.68% / $0.91 ([LocaliQ 2025](https://localiq.com/blog/facebook-advertising-benchmarks/)) |
| Meta lead gen (real estate) | CTR 3.75%, CPL $16.61, conv. 9.53% |
| ROAS / cost per booking-lead | primary exec KPI; real estate CPC rose 27% YoY in the 2026 report — watch efficiency |

### 4.3 Best-performing content

"Best" is scored per channel with a composite, not raw likes: weighted engagement score (Section 4.1.3) × 0.4 + watch-time percentile × 0.3 + outbound clicks/key events attributed × 0.3. The dashboard lists the top five pieces per brand per period with the score decomposition, so the team can see *why* something won (hook, format, topic, or distribution).

---

## 5. Data Sources & Integration Roles

| Source | Role | What it feeds |
|---|---|---|
| Google Analytics 4 | Behavior + conversion ground truth | website tab, conversion rates, channel attribution, blog metrics |
| Google Search Console | Organic search ground truth | Search & AIO tab (clicks, impressions, CTR, position, decoupling) |
| Meta Business Manager | FB + IG organic and paid | Facebook, Instagram, Stories, Meta Ads |
| HubSpot | CRM, email, attribution | email tab, lead lifecycle, revenue attribution (run first-touch AND last-touch models; review monthly with sales) |
| Google Tag Manager | **Collection layer, not a data source.** GTM deploys GA4 tags, key events, scroll/engagement events, and ad pixels. Its role in this project: standardized event taxonomy across all 20+ sites so metrics are comparable | data quality for everything above |
| Google Ads | Paid search | paid tab |
| YouTube Analytics | Channel video | YouTube tab |
| TikTok Business API | Organic + paid TikTok | TikTok tab |

### Recommended additional integrations (priority order)

1. **Google Business Profile Performance API** — the highest-value missing source for a portfolio dominated by restaurants and local venues. Calls, direction requests, profile views, and search keywords; profiles with photos get 30–50% more views ([Google](https://developers.google.com/my-business), [WebFX](https://www.webfx.com/blog/seo/google-business-profile-benchmarks/)). Free; requires an access application.
2. **Reservation/POS data (OpenTable partner API, Toast partner API)** — ties marketing to covers and revenue for dining brands. Both partner-gated; the native Toast↔OpenTable integration links reservations to spend ([Toast](https://pos.toasttab.com/integrations/opentable)).
3. **Review platforms** — Yelp Fusion (now paid, ~$7.99–14.99 per 1,000 calls) and TripAdvisor (partner-gated; verify current terms) for rating and review-velocity KPIs.
4. **Email platform APIs** (Mailchimp/Klaviyo if used outside HubSpot) — RPE and flow performance.
5. **CallRail** — call tracking; phone calls are a primary conversion for restaurants, marinas, and real estate ([CallRail](https://www.callrail.com/integrations)).
6. **Social listening** (Brand24 ~$79/mo per flagship brand) — sentiment and share of conversation; partially overlaps Ahrefs Brand Radar's social modules.

---

## 6. API Integration Management Framework

### 6.1 Recommended architecture: warehouse-centric

```
Platform APIs ──> ETL connector (Supermetrics or Funnel.io) ──> BigQuery ──> Looker Studio / dashboard
GA4 ────────────> native BigQuery export (free ≤1M events/day) ──┘
GSC ────────────> native bulk export to BigQuery (free) ─────────┘
```

Rationale: direct API calls from a dashboard hit quota walls at 20+ brands (GA4 Data API token quotas, Instagram ~200 calls/hr per account, YouTube 10K units/day). Landing everything in BigQuery decouples collection from visualization, escapes per-view API quotas, preserves history beyond platform retention windows, and survives the next Meta-style metric deprecation because raw data is owned.

**Faster low-code alternative:** AgencyAnalytics (~$20/brand/mo, 85+ native connectors including CallRail and Klaviyo) gets a credible multi-brand dashboard live in days. Reasonable Phase-1 choice; the warehouse becomes Phase 2. See Section 7.2 comparison.

### 6.2 Authentication and token management

| API | Auth model | Token lifetime | Management rule |
|---|---|---|---|
| GA4 Data API / GSC | Service account | non-expiring key | one SA per environment; grant property-level viewer |
| Meta Graph API (v25.0) | **Business system user token** | non-expiring | never use personal user tokens (60-day expiry) in production; monitor `X-App-Usage` headers |
| YouTube Analytics | OAuth2 from channel owner | refresh token | no service-account option; one-time owner consent per channel |
| TikTok Business | OAuth2 + app review | refresh cycle | apps start sandboxed; plan 2–6 weeks for audited access |
| HubSpot | Private app token | static | rotate on staff changes; respect 190 req/10s burst |
| Google Ads | Developer token + OAuth2 | refresh token | Basic access = 15K ops/day; apply for Standard |

### 6.3 Operating rules

1. **Version watch.** Meta sunsets Graph API versions ~every 2 years; subscribe to platform changelogs; quarterly review of deprecation notices (the Nov 2025 impressions deprecation is the cautionary case).
2. **Quota budgeting.** Schedule pulls overnight, batch by brand, exponential backoff on 429s. GA4: prefer the BigQuery export over the Data API for anything historical.
3. **Credential registry.** One encrypted registry (e.g., Google Secret Manager) listing every token, owner, scope, expiry, and refresh procedure. No tokens in dashboards or sheets.
4. **Schema contracts.** Each source lands in BigQuery with a versioned schema; a broken pull alerts (data freshness check per source per brand) rather than silently showing stale numbers.
5. **UTM and event governance.** A single UTM convention and GTM event taxonomy across all brands — attribution in HubSpot and GA4 is only as good as tagging hygiene.
6. **Access tiers.** Executives get view-only; marketing team gets explore; one admin owns connections.

---

## 7. Tool Recommendations

### 7.1 SEO / AIO stack

| Tier | Tool | Cost (verify — 2026 pricing) | Why |
|---|---|---|---|
| Core (now) | Google Search Console | Free | ground truth for search |
| Core (now) | Semrush Pro + **AI Visibility Toolkit** | $139.95 + $99/mo per domain | best value single-vendor path: rank tracking, audits, plus AI answer visibility (25 prompts/domain) |
| Alternative | Ahrefs + Brand Radar | ~$828–1,148/mo all-in | strongest AI Overview historical tracking; expensive for 20 brands |
| Budget AIO | Otterly.AI | $29–189/mo | monitor 2–3 flagship brands only (South Peak, Longfellow, Harbor Lights) |
| Enterprise (later) | Profound or seoClarity ArcAI | ~$2K–5K+/mo (demo-led) | if AI visibility becomes a board-level KPI; seoClarity serves Marriott/Expedia — hospitality pedigree |

Practical AIO cadence regardless of tool: track 20–30 buying-intent prompts per flagship brand ("best ski-in ski-out community New Hampshire", "Cape Cod waterfront restaurant Falmouth"), log cited/mentioned/absent monthly per engine.

### 7.2 Data visualization

| Option | Cost at ~20 brands | Strengths | Trade-offs |
|---|---|---|---|
| **Looker Studio + Supermetrics/BigQuery** (recommended end-state) | $0 + ~$199–499/mo connectors | owns the data layer, free viz, unlimited viewers, portfolio rollups via BigQuery | build effort; GA4 connector quota issues unless warehoused |
| **AgencyAnalytics** (recommended Phase 1) | ~$400/mo | 85+ native connectors, white-label, client-style per-brand views, fastest time-to-live | data lives in their platform; less custom scoring |
| Whatagraph | €199–699+/mo | cross-channel blending | pricing restructured May 2026; expensive at scale |
| Power BI / Tableau | $14–75/user/mo | deepest analytics | marketing connectors weak natively; needs the warehouse anyway |
| Databox / DashThis / Swydo | $44–159/mo | cheap, quick | thinner connector depth for this mix |

Recommendation: **Phase 1 on AgencyAnalytics** for immediate visibility, while **Phase 2 builds the BigQuery + Looker Studio (or the custom HTML app prototyped here)** as the permanent, owned asset. Supermetrics and Funnel.io are the two credible ETL vendors; choose Funnel.io if no data engineer is available, Supermetrics for lower cost.

---

## 8. AI-Enhanced Insights Layer

The insights engine combines three inputs — **own trailing performance** (warehouse), **live industry trends** (Google Trends API, TikTok Creative Center trending sounds/hashtags, seasonal search demand), and **benchmark deltas** (Section 4) — and produces three output types on a weekly cycle:

1. **Performance insights** — anomaly and driver detection. Example: "Snowfish Sushi Reels with staff on camera earned 3.1x the weighted engagement of menu-only posts over 90 days; sends-per-reach doubled."
2. **Content ideas** — generated from top-performing themes × rising trend signals × seasonal calendar. Example: "Search demand for 'Loon Mountain summer' rises 4x June–August; South Peak's top format is drone property video; recommend a 3-part 'Summer at South Peak' Reels series with carousel follow-ups (carousels currently out-engage Reels portfolio-wide)."
3. **Prescriptive alerts** — benchmark breaches and opportunities. Example: "Harbor Lights GSC impressions +42% but clicks flat — title/snippet rewrite opportunity on 8 event-venue pages; AI Overviews now answer 5 of its top 12 queries, and Harbor Lights is cited in none."

Implementation: a scheduled job (weekly) sends each brand's metric deltas, top/bottom content with attributes (format, topic, hook length, posting time), trend feeds, and benchmark table to an LLM (Claude API) with a fixed analysis prompt; outputs are stored with the evidence rows that produced them so every insight is auditable. Insights the team marks "useful" are retained as few-shot examples — the system improves with feedback.

---

## 9. Phased Rollout

| Phase | Timeline | Scope |
|---|---|---|
| 1 — Foundation | Weeks 1–4 | GTM event taxonomy + UTM standard across all sites; GA4 key events audited per brand; GA4→BigQuery export on; AgencyAnalytics live for 5 flagship brands (South Peak, Longfellow, Flying Bridge, Harbor Lights, Newport Creamery) |
| 2 — Full portfolio | Weeks 5–10 | remaining brands connected; Meta system-user tokens; YouTube/TikTok authorized; GBP API application; Semrush AI Visibility on flagships |
| 3 — Owned dashboard | Weeks 8–16 | BigQuery warehouse complete; custom dashboard (this prototype productionized) replaces or augments AgencyAnalytics; composite scores live |
| 4 — AI insights | Weeks 12–20 | weekly insight job; content idea queue; reservation/POS and CallRail integrations |

**Estimated Phase 1–2 tooling budget:** roughly $750–1,100/month (AgencyAnalytics ~$400, Semrush + AI toolkit ~$240, Supermetrics ~$200, Brand24 ~$79, misc. API costs), before the optional enterprise AIO tier.

---

## 10. Caveats

Benchmarks are directional: every publisher sells analytics software, methodologies differ, and 2025 broke several time series (Meta views change, API deprecations, AI Overviews, MPP-inflated opens). The primary standard for every brand is its own trailing performance; segment benchmarks are guardrails. Verify vendor pricing before purchase — Whatagraph, AgencyAnalytics, and Profound all restructured pricing within the last 12 months. Yelp's API is now paid-only; TripAdvisor and TikTok/OpenTable/Toast API access are application-gated with unpredictable timelines.

---

## Appendix A — Key sources

Benchmarks: [Quid/Rival IQ 2026 Social Media Industry Benchmark Report](https://www.quid.com/knowledge-hub/resource-library/blog/2026-social-media-industry-benchmark-report) · [Rival IQ 2025 report](https://www.rivaliq.com/blog/social-media-industry-benchmark-report/) · [Hootsuite engagement benchmarks](https://blog.hootsuite.com/average-engagement-rate/) · [Socialinsider TikTok](https://www.socialinsider.io/social-media-benchmarks/tiktok) and [Stories studies](https://www.socialinsider.io/social-media-benchmarks/instagram-stories-benchmarks) · [MailerLite email benchmarks 2025](https://www.mailerlite.com/blog/compare-your-email-performance-metrics-industry-benchmarks) · [WordStream Google Ads 2025](https://www.wordstream.com/blog/2025-google-ads-benchmarks) · [LocaliQ Facebook Ads](https://localiq.com/blog/facebook-advertising-benchmarks/) · [Ruler Analytics conversion benchmarks](https://www.ruleranalytics.com/blog/insight/conversion-rate-by-industry/) · [Retention Rabbit YouTube 2025](https://www.retentionrabbit.com/blog/2025-youtube-audience-retention-benchmark-report) · [GrowthSRC organic CTR study](https://growthsrc.com/google-organic-ctr-study/) · [Seer Interactive AIO impact](https://www.seerinteractive.com/insights/aio-impact-on-google-ctr-september-2025-update) · [Ahrefs AIO study](https://ahrefs.com/blog/ai-overviews-reduce-clicks-update/)

Platforms & APIs: [Google Analytics engagement definitions](https://support.google.com/analytics/answer/12195621?hl=en) · [GA4 BigQuery export](https://support.google.com/analytics/answer/9358801?hl=en) · [Meta Page Insights API deprecations](https://developers.facebook.com/blog/post/2025/08/15/page-insights-api-updates/) · [Meta rate limiting](https://developers.facebook.com/docs/graph-api/overview/rate-limiting/) · [GSC API limits](https://developers.google.com/webmaster-tools/limits) · [Google Business Profile APIs](https://developers.google.com/my-business)

Tools: [Semrush AI pricing](https://www.semrush.com/pricing/ai/) · [Ahrefs Brand Radar](https://ahrefs.com/brand-radar) · [AgencyAnalytics integrations](https://agencyanalytics.com/integrations) · [Supermetrics pricing](https://supermetrics.com/pricing) · [Search Engine Land GEO metrics](https://searchengineland.com/geo-metrics-to-track-476642)
