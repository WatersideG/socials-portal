# Research: Paid Campaign Reporting Standards & Dashboard Design for Scannability

Research for a multi-brand marketing dashboard serving two audiences: ownership (glance, judge, decide) and social/content staff (monitor, act, explain). Compiled July 2026 from 60+ web sources (full list at bottom).

---

# TOPIC A — Paid Campaign Reporting Standards (2025–26)

## A1. What belongs in a campaign table

The consensus across agency reporting tools (Improvado, Supermetrics, TapClicks, DigGrowth, AgencyAnalytics, Swydo) is that a campaign-level table needs **identity fields, money fields, delivery fields, and outcome fields** — and that the outcome fields must match the campaign's objective, not a generic metric list.

### The field list

| Group | Field | Notes |
|---|---|---|
| Identity | Campaign name | Enforce a naming convention (below) so the table can be parsed/filtered |
| Identity | Platform | Meta / Google / TikTok etc. — never mix platform metrics without labeling |
| Identity | Objective | Leads, Sales/Purchases, Calls, Traffic, Awareness — drives which "result" column shows |
| Identity | Status | Active / Paused / Ended / Learning. Meta also surfaces "Creative Fatigue" / "Creative Limited" delivery statuses worth passing through |
| Flight | Start date / End date | End date is critical for pacing math and "ending soon" alerts |
| Money | Budget + budget type | Daily vs. lifetime — the pacing math is different for each (see A2) |
| Money | Spend to date | With a data-freshness timestamp ("as of 6 AM today") |
| Money | Pacing % | % of budget spent vs. % of flight elapsed (see formula below) |
| Results | Results (by objective) | Leads, purchases, calls, bookings, etc. — labeled in plain English ("42 leads", not "42 conversions") |
| Results | Cost per result (CPA/CPL) | The number owners actually care about |
| Results | ROAS or revenue | Only for purchase-objective campaigns; showing ROAS on a lead-gen campaign is misleading |
| Delivery | CTR | Engagement health signal |
| Delivery | CPC / CPM | CPM rising with flat targeting = auction pressure or fatigue |
| Delivery | Frequency (Meta) | The #1 creative-fatigue signal — thresholds in A4 |
| Delivery | Impressions / Reach | Context for the ratios |
| Diagnostics | Quality / relevance diagnostics (Meta) | Quality Ranking, Engagement Rate Ranking, Conversion Rate Ranking (below) |

**Key design point (multiple sources):** dashboards fail when they show the same metric block for every campaign. Show CPL for lead campaigns, ROAS for sales campaigns, cost-per-call for call campaigns. Google Ads itself organizes this via "conversion goals" (Purchases, Contacts, Submit lead forms, Phone calls, Bookings) and lets you break conversions out by conversion action — mirror that structure.

### Campaign naming conventions

- Best practice (Adverity, Improvado, Claravine, CampTag): a **fixed-order taxonomy of 6–9 fields separated by one delimiter** (underscore or pipe), lowercase, no spaces, controlled vocabulary per field. Example core: `channel_brand_objective_audience_geo_flight` → `meta_beachhouse_leads_locals_fl_2026q3`.
- Controlled vocabulary matters: `paidsocial` is allowed; `Paid Social`, `paid-social`, `PaidSocial` are not — inconsistency permanently fragments historical reporting.
- Define this **before** launch; renaming mid-flight fragments history. For a multi-brand dashboard, the brand token is the field that makes cross-brand rollups possible.
- Practical fallback: if client campaigns are already messily named, the dashboard should map campaigns to brand/objective via metadata rather than trusting names.

### Meta quality/relevance diagnostics (what to show)

Meta replaced the old Relevance Score with three **Ad Relevance Diagnostics** (Meta Business Help Center):
- **Quality Ranking** — perceived quality vs. ads competing for the same audience (feedback, hide rates, clickbait/engagement-bait signals).
- **Engagement Rate Ranking** — expected engagement vs. competitors for the same audience.
- **Conversion Rate Ranking** — expected conversion rate vs. ads with the same optimization goal.
Each is reported as Above Average / Average / Below Average (bottom 20–35%). Better rankings = cheaper delivery in the auction. On a dashboard, these are best surfaced as a **flag only when Below Average** — not as three permanent columns (they're diagnostics, not KPIs).

### The pacing formula (the single most useful derived field)

```
pacing = (% of budget spent) / (% of flight elapsed)
```
- ~1.0 (within ±5%) = on track → green
- 5–15% off = minor deviation → amber
- >15% off = intervention needed → red
This green/amber/red banding is a documented agency practice (Improvado, Markana Media, Camphouse). A common alert formula: alert when cumulative spend exceeds `target daily spend × days elapsed × 1.15`.

## A2. Budget pacing best practices (how agencies actually do it)

- **Daily human check + automated anomaly detection, both.** Wpromote's documented system: media managers manually check platform spend against pacing rollups every morning AND an anomaly-detection system builds a 10-day predictive forecast from 90 days of spend history, alerting on deviations. Alerts escalate up the management chain if unacknowledged within 2 hours. Their principle: "no single system should be solely responsible" — people + process + tech.
- **Alert on both over- AND under-pacing.** Underspend is "leaving sales on the table" and, for agencies, damages client trust just like overspend. A 10x budget-change alert catches fat-finger errors (extra zero on a Friday).
- **End-date awareness:** the question a pacing view must answer is "are we on track to fully use the budget by the flight end date without over/underspending?" Show days remaining, projected final spend (current daily run-rate × days left + spend to date), and flag campaigns ending within 7 days.
- **Platform mechanics the dashboard must respect:**
  - **Google Ads:** daily budget is a *target*, not a cap. Google can spend up to **2× the daily budget in a single day**, self-correcting so the monthly total never exceeds **30.4× daily budget** (30.4 = 365/12). You're never billed above the monthly cap. Consequence: a "spent 180% of daily budget yesterday" alert is a false alarm; pace monthly, not daily. (Since a June 2024 change, scheduled campaigns pace toward the full 30.4× cap even when running fewer days — compressing spend into active days.)
  - **Meta:** daily budgets average over the **week** — Meta can spend up to ~75% more on a strong day, balancing within 7×daily. **Lifetime budgets** let Meta pace across the whole flight (front-loading good days) and are the only budget type that supports dayparting; they suit fixed-date promos. Daily budgets suit evergreen/always-on.
  - Practical implication: pacing math should treat lifetime-budget campaigns as `% spent vs % flight elapsed` and daily-budget campaigns as `month-to-date spend vs (daily budget × days elapsed)`.
- **Seasonality-adjusted expectations:** sophisticated agency systems adjust the expected-pace curve for known seasonality (e.g., a retail client normally paces at 110% through mid-December) rather than triggering false alarms — relevant for ski/beach seasonal brands.

## A3. Google Ads vs. Meta Ads reporting differences (and how to present them honestly)

**Why the numbers never match (this is structural, not a bug):**

| Aspect | Meta Ads | Google Ads | GA4 |
|---|---|---|---|
| Default attribution window | **7-day click + 1-day view** | 30-day click (adjustable) | 30-day lookback (up to 90 for some events) |
| Model | Last-touch within its own window | Data-driven (within Google touchpoints) | **Cross-channel data-driven** — splits credit across Google, Meta, email, organic |
| View-through conversions | **Yes** (see ad, no click, buy within 24h = counted) | Display/video only | **No** — GA4 has no impression visibility |
| Conversion date | Day of the **click/impression** | Day of the click | Day of the **conversion** |
| Cross-device | Strong (logged-in users) | Strong (logged-in users) | Weak (cookie-based; broken by iOS ATT/ITP) |
| Same user converts twice | Can count multiple | Varies | One conversion per session |

- Each platform **claims full credit for conversions it touched**, so Meta + Google conversions added together will exceed real orders. If one person clicks a Meta ad Monday and a Google ad Wednesday then buys, *both* platforms report 1 conversion; GA4 gives most credit to Google; the CRM shows one sale.
- Clicks ≠ sessions: Meta counts the tap; GA4 only counts a session if the page loads and the tag fires (slow mobile loads, bounces, consent declines all create gaps). 10–20% variance between platforms is **normal** (Ruler Analytics).
- Last-click tools systematically **undervalue prospecting**: Ruler's benchmark data showed Facebook prospecting at 0 last-click ROAS but 4.1× ROAS under marketing-mix modelling. Cutting channels on GA4 last-click numbers alone is a documented way to make wrong budget decisions.
- iOS App Tracking Transparency cut Meta's off-platform visibility; Meta backfills with **modeled conversions** — another reason its numbers are estimates, not counts.

**How to present this honestly to executives (synthesized from Ruler, Cometly, Search Engine Land, EasyInsights):**
1. **Never sum conversions across platforms.** Report each platform's results under its own labeled column, or pick one source of truth (bookings system / POS / CRM) for the "business results" row.
2. **Label the ruler on every number.** A footnote or info-tooltip: "Meta counts a sale if someone clicked within 7 days or saw the ad within 1 day of buying. Google Analytics splits credit across every channel a customer touched. That's why these two numbers differ — both are true, they're just measuring with different rulers."
3. **Set the expectation once, in writing:** numbers will never reconcile perfectly; the goal is understanding *why* they differ, not forcing a match. Minor (10–20%) gaps are noise; investigate only when a gap is big enough to change the decision.
4. **Use platform numbers for platform decisions** (which ad/creative/audience wins inside Meta) and **business-source numbers for budget decisions** (revenue, bookings, calls).
5. **Track ratio stability:** the ratio of platform-reported conversions to CRM/real conversions should be roughly stable over time. If the ratio breaks, investigate; if it holds, the framework is trustworthy (Search Engine Land).

## A4. Meta creative fatigue: frequency benchmarks and refresh timing

**Meta's own research** (Analytics at Meta): mean exposure is 4.2 views per creative per 30 days; conversion likelihood drops **~45% by the 4th repeated exposure**; decay is modeled as (N+1)^-0.43 — every extra impression on a fatigued ad costs compounding efficiency.

**Practitioner frequency thresholds (7-day frequency, prospecting/cold audiences)** — remarkably consistent across TheOptimizer, Madgicx, Flighted, GoodMorning, AdAmigo, MHI Growth:
- **< 1.5** — healthy reach phase
- **1.5–2.5** — working zone; monitor
- **~2.5** — early-warning line (DTC/ecommerce often already declining here); brief replacement creative
- **~3.0** — cross-vertical fatigue signal for cold audiences; rotate within 7 days
- **~3.5** — refresh-now line; past this the ad usually loses money vs. a fresh variant
- **4.0+** — pause or replace immediately
- **Retargeting/warm audiences** tolerate more: 4.0–6.0 acceptable, 6.0+ is the fatigue zone. Brand-awareness campaigns can sustain 8–10+.
- Reels fatigue 30–40% faster than static feed placements — use ~2.8–3.0 as the Reels trigger.

**Frequency alone is not a diagnosis.** The four-signal check (GoodMorning, Motion): fatigue = frequency above band **plus at least one of**: CTR down >10–15% vs. prior 7 days (or >25% vs. the ad's own week-one baseline), CPM rising with unchanged targeting, CVR/ROAS sliding. Frequency 3.5 with stable CTR/CVR = a tight audience that still converts, not fatigue.

**Cost of ignoring it:** CTR drops ~50% after 5–8 exposures; cost per result climbs 50–80% at 5+ exposures; CPC can spike 161% at frequency 9; top ads lose ~38% effectiveness after 5 weeks unrefreshed; negative brand sentiment rises 16% after 10+ views.

**Meta's native flags:** Ads Manager shows **"Creative Limited"** (cost per result elevated above baseline) and **"Creative Fatigue"** (cost per result ≈2× historical baseline). These fire *late* — the 2.5/3.5 frequency reading gives ~a week's head start.

**Refresh cadence:** creatives typically perform 10–36 days; high-performing accounts refresh roughly every 10–14 days; ~half of all creatives get retired before 28 days (Motion 2026 benchmarks, $1.3B spend). Partial refreshes (new hook/headline) fix early fatigue cheaply; full concept overhauls are for collapsed performance.

**Dashboard rule:** show frequency on every Meta campaign row with amber at 2.5 and red at 3.5 (cold) / amber 4.0, red 6.0 (retargeting), and pair the color with the plain-English reason: "Same people have seen this ad 3.8 times — time for fresh creative."

## A5. Period comparisons: prior period vs. prior year

- **For seasonal businesses (ski resorts, beach restaurants), YoY is the honest comparison.** Comparing a ski shop's March to its February tells you about the calendar, not the marketing. Comparing March to last March isolates real performance change. Multiple finance/analytics sources state the default: "unless you have a strong reason otherwise, your safest baseline comparison is the same period last year."
- **Prior period (MoM/WoW) is still useful for operational questions** — "did last week's fix work?" — just never as the headline growth number for a seasonal brand. Best practice: show both, but lead with YoY and label each delta explicitly ("vs. last month", "vs. this time last year").
- **Pitfalls that make even YoY lie:**
  - **Weekday misalignment:** Looker Studio's default YoY compares the same *calendar dates*, so 2025-11-27 (Thursday) compares to 2024-11-27 (Wednesday). For businesses with strong day-of-week patterns (restaurants!), this is materially wrong. Fix: compare same-weekday-same-week (Looker Studio: format the date dimension as `FORMAT_DATETIME("%a, V.%V", date)` so comparisons match weekday+week number; or blend data on week/weekday).
  - **Moving holidays:** Easter shifts by up to a month year to year; a March vs. March comparison where Easter moved to April will show a phantom decline. Same for spring break weeks and local events. The fix is annotation ("Easter fell in March last year, April this year — the dip is calendar, not performance"), not silence.
  - **Leap years / extra days:** Feb 2024 had 29 days vs. 28 — a +3.5% "growth" artifact if unnoticed.
  - **The 4-5-4 retail calendar** (NRF) exists precisely to solve these problems: it divides the year into 4-week/5-week/4-week "months" so comparable periods always contain the same number of each weekday and holidays align. Cost: every 5–6 years a 53rd week appears (FY12, FY17, FY23...), which inflates that year's totals and requires either excluding the extra week or comparing first-52-weeks-only. Takeaway for a marketing dashboard: you don't need to adopt 4-5-4, but you should adopt its *principle* — compare like-for-like weeks, not raw calendar dates.
- **How tools handle it:** GA4 and Looker Studio both offer "previous period" and "previous year" toggles; both default to calendar-date alignment (with the weekday problem above). Looker Studio's "advanced" comparison (today minus 1 year on both ends) plus a weekday-aware dimension is the documented workaround.
- **Comparison honesty rules for the dashboard:** (1) every delta arrow states its baseline in words; (2) seasonal brands default to YoY; (3) known calendar shifts get an automatic or manual annotation; (4) if the brand is <1 year old and has no YoY baseline, say so rather than showing MoM as if it means growth.

---

# TOPIC B — Dashboard Design for Scannability and Storytelling

## B1. Core design principles from credible sources

**The 5-second rule.** An executive should grasp the dashboard's main message — "are we OK, and where's the problem?" — within five seconds of looking (Customer Science, Den Otter, multiple exec-dashboard guides). Design consequence: one headline verdict at the top, biggest numbers first, status colors visible without reading.

**Stephen Few (Information Dashboard Design):** a dashboard is "a visual display of the most important information needed to achieve one or more objectives, consolidated on a single screen so it can be monitored at a glance." His core rules: single screen (scrolling kills monitoring), exceptional clarity, no decoration that doesn't carry data, design aligned with visual perception. His famous "13 common mistakes" include exceeding a single screen, poor visual encodings (gauges, pies), meaningless variety, and cluttered decoration.

**Nielsen Norman Group (dashboard + eye-tracking research):**
- Dashboards are for *monitoring*, not exploration — information consumed fast with minimal interaction (the car-dashboard metaphor: "Am I speeding? Am I out of gas?").
- **Preattentive processing:** humans judge *length* (bar charts) and *2D position* (line charts, scatterplots) quickly and accurately. Area and angle (pies, donuts, gauges, treemaps, 3D anything) are processed poorly — avoid them for quantitative comparison. Gauges waste space and encode via angle, the weakest channel.
- Color is preattentive but **not ordered** — never use color to encode magnitude; use it to flag category/status, and only as a *secondary* cue (pair with icons/text) because ~8% of men are colorblind.
- **F-pattern scanning:** users spend ~80% of viewing time on the left half and the top of the page. Top-left is the most valuable real estate — put the verdict there.

**Cole Nussbaumer Knaflic (Storytelling with Data):** context first (know your audience and the one thing they must take away); choose simple visuals; **clutter is your enemy** (maximize data-ink, strip gridlines/borders/legends where labels can sit on the data); **focus attention** with sparing use of color — gray everything, color only the one line that matters; use **action titles and annotations**: the chart title should state the takeaway ("Bookings up 22% since the new ads launched"), not the topic ("Bookings by month"), and annotations on the chart should explain *why* a line moved.

**Google Material Design / Google's six data-viz principles (Manuel Lima, Google Design):** direct users to essential information quickly; maximize data-ink ratio; apply color *meaningfully* (label, group, highlight, or measure — never decorate); provide context (clear labels, honest axes and baselines, tooltips); be transparent about data provenance; keep graphical treatments and interaction patterns uniform across the whole dashboard so users learn the system once.

**Inverted pyramid (data.europa.eu data-viz guide; journalism-derived):** structure every view conclusion-first: (1) top = the verdict and key KPIs, (2) middle = trends and comparisons that explain the movement, (3) bottom = granular detail and links. A 5-second glance reads layer 1; a 2-minute review reads 1–2; a deep dive uses all three.

**Progressive disclosure (NN/g concept, widely applied):** show the clean summary by default; reveal detail on click/expand. Summary → Segment → Detail, each level answering a more specific question. This is how one dashboard serves both owners (stay at level 1) and staff (drill to level 3) without two products. NN/g-cited research: progressive disclosure can cut cognitive load dramatically (figures up to ~55% are cited in practitioner summaries).

**One number, one message.** Each KPI card carries exactly one metric, one comparison, one status. Don't make a card do two jobs.

**Max metrics per view.** Convergent guidance: executive views **3–5 KPIs** (DashThis: "3 to 10, and if you can get fired for ignoring it, it's critical enough to include"); general dashboards **5–7** (Miller's 7±2 working-memory limit); operational views can stretch to 7–9 for daily users. Beyond ~9 on one screen, comprehension drops and users start skipping metrics entirely. KPI card rows work best at 3–6 across; more and the cards get too narrow.

**Color = meaning, used sparingly (RAG discipline):**
- Red/amber/green only for *status against a target*, never as decoration or brand color, and never more than a handful of colored elements per view — if everything is colored, nothing is.
- Accessibility: ~1 in 12 men can't reliably distinguish red from green (UK Government Analysis Function, Mass.gov, Carbon Design). Always pair color with a second cue: icon (▲▼), text label ("On track"), or position. Some orgs replace RAG hues entirely (e.g., blue/cyan/orange) for colorblind safety.
- Contrast: ≥4.5:1 for body text, ≥3:1 for large text and graphical elements (WCAG). True red/amber/green on white can't all hit contrast targets — another reason to lean on labels + icons.

**Charts:** bars for comparison, lines for trend, sparklines inside KPI cards for glanceable direction. No pies/donuts/gauges/3D (NN/g, Few). Label data directly instead of legends where possible. Honest axes (bars start at zero).

## B2. How executives actually consume dashboards

- **They skim, and they abandon.** Surveys cited by KPI Institute / Towards Data Science: 82% of teams use dashboards to communicate, but **53% report dashboards get disregarded because they take too long to interpret**; most organizations find 60–70% of reporting generates no action. Brent Dykes (Forbes): dashboards show *what* happened but rarely *why* — and the "why" is the part that drives decisions; that's the gap storytelling fills.
- **They rarely challenge what's shown** (77% only sometimes or rarely challenge the data) — which means a misleading chart won't be caught; honesty must be designed in.
- **They read top-left first and quit early** (NN/g F-pattern; ~80% of attention on the left half/top). Anything below the fold or right-rail is effectively optional content.
- **What gets ignored:** detail without hierarchy, metrics that don't map to their goals (executives care about revenue/bookings/leads; clicks and impressions are staff metrics), unexplained jargon, and any number without context. A dashboard "that overwhelms senior leaders with unnecessary detail goes unread."
- **Plain-language labeling** (Databox, AgencyAnalytics, Swydo, Improvado client-reporting guides):
  - Apply the "CFO test": would a smart person who has never run an ad understand every label? If not, rewrite.
  - Translate, don't just abbreviate: "CTR" → "% of people who saw the ad and clicked"; "ROAS" → "dollars back per dollar spent on ads"; "CPL" → "what each new lead cost"; "Frequency" → "times the average person saw this ad"; "Impressions" → "times ads were shown."
  - Practical pattern: plain-English primary label with the industry acronym in small text or a tooltip — staff keep their vocabulary, owners aren't excluded.
- **Benchmark context on every number.** A number without a comparison is unreadable ("Is 2.4% CTR good?"). Every metric needs at least one anchor: vs. target, vs. same period last year, vs. account's own trailing average, or vs. industry benchmark (Databox's benchmark products exist precisely because "average" differs wildly by industry — a fine SaaS conversion rate is a disaster in ecommerce). Best form: delta + direction + plain verdict ("2.4% CTR — above the 1.9% restaurant-industry norm").
- **TL;DR at the top.** Agency reporting guides converge on a 3–4 sentence executive summary at the very top answering: how did it go, what's working, what's the concern, what happens next. "A busy executive who reads nothing else should walk away knowing how things went and what the next move is."

## B3. Insight and annotation text: turning data into narrative

- **Annotations that explain WHY beat charts that show WHAT.** Knaflic: descriptive titles + on-chart annotations are what prevent misreading and give the audience the story. Dykes: moving from "what" to "why" is what unlocks action.
- **News-driven callouts are the highest-trust annotation type.** SEO/analytics practice (Lazarina Stoy's Looker Studio algorithm-update annotation technique, Search Engine Journal, Graphed): overlay known external events on trend charts — "Google core update rolled out March 15; this dip is industry-wide, not your site," "Easter moved to April this year," "iOS update reduced tracking," "Meta raised CPMs during election week." These transform a scary dip into an explained one and demonstrate that the agency/team is watching the horizon. GA4 removed native annotations (later partially restored); Looker Studio needs a manual annotation table or blended event source — meaning a custom dashboard that stores annotations is genuinely differentiating.
- **Formula for a good callout** (synthesized from client-reporting guides): *what changed + why + what we're doing about it*, in one or two sentences, dated. "Leads fell 18% this week (school break — the same dip happened last year). No action needed; volume recovers next week." Cause-and-effect specificity builds trust: don't say "traffic up 20%," say "traffic up 20%, mostly from the refreshed landing pages and the new ad set launched on the 3rd."
- **Annotation hygiene:** attach annotations to a date and a metric (so they render on the right chart), keep a running log (institutional memory across staff turnover), and distinguish *external* events (market-wide) from *internal* ones (we changed the budget) — the external ones are the ones that protect trust when numbers dip.
- **Anticipate the question before it's asked.** The pattern in every strong client-report guide: if an owner will see a red number, the explanation must already be next to it. An unexplained red number generates a phone call; an annotated one generates confidence.

---

# Actionable design rules (synthesis)

**Campaign table**
1. One row per campaign: name, platform, objective, status, flight dates, budget (+type), spend, pacing %, objective-matched results, cost per result, CTR, CPC/CPM, frequency (Meta).
2. Results column speaks the objective's language: leads, purchases, calls, bookings — never generic "conversions."
3. Pacing = % budget spent ÷ % flight elapsed; green ±5%, amber 5–15%, red >15%; flag campaigns ending within 7 days; respect platform mechanics (Google 2×-day/30.4×-month; Meta weekly averaging; lifetime budgets pace against flight).
4. Frequency thresholds: amber ≥2.5, red ≥3.5 for cold audiences (amber 4/red 6 retargeting); pair the flag with a plain-English fatigue message and confirm with CTR/CPM trend before recommending refresh.
5. Surface Meta relevance diagnostics only as exception flags (Below Average), not permanent columns.
6. Never sum conversions across platforms; keep a platform-labeled view and a single "source of truth" business row; footnote the attribution rulers on any cross-platform view.

**Comparisons**
7. Seasonal brands: YoY is the headline comparison; prior-period is secondary and always labeled.
8. Align YoY by weekday-and-week, not calendar date; annotate moving holidays (Easter), leap days, and event shifts automatically where possible.
9. Every delta states its baseline in words ("vs. last July").

**Layout & scannability**
10. Inverted pyramid: verdict + 3–5 KPI cards on top, trends in the middle, tables/detail behind a click (progressive disclosure). Top-left gets the most important thing.
11. Max 5–7 metrics per view (3–5 for the owner view, up to 9 for staff operational views); one number, one message per card; sparkline + delta + status on each card.
12. Bars and lines only; no pies, donuts, gauges, 3D. Length and position are what humans read fast.
13. RAG colors only for status vs. target, sparingly, always paired with an icon or word; check contrast and colorblind safety.
14. Plain-English labels with acronyms as secondary text; pass the "CFO test."
15. Benchmark context on every number: target, last year, own trailing average, or industry norm.

**Narrative**
16. 3–4 sentence TL;DR at the top: how it went, what's working, the concern, the next move.
17. Chart titles state takeaways, not topics.
18. Annotations explain WHY a line moved — especially external, industry-wide events (algorithm updates, holidays, platform changes) — using "what changed + why + what we're doing," dated, stored in a persistent log.
19. Every red number ships with its explanation already attached.
20. Show a data-freshness timestamp; if a chart has no action attached to it, cut it.

---

# Sources consulted

**Topic A — campaign reporting, pacing, attribution, fatigue, comparisons**
1. https://improvado.io/blog/12-best-marketing-dashboard-examples-and-templates
2. https://www.dataslayer.ai/blog/marketing-dashboard-best-practices-2025
3. https://influenceflow.io/resources/social-media-reporting-dashboard-complete-2025-guide-to-tools-implementation-best-practices/
4. https://diggrowth.com/blogs/marketing-metrics/paid-media-dashboard/
5. https://www.adverity.com/blog/best-practices-naming-conventions-marketing-campaigns
6. https://improvado.io/blog/marketing-campaign-taxonomy
7. https://improvado.io/blog/marketing-campaign-naming-conventions
8. https://camptag.ai/resources/marketing-campaign-name-taxonomy.html
9. https://www.claravine.com/crafting-a-taxonomy-structure-a-marketers-guide-to-naming-conventions/
10. https://www.wpromote.com/blog/digital-intelligence/paid-media-budget-pacing/ (fetched in full)
11. https://improvado.io/blog/budget-pacing
12. https://camphouse.io/blog/campaign-pacing
13. https://supermetrics.com/blog/ad-spend-tracking
14. https://www.g2.com/glossary/budget-pacing-definition
15. https://markanamedia.com/blog/budget-pacing-multiple-ppc-accounts/
16. https://www.get-ryze.ai/blog/google-ads-daily-and-monthly-budget-pacing-rules
17. https://support.google.com/google-ads/answer/10486637 (Google Ads spending limits)
18. https://theoptimizer.io/blog/google-ads-just-changed-how-daily-budgets-work-heres-what-it-means-for-your-spend
19. https://www.clicktrends.com/blog/google-ads-budget-pacing-scheduled-campaigns
20. https://roaspig.com/blog/daily-vs-lifetime-budget-meta/
21. https://www.adamigo.ai/blog/daily-vs-lifetime-budgets-ai-optimization-tips
22. https://leadenforce.com/blog/meta-ads-budgets-explained-daily-vs-lifetime-and-cbo-vs-abo
23. https://www.jonloomer.com/qvt/should-you-use-a-daily-or-lifetime-budget/
24. https://www.ruleranalytics.com/blog/analytics/facebook-ads-google-analytics-discrepancy/ (fetched in full)
25. https://searchengineland.com/google-ads-ga4-crm-numbers-never-match-476978 (fetched in full)
26. https://easyinsights.ai/blog/why-conversions-dont-match-across-meta-google-and-ga4-and-how-to-fix-cross-platform-attribution/
27. https://benly.ai/learn/meta-ads/meta-ads-attribution-discrepancies
28. https://www.lighthouse.gr/blog/trending-topics/why-conversion-data-varies-across-ga4-google-ads-meta-ads-and-crm/
29. https://www.cometly.com/post/attribution-data-discrepancies
30. https://www.braze.com/resources/articles/challenges-of-marketing-attribution
31. https://www.adamigo.ai/blog/meta-ads-frequency-benchmarks-when-ads-start-fatiguing (fetched in full)
32. https://goodmorningco.com/blog/what-is-creative-fatigue-meta-ads-frequency-thresholds (fetched in full)
33. https://www.facebook.com/business/help/1346816142327858 (Meta: creative fatigue recommendations)
34. https://medium.com/@AnalyticsAtMeta/creative-fatigue-how-advertisers-can-improve-performance-by-managing-repeated-exposures-e76a0ea1084d (Analytics at Meta)
35. https://theoptimizer.io/blog/meta-ads-creative-fatigue-how-to-detect-it-early-and-what-to-do-about-it
36. https://madgicx.com/blog/creative-fatigue-detection
37. https://motionapp.com/thumbstop-pulse/creative-benchmarks-2026
38. https://adlibrary.com/posts/meta-ad-creative-refresh-rate
39. https://www.facebook.com/business/help/303639570334185 (Meta: quality ranking)
40. https://www.facebook.com/business/help/403110480493160 (Meta: ad relevance diagnostics)
41. https://www.klientboost.com/facebook/facebook-ad-quality-ranking/
42. https://www.oneadvanced.com/resources/the-ultimate-guide-to-year-over-year-analysis/
43. https://insightfulpartners.com/financial-reporting/importance-of-year-over-year-comparisons-and-seasonality/
44. https://www.getfused.com/blog/benefits-of-qoq-vs-yoy-analysis/
45. https://nrf.com/resources/4-5-4-calendar
46. https://www.toolio.com/post/free-tool-guide-reporting-retail-4-5-4-calendar
47. https://www.calculatorian.com/en/articles/time-and-date/fiscal-years-and-week-numbers
48. https://fitsmallbusiness.com/4-5-4-retail-calendar/
49. https://ondigital.io/blog/articles/reporting/how-to-do-accurate-year-over-year-comparisons-in-looker-studio (fetched in full)
50. https://www.graphed.com/blog/what-is-previous-period-in-looker-studio
51. https://lookerstudiobible.com/p/how-to-make-a-same-day-last-year-comparaison-in-looker-studio-739b3a61af81
52. https://www.catchr.io/university/looker-studio-lessons/compare-data-to-previous-period
53. https://support.google.com/google-ads/answer/9143218 (campaign-specific conversion goals)
54. https://support.google.com/google-ads/answer/10995103 (conversion goals)
55. https://support.google.com/google-ads/answer/12007894 (results reporting)

**Topic B — dashboard design, storytelling, executive consumption**
56. https://www.nngroup.com/articles/dashboards-preattentive/ (fetched in full)
57. https://customerscience.com.au/customer-experience-2/designing-actionable-dashboards-the-5-second-rule-for-executives/
58. https://denottersolutions.com/en/data-insights/dashboard-design-5-seconds-rule/
59. https://alphabytesolutions.com/executive-dashboard-design-best-practices-and-examples/
60. https://uxpilot.ai/blogs/dashboard-design-principles
61. https://www.designprinciplesftw.com/authors/stephen-few
62. https://www.amazon.com/Information-Dashboard-Design-At-Glance/dp/1938377001 (Few, Information Dashboard Design)
63. https://www.storytellingwithdata.com/books
64. https://www.mauriziolacava.com/en/6-key-lessons-on-data-storytelling/
65. https://www.leaderself.com/summary/storytelling-with-data-cole-nussbaumer-knaflic/
66. https://m2.material.io/design/communication/data-visualization.html
67. https://medium.com/google-design/redefining-data-visualization-at-google-9bdcf2e447c6 (Google's six principles)
68. https://m3.material.io/blog/data-visualization-accessibility
69. https://data.europa.eu/apps/data-visualisation-guide/the-inverted-pyramid
70. https://www.datacamp.com/tutorial/dashboard-design-tutorial
71. https://appdeck.com/blog/executive-dashboard-design-best-practices
72. https://www.intelligentgraphicandcode.com/design/dashboard-design/dashboard-layout
73. https://dashthis.com/blog/how-many-kpis-go-on-an-executive-dashboard/ (fetched in full)
74. https://www.datawirefra.me/blog/how-many-kpis-on-a-dashboard
75. https://www.mokkup.ai/blogs/maximizing-your-dashboards-impact-key-metrics-to-include/
76. https://www.boundev.ai/blog/dashboard-design-best-practices-guide
77. https://medium.com/@bhushanpriya1607/the-psychology-of-dashboards-why-some-get-ignored-0be3b050a2b1
78. https://www.forbes.com/sites/brentdykes/2018/10/30/the-real-reason-most-dashboards-dont-tell-data-stories/
79. https://www.forbes.com/sites/brentdykes/2021/07/13/shifting-from-what-to-why-how-data-storytelling-unlocks-your-datas-full-potential/
80. https://news.kpiinstitute.org/why-some-dashboards-get-ignored-while-others-drive-action/
81. https://towardsdatascience.com/can-and-should-management-dashboards-tell-stories-68e908c904b7/
82. https://smart-frames.co.uk/2025/01/23/rethinking-rag-colours-in-business-intelligence-tools/
83. https://analysisfunction.civilservice.gov.uk/policy-store/data-visualisation-colours-in-charts/
84. https://medium.com/carbondesign/color-palettes-and-accessibility-features-for-data-visualization-7869f4874fca
85. https://www.mass.gov/info-details/data-visualization-accessibility
86. https://www.swydo.com/blog/client-reporting-best-practices/
87. https://databox.com/client-reporting-best-practices
88. https://agencyanalytics.com/blog/client-reporting-tips
89. https://improvado.io/blog/what-is-client-reporting
90. https://databox.com/marketing-benchmarks-by-industry
91. https://www.sona.com/blog/what-is-a-marketing-benchmark-report-definition-examples-and-best-practices
92. https://lazarinastoy.com/how-to-create-looker-studio-charts-with-seo-algorithm-updates-annotations/
93. https://www.graphed.com/blog/how-to-annotate-in-google-analytics
94. https://www.searchenginejournal.com/seo/track-google-algorithm-updates/
