# Waterside Group Marketing Performance Dashboard
## Build Specification v2

**Prepared:** July 12, 2026 · Supersedes v1 (July 12, 2026)
**Research base:** 550+ sources consulted across four research tracks (competitor landscape 166, SEO/content publications 141, AI recommendations 152, campaign reporting & dashboard design 94). Full briefs with every source URL are in the `research/` folder; v1 covered metrics, benchmarks, integrations, and tooling and remains valid where not amended here.

**What's new in v2:** named competitor sets for every brand (up to 5 each) with a tracking method; period comparison (prior period AND prior year); a full paid campaign table with budget, pacing, and end dates; an expanded AI recommendation engine built on free data sources and trigger playbooks; a news-driven advice feed; and 20 evidence-based design rules that keep the whole thing scannable for non-technical readers.

---

## 1. Design philosophy: tell the story, then show the data

The dashboard follows the inverted pyramid, drawn from Nielsen Norman Group usability research, Stephen Few, and Storytelling with Data: verdict first, evidence second, detail behind a click. Concretely:

- **Every brand view opens with a 3–4 sentence TL;DR:** how the period went, what's working, the one concern, the next move.
- **Owner view shows 3–5 numbers; staff views show at most 9 per screen.** One number, one message per card — value, delta with its baseline named in words ("vs. last July"), a sparkline, and a status color.
- **Plain-English labels pass the "CFO test."** "People who clicked" leads; "CTR" is the small print. Bars and lines only — no pies, gauges, or 3D.
- **Every red number ships with its explanation attached.** Annotations follow "what changed + why + what we're doing," dated and stored in a persistent log. News-driven callouts ("Google's December core update rolled out Dec 10–29 — this dip is industry-wide") are the highest-trust annotation type.
- **If a chart has no action attached to it, it gets cut.**

---

## 2. Period comparison (new)

A global comparison selector applies to every metric: **vs. prior period** or **vs. same period last year**.

- **Year-over-year is the headline comparison for this portfolio.** Nearly every Waterside brand is seasonal (ski, beach, foliage, wedding season) — comparing a ski-town brewery's March against its February rewards the calendar, not the marketing. YoY is the honest ruler; prior-period is secondary and always labeled.
- **YoY aligns by weekday and week, not calendar date.** For restaurants, Saturday vs. Saturday matters more than July 12 vs. July 12 (Looker Studio's calendar-date default gets this wrong).
- **The comparison layer auto-annotates calendar traps:** moving holidays (Easter shifted from March to April between 2027 and 2028), leap days, school-vacation weeks, and event shifts — so a "down 18% YoY" week that lost a holiday explains itself.
- Every delta on every card states its baseline in words: "+12% vs. July 2025," never a bare arrow.

---

## 3. Competitor tracking (new)

### 3.1 What we can see without their logins

All competitor metrics come from public data — no access to competitor accounts is needed:

| Metric | Source | Cost |
|---|---|---|
| Followers, posting frequency, engagement on public posts | Instagram native **Competitive Insights** (up to 10 accounts, launched Nov 2025, free) · Metricool (free tier tracks 5 competitors) · Socialinsider (~$99/mo) or Rival IQ (~$239/mo) for depth | Free–$99/mo |
| Whether they're advertising, ad count, ad longevity, creative themes, offers | **Meta Ad Library** — every active FB/IG ad is public; long-running ads are likely working. No spend/performance data | Free |
| Who bids against us in Google, and how hard | **Google Ads Auction Insights** — impression share, overlap rate, outranking share, from our own account | Free |
| Share of search (brand demand vs. theirs) | **Google Trends** — brand vs. competitor brand queries; share of search correlates with, and often leads, market share. Directional; read the multi-month trend | Free |
| Review rating, count, velocity (reviews/30 days), recency | Google Maps public profiles, logged monthly; Local Falcon / Whitespark / Semrush Local to automate | Free–low |
| Estimated site traffic, keyword overlap | Semrush/Ahrefs domain comparison; Similarweb (overstates small local sites 2–3x — use only for large competitors) | Included in SEO stack |

**Cadence:** monthly for social + reviews + Ad Library, quarterly for search/traffic deep-dives. **Dashboard treatment:** one competitor strip per brand — our number, their median, the gap, and a one-line takeaway ("Woodstock Inn posts 5x/week vs. our 2x and gains followers 3x faster — frequency, not quality, is the gap").

### 3.2 Named competitor sets (researched, up to 5 per brand)

Verified operating businesses in the same market and category (full detail with URLs in `research/competitors.md`):

| Waterside brand | Competitors to track |
|---|---|
| Flying Bridge Restaurant | Pier 37 Boathouse · The Quarterdeck · Landfall (Woods Hole) · Falmouth Raw Bar · Paul's Pizza & Seafood |
| Timber Wood Fired (Lincoln NH) | Alpine Pizza · GH Pizza · Enzo's Pizzeria · Tartaglia's Pizza · Pub 32 |
| Timber Wood Fired (Falmouth MA) | Chapoquoit Grill · Osteria La Civetta · Simply Divine Pizza · Eli's Tavern |
| Timber Axe Bar & Bowl | The Lanes Bowl & Bistro (Mashpee) · Ryan Family Amusements (S. Yarmouth) · Ten Pin Eatery (Hyannis) · Ryan's Buzzards Bay · The Alley Bowling & BBQ (Orleans) |
| Basecamp Brewing | Woodstock Inn Brewery · Twin Barns (N. Woodstock) · Rek'-lis (Bethlehem) · Schilling (Littleton) · Moat Mountain (N. Conway) |
| Snowfish Sushi | Grey Whale Sushi & Grill (the one in-town rival — benchmark closely) · Taste The Thai & Sushi House · Enso Japanese Steak House |
| Bluebird Martini Bar | The Grateful Skier · Gordi's Fish & Steak · Seven Birches Winery · Loon Mountain bars (Babe's Blue Ox / Black Diamond) · DeaconStreet Martini & Whiskey Bar (N. Conway) |
| Newport Creamery | Gregg's · Chelo's · Friendly's · Frosty Freeze · Sundaes |
| South Peak Resort | RiverWalk Resort at Loon · Owl's Nest Resort · Bretton Woods townhomes · Sunday River Merrill Hill · Spruce Peak at Stowe |
| Tides Hotel | Inn on the Sound · Shore Haven Inn (Lark) · Green Harbor Waterfront Lodging · CapeWind Waterfront Resort |
| Three Suns Captiva | Sea Oats Luxury Estate · Royal Shell Vacations · SanCap Island Vacation Rentals · Kingfisher Vacations · 'Tween Waters Island Resort |
| Harbor Lights | Warwick Country Club · Quidnessett Country Club · Chelo's Waterfront (Warwick) · Safe Harbor Greenwich Bay · Safe Harbor Cowesett |
| The Mills Marketplace | Settlers Green (N. Conway) · North Conway Village shops · Tanger Outlets Tilton · Downtown Littleton · Lincoln Main St retail |
| Longfellow Design Build | Cataldo Custom Builders · McPhee Associates · Cape Associates · S+H Construction (Best of Boston rival) · Feinmann Inc. |
| Lighthouse Station | Southport on Cape Cod · Everleigh Cape Cod · The Boatyard Condos · Dillingham Place · Cottages at LeBaron Hills |
| Mountain Furniture Co. | Green Mountain Furniture (Ossipee) · Allen Wayside (Conway) · The Naked Bohemian (N. Conway) · Yankee Furniture Barn · Jerry's Furniture (Intervale) |
| Flying Bridge Marina | MacDougalls' · East Marine / Oyster Harbors · Falmouth Marine & Yachting · Cataumet Boats · Green Pond / The Haven |
| Flying Bridge Service Center | Fairhaven Shipyard · Earl's Marina · South Coast Mobile Marine · Preservati Marine · Fairhaven Marine Service |
| Little Blue · South Peak Coffee Cart · The Shop at South Peak | Competitor sets to be confirmed with the team (small hyper-local categories; candidates exist but weren't verified in this pass) |

Data caution: "Loon Rustics" shares Mountain Furniture Co.'s address and appears to be its predecessor identity, not a competitor — verify before tracking.

---

## 4. Paid campaigns table (new)

Each brand's Paid view shows one row per campaign. Results always speak the objective's language — "42 leads," "310 covers," "18 bookings" — never generic "conversions."

**Columns:** Campaign · Platform · Objective · Status (Active/Paused/Ended/Learning + Meta's "Creative Fatigue" flag passed through) · Start–End date · Budget + type (daily vs. lifetime) · Spend to date (with freshness timestamp) · **Pacing %** · Results (objective-matched) · Cost per result · ROAS (purchase campaigns only) · CTR · Frequency (Meta).

**Pacing** = % of budget spent ÷ % of flight elapsed. Green within ±5%, amber 5–15% off, red beyond 15% — and alerts fire on *under*-pacing too (unspent budget is missed demand). Campaigns ending within 7 days get an "ending soon" flag with projected final spend. Platform mechanics respected: Google Ads can spend up to 2x a daily budget in a day but never exceeds 30.4x per month (pace monthly); Meta averages daily budgets over the week (up to +75% on a strong day); lifetime budgets pace against the flight.

**Creative fatigue:** Meta frequency amber at ≥2.5, red at ≥3.5 for cold audiences (4/6 for retargeting) — Meta's own research shows conversion likelihood drops ~45% by a fourth exposure. The flag always pairs with a CTR/CPM trend check before recommending a refresh, phrased in plain English: "This audience has seen this ad ~3.6 times and clicks are fading — time for fresh creative."

**Attribution honesty:** Meta (7-day click / 1-day view) and GA4 (data-driven, click-based) measure with different rulers; 10–20% variance is structural, not an error. The dashboard never sums conversions across platforms — each row is platform-labeled, and one "business truth" row (bookings/leads from GA4 + POS/CRM) anchors the view, with the ruler footnoted.

**Naming convention** (prerequisite for cross-brand rollups): `platform_brand_objective_audience_geo_flight`, lowercase, one delimiter, controlled vocabulary — e.g., `meta_southpeak_leads_bostonmetro_2026q3`.

---

## 5. AI recommendation engine v2 (expanded)

### 5.1 Architecture: precompute, then interpret

The industry-converged pattern: **metrics are computed in the warehouse (SQL), the LLM only interprets and drafts** — it never does arithmetic. Every insight card stores the evidence rows that produced it; anomalies are joined against context tables (weather, events, campaigns, Google update calendar) *before* the model writes an explanation, because a spike might be an anomaly — or a snowstorm. Humans approve; the engine detects and drafts. Insights the team marks useful are kept as examples, so recommendations improve.

Anomaly detection uses seasonality-aware baselines (STL/Prophet — free, handles daily/weekly/yearly seasonality plus holidays), otherwise every season change in a tourism portfolio triggers false alarms. GA4's built-in anomaly detection covers site metrics; Prophet baselines cover what GA4 can't see (GBP actions, social reach, review velocity).

### 5.2 Free data feeds (beyond the paid accounts)

| Feed | What it gives the engine |
|---|---|
| Google Trends (+ 2025 API alpha) | seasonal demand curves, share of search vs. competitors |
| Google Business Profile Performance API | calls, direction requests, discovery keywords per location — the highest-value free feed for local brands |
| Meta Ad Library | competitor ad activity and creative themes (UI-level; the API excludes US commercial ads) |
| TikTok Creative Center | trending sounds, hashtags, top ads by region |
| Pinterest Trends | the best free seasonal-planning signal — start publishing when a seasonal term hits ~25–30% of its peak |
| YouTube Studio Inspiration tab | AI content suggestions per channel |
| Open-Meteo / NWS weather APIs (free, keyless) | snow and beach-weather triggers |
| Ticketmaster Discovery API + local calendars | event-adjacent content opportunities |
| Reddit (+ F5Bot alerts, free) | what travelers actually ask; AI engines cite Reddit heavily for dining/lodging |
| Google Keyword Planner, AlsoAsked/AnswerThePublic free tiers, People Also Ask | question mining for content |
| Zillow Research / Redfin Data Center (free downloads) | market context for the real estate brands |

### 5.3 Native AI already included in current accounts — switch on, cost $0

- **GA4:** anomaly detection + custom alerts (50 free slots) + Gemini-powered Analytics Advisor rolling out to free properties.
- **Search Console:** Recommendations feature (fully rolled out); claim the new **Generative AI performance report** (June 2026) and use the **branded-query filter** (Nov 2025).
- **Google Ads:** Gemini asset generation is useful; treat **Optimization Score with gloves** — it measures recommendation adoption, not performance; keep auto-apply off and triage recommendations adopt/review/dismiss.
- **Meta Advantage+:** strong average ROAS, but a 55,661-campaign analysis found new-customer acquisition cost can double — monitor new-customer CAC separately.
- **HubSpot Breeze** Copilot features included in existing tiers.

### 5.4 Trigger playbook (if-this-then-that, evidence-backed)

| Trigger | Action |
|---|---|
| GBP rating dips below ~4.4 or a negative review lands | respond within 24h + ask-for-review push to recent happy guests (above ~4.4, review *volume* decides AI-driven discovery; under 4.0 costs ~70% of clicks) |
| Snow forecast ≥6" for the weekend (checked Mon–Tue) | boost ski/cozy content **Wednesday** + "powder weekend" email (Vail's snow-triggered automation lifted last-minute bookings ~23%) |
| Sunny/hot stretch forecast for the coast | shift budget to beach/patio/waterfront creative (weather-matched ads: +89% link clicks in the Molson Coors case) |
| Rainy weekend | promote indoor offers — axe throwing, bowling, tastings, open-house tours; bad weather at home *raises* getaway searches |
| Seasonal term hits 25–30% of its Trends/Pinterest peak | start that season's content now (1–2 month lead) |
| Big local event 2–6 weeks out | event-adjacent content + geo-targeted boost + staffing note |
| GSC: page CTR down, position stable | rewrite title/meta |
| Post outperforms brand baseline by >2σ | "do more of this" card with format/topic/hook breakdown; consider cross-posting to sibling brands |
| Campaign pacing red, or ending ≤7 days with budget left | rebalance/extend recommendation with projected final spend |
| Meta frequency ≥3.5 with fading CTR | creative refresh recommendation |
| Advantage+ new-customer CAC drifts >30% above trailing average | rebalance toward manual prospecting |
| Review volume drops suddenly at any location | check Google's new review filters before assuming unhappy guests |

Every recommendation is **ICE-scored** (impact × confidence × ease), phrased as an action with an owner and a deadline, and shown with its evidence.

### 5.5 News-driven advice feed

A curated strip that turns industry news into one-line guidance, each ending with "what this means for us":

- **Algorithm weather:** confirmed Google update start/end dates annotated on every traffic chart; during a rollout the dashboard literally says "Google update in progress — judge after [end date]." (Only 3 core updates in 2025, but each hit harder.)
- **AI search shifts:** AI Mode/AI Overviews expansions; the AI direct-booking-link test for hotels; per-brand "are we cited when someone asks 'best waterfront restaurant Falmouth'?"
- **Policy compliance:** April 2026 review-policy bans — never set staff review quotas, never ask guests to name employees in reviews, never draft reviews with AI.
- **Platform changes:** metric deprecations (FAQ rich results died May 2026 — that KPI going to zero is by Google's design, not failure), new native features worth adopting (Instagram Competitive Insights).

---

## 6. Measurement framework updates (amendments to v1 §4)

1. **Visibility and clicks are now two separate stories.** The "Great Decoupling" (Ahrefs: impressions-clicks correlation flipped from +0.43 to −0.35; ~68% of searches end without a click) means the dashboard shows impressions + AI mentions as "visibility" and clicks as "visits," with a widening-gap trend that is explained, not alarming. AI-referred traffic is small but converts up to ~23x better — it gets its own row (GA4's new "AI Assistant" channel, May 2026).
2. **The headline row per brand becomes:** (1) total visibility (impressions + AI mentions), (2) qualified visits, (3) actions that matter — bookings, covers, leads, calls, direction requests, (4) branded-search growth. Rankings become a supporting diagnostic.
3. **Local gets equal billing with the website** for restaurant/venue brands — for many locations the Google Business Profile *is* the website. Per location: GBP health score (categories, hours incl. holidays — "open at time of search" is a top-5 local ranking factor, photos fresh, posts ≤14 days), calls, direction requests, plus reviews (rating, velocity, response rate, median response time). Whitespark's 2026 factors weight GBP signals at 32% and reviews at 20% of local ranking.
4. **Vertical split for search strategy:** restaurants/hotels are heavily AI-exposed (AI engines cite Reddit ~22%, Google/Maps ~19%, OpenTable ~13% for dining — almost never restaurant sites), so third-party presence (Reddit, TripAdvisor, best-of lists) is a tracked tile. Real estate has <3% AI Overview coverage — classic rankings and hyperlocal neighborhood pages still win for Longfellow and Lighthouse Station.
5. **Content ops widgets:** a **refresh queue** (cornerstone pages flagged red past 6 months — AI-cited content is measurably fresher) and a **"something new" tally** (pieces with original data, first-person visits, named local authors). Publishing volume alone is no longer a KPI any major publication recommends.

---

## 7. Implementation notes

- Dashboard prototype v2 (`waterside-dashboard.html`) implements: comparison selector (prior period / prior year) that recalculates every delta, a Competitors view with the named sets above, the paid campaign table with pacing and fatigue flags, the TL;DR verdict strip, and the news-driven advice feed. Sample data throughout.
- Rollout phases and the API integration framework from v1 (§6, §9) stand; add to Phase 2: Instagram Competitive Insights setup (10 accounts per flagship brand), Metricool free-tier competitor tracking, monthly Ad Library log, and the GBP Performance API application.
- Estimated incremental tooling cost for v2 features: **$0–$99/month** (all competitor tracking can start on free tiers; Socialinsider optional).

---

## 8. Revenue Centers module (added July 2026)

Each brand lists its revenue centers — the distinct lines of business a customer buys from — and admins can add, rename, or remove them. Example, Flying Bridge Marina: Boat Sales, Boat Club, Service, Slips, Storage.

**Sales data.** Toast-connected brands (the dining group) feed real-time sales per revenue center through the Toast partner API, which carries a revenue-center dimension on every check. Non-POS brands (real estate, marina, hotel) import monthly from accounting, with the data-freshness timestamp making the difference visible. Each center shows: sales today (where real-time), month to date, change vs. last year, and share of brand revenue.

**Opportunity Score — the formula.** The module's purpose is to spot centers where *external demand* and *actual revenue* have drifted apart. Two indexes, each 0–100:

*Demand Index (D)* — how much the market is asking for this center right now:

| Signal | Weight | Source |
|---|---|---|
| Search interest (keyword impressions + trend for center-specific terms, e.g., "boat slips Falmouth") | 25% | Google Search Console + Keyword Planner |
| Web engagement (page views + clicks on the center's pages) | 25% | GA4 |
| Mentions in reviews and comments (share of reviews/social comments referencing the center) | 20% | Google/Yelp/TripAdvisor reviews + social comments, keyword-matched |
| Content coverage (posts published featuring the center, trailing 90 days) | 15% | social + blog content log |
| Hashtag & social volume (center-related hashtag usage and tagged posts) | 15% | Instagram/TikTok public data |

Each signal is normalized against the brand's other centers (percentile within brand), so a marina's slips compete with its storage — not with a restaurant's bar.

*Revenue Index (R)* = 60% revenue-share percentile within the brand + 40% normalized year-over-year growth.

**Opportunity Gap = D − R.**

| Reading | Status | What it means |
|---|---|---|
| Gap ≥ +15 | **Growth opportunity** | People are searching, clicking, and talking about this center more than they're buying — pricing, packaging, booking friction, or visibility on the money pages is the likely blocker. Invest here first. |
| −15 < Gap < +15 and growth ≥ 0 | **Healthy** | Demand and revenue moving together. |
| Growth < 0, or Gap ≤ −15 | **Underperforming — flagged** | Revenue is declining, or sales are coasting on momentum while demand signals thin out — the leading indicator of next season's decline. |

Every flag ships with its evidence (which signals drove the gap) and a one-line recommended action. The formula's weights are configurable per segment and should be revisited after two quarters of live data — the correct weights are the ones that predict next-quarter revenue movement.

## 9. Demographics module (added July 2026)

Audience composition per brand, built from sources already in the stack: Meta audience insights (followers + engaged audience), GA4 demographics and geography (Google Signals), email list geography, TikTok audience analytics, and — where available — Toast order geography and OpenTable guest data. Shows: age distribution (audience vs. customers where both exist), gender split, top home markets with share, new vs. returning, and device mix. Each view leads with a takeaway line ("Weekend visitors skew 25–34 from Greater Boston; email list skews 55+ — two different audiences, two content tracks") because demographic tables without a "so what" are decoration. Privacy note: all data is aggregate and platform-reported; no individual-level data is collected or stored.

---

## Appendix — Research base

Four research briefs (this session, July 2026), each with a full numbered source list:

- `research/competitors.md` — 166 sources: competitor identification for 17 brands + tracking tools
- `research/seo-publications.md` — 141 sources: Search Engine Journal, Search Engine Land, Google Search Central, Ahrefs, Semrush, Yoast, Backlinko, Search Engine Roundtable, Whitespark/BrightLocal (note: Moz blocks automated access; no Moz claims included)
- `research/ai-recommendations.md` — 152 sources: free data feeds, LLM analytics patterns, native AI features, trigger evidence
- `research/campaigns-ux.md` — 94 sources: campaign reporting standards, pacing, attribution, fatigue research, NN/g / Few / Knaflic dashboard design

Combined: **553 source URLs**, exceeding the 200-source requirement. v1's benchmark appendix remains in the original spec file.
