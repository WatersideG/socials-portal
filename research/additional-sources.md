# Additional Data Sources & Integrations — Strategic Advantage Research
## Waterside Group Marketing Analytics Portal

**Research date:** July 13, 2026 (pricing/status verified against 2025–26 sources)
**Already integrated (baseline):** GA4, GSC, Meta, HubSpot, Google Ads, YouTube, TikTok, Google Business Profile, Toast POS, review platforms, weather APIs, Google Trends, monthly P&L imports.

**Portfolio context:** restaurants + brewpub (Toast), 29-room boutique hotel, Three Suns Captiva vacation rentals (FL), South Peak ski-resort real-estate community at Loon Mountain (NH), marinas, Harbor Lights golf/wedding venue, 55+ condos, custom home builder, furniture store, retail.

**The core thesis of this research:** the biggest competitive edge for a portfolio this size is not another enterprise data feed — it is (a) *free or near-free demand-side signals* that local competitors ignore (Google free booking links, Apple Business Connect, Census permits, state tourism data, school calendars, ski-pass economics), and (b) *leading-indicator pacing data* already latent in the booking systems each business uses (Dockwa, reservation books, hotel booking pace) surfaced in one portal next to the lagging GA4/social metrics. Section 13 develops this explicitly.

---

## 1. Foot Traffic Intelligence

### Placer.ai
- **What it provides:** anonymized mobile-location foot traffic — your visits vs. named competitors' visits, trade areas, visitor demographics, cross-shopping, true visit trends by day/hour.
- **Access model:** annual SaaS subscription, sales-gated custom quote; no self-serve tier. [Placer.ai pricing page](https://www.placer.ai/pricing) confirms "customized subscription packages" only.
- **Realistic cost (2025–26):** estimates cluster at **$5,000–$30,000/yr**, with enterprise tiers **$12K–$50K+/yr**; costs scale with number of tracked locations and API access adds roughly **$2,000–$10,000/yr** ([Software Finder](https://softwarefinder.com/analytics-software/placer-ai), [Capterra](https://www.capterra.com/p/199858/Placer-ai/), [municipal vendor comparison PDF](https://www.tontitown.com/wp-content/uploads/2026/05/8D.-Placer.ai-comparison.pdf)). SMBs consistently report budget strain as locations/data depth grow ([Oreate cost analysis](https://www.oreateai.com/blog/understanding-the-cost-of-placerai-what-you-need-to-know/a4189949cff62b13a96c1ac5f2b2acbe)).
- **Integration effort:** low for dashboard use; medium for API into the portal (CSV/API exports).
- **Strategic edge for this portfolio:** genuinely unique — it's the only practical way to see *competitor restaurant and retail visit trends* (e.g., is the rival brewpub's Friday traffic growing?). But at ~10+ locations the realistic quote lands $25K–$50K/yr. Alternatives are no cheaper: [Advan ~$15K+/yr, Buxton/SiteZeus ~$20K+/yr, Unacast custom licensing](https://www.tontitown.com/wp-content/uploads/2026/05/8D.-Placer.ai-comparison.pdf).
- **Verdict:** high strategic value, poor cost fit today. Revisit if a single high-stakes question (site selection for a new restaurant, competitor cannibalization) justifies a one-year, one-market contract. A free partial proxy: Google Business Profile "Popular times"/visit trends you already ingest, plus [Google Trends](https://trends.google.com) geo-queries.

---

## 2. Vacation Rental Comps (Three Suns Captiva + South Peak rentals)

### AirDNA
- **What it provides:** Airbnb/Vrbo market ADR, occupancy, RevPAR, booking lead time, seasonality, and property-level revenue projections (Rentalizer) across 10M+ listings / 120K+ markets ([AirDNA](https://www.airdna.co/), [AirDNA pricing](https://www.airdna.co/pricing)).
- **Access/cost (2026):** free Explorer tier (capped); **Starter ~$15/mo per market**, **Professional ~$25–40/mo** adds historical data, multi-market and exports; enterprise/API custom-priced ([BNBCalc review 2026](https://www.bnbcalc.com/reviews/airdna-review-2026), [10xBNB review](https://learn.10xbnb.com/airdna-review/), [Awning review](https://awning.com/post/airdna-review)).
- **Integration effort:** low (dashboard + CSV export); API is enterprise-only.
- **Strategic edge:** two markets (Captiva/Sanibel FL and Lincoln/Loon NH) for **under $100/mo total** gives rate-setting and occupancy benchmarks competitors' owners rarely track — e.g., pricing South Peak townhomes against the Lincoln STR comp set during Ikon-driven peak weekends.

### Key Data (Key Data Dashboard)
- **What it provides:** benchmarking from *direct PMS reservation data* (not scraped) — 65+ PMS sources, 700K+ properties, 45+ KPIs incl. forward-looking occupancy pacing, plus owner-ready reports ([Key Data](https://www.keydatadashboard.com/), [ProData](https://www.keydatadashboard.com/products/prodata)).
- **Access/cost:** subscription, quote-based; requires connecting your PMS (80+ integrations). Aimed at professional property managers ([Hostfully BI tools guide](https://www.hostfully.com/blog/str-business-intelligence-tools/)).
- **Integration effort:** medium (PMS connection); worth it only if Three Suns Captiva is run on a supported PMS.
- **Strategic edge:** forward-looking *pacing vs. market* — a true leading indicator (see §13) and the owner-report feature doubles as a homeowner-acquisition sales tool for the rental program.

### PriceLabs Market Dashboards
- **What it provides:** daily-refreshed Airbnb/Vrbo market dashboards — occupancy, ADR, RevPAR, booking window, length of stay, custom comp sets by radius ([PriceLabs Market Dashboards](https://hello.pricelabs.co/market-dashboards/), [help docs](https://help.pricelabs.co/portal/en/kb/articles/market-intel-dashboard)).
- **Access/cost:** **$9.99/dashboard/month**; one free dashboard bundled with the Dynamic Pricing product ([PriceLabs](https://hello.pricelabs.co/market-dashboards/)).
- **Integration effort:** very low.
- **Verdict:** cheapest credible STR market data on the market; buy two dashboards (Captiva + Lincoln NH) for ~$20/mo, and consider the dynamic-pricing product itself for the rental units.

---

## 3. Hotel Market Data (29-room boutique)

### STR / CoStar STR Benchmark ("STAR report")
- **What it provides:** the industry-standard occupancy/ADR/RevPAR benchmark vs. an anonymized comp set; 94,000 hotels globally; independents are their own chain-scale category ([CoStar STR Benchmark](https://www.costar.com/products/str-benchmark), [FAQs](https://www.costar.com/products/str-benchmark/resources/faqs)).
- **Access model:** *data exchange* — you must submit your occupancy, ADR and room revenue to receive benchmarks ([Engine STAR report guide](https://engine.com/business-travel-guide/star-report-hotel), [Little Hotelier](https://www.littlehotelier.com/blog/running-your-property/star-report/)).
- **Realistic cost:** pricing is not published; a basic monthly STAR report carries a "modest subscription fee," daily data costs more, and one-time trend reports run ~$600 ([Engine](https://engine.com/business-travel-guide/star-report-hotel), [Hospitality Net FAQ](https://www.hospitalitynet.org/news/4127272.html)). For a 29-room independent expect low-thousands/yr, not five figures — the full CoStar platform is a separate, much larger contract.
- **Strategic edge:** independents arguably benefit *more* than chains because they have no brand data to fall back on ([Chekin STR guide](https://chekin.com/en/blog/str-report-for-hotels/)); boutique hotels outperformed traditional comps in 2025 (demand +3.1% vs −0.6%, ADR $258 vs $192 — [CoStar analysis](https://www.costar.com/article/1969001935/what-the-2025-numbers-are-really-telling-us-about-boutique-hotels)), a story worth benchmarking against. Monthly RevPAR index (yours vs. comp set) is the single best "are we winning?" hotel KPI for the portal.

### Lighthouse (formerly OTA Insight)
- **What it provides:** competitor rate shopping (1.7B data points/day across 16.4M hotels *and* short-term rentals), demand signals, parity monitoring; #1 rate-shopping tool in the 2026 HotelTechAwards ([Lighthouse](https://www.mylighthouse.com/), [Rate Insight](https://www.mylighthouse.com/platform/rate-insight), [Hotel Tech Report](https://hoteltechreport.com/revenue-management/market-intelligence-tools/lighthouse-rate-insight)).
- **Access/cost:** quote-based subscription ([pricing page](https://www.mylighthouse.com/platform/pricing) publishes no numbers); independent-hotel entry tiers are typically low-hundreds/month per property.
- **Integration effort:** low-medium (standalone SaaS; some PMS/RMS integrations).
- **Strategic edge:** the hotel + STR combined view fits this portfolio exactly (the 29-room hotel competes with local Airbnbs). Second priority after STR — rate intelligence matters most once you know your RevPAR index.

### Google Hotel Ads / Free Booking Links + metasearch
- **What it provides:** your direct rate shown alongside OTAs in Google's hotel module. Free booking links (launched 2021) cost **$0** and label the hotel site "Official site" ([D-EDGE](https://www.d-edge.com/googles-free-booking-links-the-secret-weapon-for-hotels-in-the-battle-for-direct-bookings/), [Minihotel 2026 guide](https://minihotel.io/blog/google-hotels-complete-guide/)).
- **Access model:** free; requires an active Google listing + a connectivity partner (booking engine/channel manager) feeding real-time rates ([Minihotel](https://minihotel.io/blog/google-hotels-complete-guide/)). Paid Hotel Ads on top; note Google eliminated commission bidding, changing metasearch economics ([Sojern](https://www.sojern.com/blog/google-eliminated-commission-bidding--heres-how-to-make-metasearch-work-for-your-hotel)).
- **Realistic performance:** free links typically deliver 15–25% of paid-placement volume — a zero-cost direct-booking baseline that compounds ([Digital Fox](https://digitalfoxllc.com/blog/hotel-metasearch-vs-direct.html)); rate parity vs. OTAs is the make-or-break factor ([Apycue](https://apycue.com/blog/how-to-win-direct-bookings-on-google-hotel-metasearch)).
- **Integration effort:** low if the booking engine is Google-connected; the portal should track free-link impressions/clicks via Hotel Center reporting.
- **Strategic edge:** every direct booking stolen back from Expedia/Booking is ~15–20% commission saved — the highest-ROI single action in this entire document for the hotel.

### Amadeus Demand360 (evaluated, not recommended now)
- Forward-looking 12-month occupancy + comp-set ranking from 44K hotels and 35M STRs ([Amadeus Demand360](https://www.amadeus-hospitality.com/solutions/business-intelligence/demand360/), [Hotel Tech Report](https://hoteltechreport.com/revenue-management/market-intelligence-tools/amadeus-demand360)). Quote-based, chain-oriented pricing; overkill for 29 rooms until STR + Lighthouse are in place.

---

## 4. Marina-Specific Data

### Dockwa (+ Dockwa Insights)
- **What it provides:** the dominant marina reservation marketplace + management platform; the **Insights add-on** delivers occupancy trends, ADR, lead flow, *pacing reports and forecasts (bookings vs. plan)*, traffic/lead analytics, revenue trends daily/weekly/seasonally ([Dockwa Insights](https://marinas.dockwa.com/business-insights), [Dockwa marina platform](https://marinas.dockwa.com/marina-software)).
- **Access/cost:** modular pricing — mix-and-match features per marina ([Dockwa pricing](https://marinas.dockwa.com/marina-software-pricing), [Capterra](https://www.capterra.com/p/147452/Dockwa/)); marketplace bookings carry per-reservation fees.
- **Integration effort:** low if the marinas already run Dockwa (likely); Insights is a toggle + export, no public API — plan on CSV/report ingestion into the portal.
- **Strategic edge:** transient-slip *lead flow and pacing* is a leading indicator of the entire waterfront season — slip reservations pace 2–8 weeks ahead of restaurant covers at the dockside restaurant. Nobody else in the harbor is cross-referencing slip pacing with restaurant staffing and marketing spend.

### Snag-A-Slip
- **What it provides:** second-tier slip booking marketplace (700+ marinas, US/Bahamas/Caribbean), free to list, percentage fee per reservation, "Instant Book" ([Snag-A-Slip for marinas](https://www.snagaslip.com/snag-a-slip-for-marinas), [FAQ](https://www.snagaslip.com/frequently-asked-questions/)).
- **Strategic edge:** marginal — worth listing on for incremental demand capture, but its analytics are thin vs. Dockwa. Treat as a distribution channel, not a data source.

### Boating demand signals (free composites)
- NMMA/industry boat-sales trends, plus your own Dockwa lead data, plus weather APIs you already have. The [Cape Cod Commission ferry survey work](https://www.capecodcommission.org/about-us/newsroom/five-years-of-ferry-surveys-data-collection-to-preserve-critical-federal-funding/) shows how regional bodies publish boating/ferry demand context for free (see §14).

---

## 5. Restaurant Reservation & Demand Data

### OpenTable — API reality check (2025–26)
- **Status:** no public consumer/search API — partner API is restricted to restaurant operators under direct agreement ([OpenTable platform docs](https://platform.opentable.com/documentation/), [OpenTable support](https://support.opentable.com/s/article/What-is-OpenTable-s-Consumer-API?language=en_US)).
- **Critical 2025 change:** new terms require restaurants to make OpenTable their reservation "system of record" with full inventory on the marketplace (effective April 16, 2025), and OpenTable now **charges for data egress to third parties: $250/location for existing SevenRooms+OpenTable customers, up to $1,000/location for new ones** ([Restaurant Business](https://www.restaurantbusinessonline.com/technology/opentable-will-require-restaurants-make-it-their-primary-reservations-system), [The Hustle](https://thehustle.co/opentable-reservation-tech-sevenrooms), [Hospitality Technology](https://hospitalitytech.com/debate-who-owns-restaurants-data-heats-opentable-makes-changes), [Restaurant Dive on earlier blocking](https://www.restaurantdive.com/news/opentable-blocks-data-sharing-with-competitors/550662/)).
- **Portal implication:** if the restaurants use OpenTable, pull *covers-booked-by-future-date* (pacing) via its native reporting exports rather than paying egress fees; if choosing a system fresh, weigh the data-lock-in.

### SevenRooms
- **What it provides:** reservations + CRM with an *open* integration/API posture (POS, marketing, PMS integrations) ([SevenRooms integrations & APIs](https://sevenrooms.com/platform/integrations-apis/)).
- **Cost:** quote-based SaaS, typically mid-hundreds/mo per venue.
- **Strategic edge:** guest-data ownership (spend per guest via Toast integration, visit frequency, tags) feeding HubSpot — turns the reservation book into a CRM asset OpenTable won't give you. Best fit if the restaurants want owned guest data over marketplace demand.

### Resy
- **What it provides:** reservations, automated waitlist, Resy Analytics (reservations, cover performance, guest surveys), Toast/Square POS integration, and **Reserve with Google** so guests book from Search/Maps ([Resy for restaurants](https://resy.com/join/reservations/), [Resy Analytics helpdesk](https://helpdesk.resy.com/resy-analytics-BJdQMvX8_)). Waitlist Performance reporting quantifies quoted-wait accuracy and drop-off ([Resy](https://resy.com/join/reservations/)).
- **Cost:** flat monthly tiers (historically ~$249–$899/mo), no per-cover fees at most tiers.

### Yelp Guest Manager & Google Reserve
- Yelp Guest Manager combines reservations + waitlist with POS integration and claims up to 92% wait-quote accuracy ([Yelp comparison article](https://business.yelp.com/resources/articles/online-restaurant-reservation-systems/?domain=restaurants), [SelectHub Resy vs Yelp](https://www.selecthub.com/restaurant-reservations-software/resy-os-vs-yelp-for-restaurants/)).
- **Reserve with Google is free** through participating providers — make sure whichever system is used has it switched on; it converts Maps intent directly.
- **Portal metric that beats social metrics:** *reservation pacing* — covers on the books for the next 14/30 days vs. same time last year (see §13).

---

## 6. Weddings & Events (Harbor Lights)

### The Knot / WeddingWire (The Knot Worldwide)
- **What it provides:** the dominant couple-facing directories; vendor Storefront with lead flow, and (new since 2024) **free Storefronts** plus flexible paid placement ([TKWW press release](https://www.theknotww.com/press-releases/the-knot-worldwide-announces-new-platform-features-to-drive-wedding-vendor-success), [Business Wire](https://www.businesswire.com/news/home/20240730891687/en/The-Knot-Worldwide-Announces-New-Platform-Features-to-Drive-Wedding-Vendor-Success)).
- **Realistic cost:** listing tiers **$50/mo to $1,200+/mo** by market and placement; competitive metros commonly $6,000–$12,000/yr for high-tier venue placement; The Knot and WeddingWire listings are often sold bundled ([Fully Booked Venue pricing guide](https://www.fullybookedvenue.com/the-ultimate-guide-to-the-knot-vendor-pricing/), [Curate](https://curate.co/blog/the-knot-advertising-cost/)). ROI reviews are mixed for photographers but stronger for venues ([Zach Nichols long-term review](https://www.zachnicholz.com/blog/is-advertising-on-weddingwire-amp-theknot-worth-the-money-a-long-term-professional-review), [Fully Booked Venue honest breakdown](https://www.fullybookedvenue.com/is-the-knot-worth-it-for-vendors/)).
- **Analytics edge:** Storefront lead volume, inquiry-to-tour conversion and seasonality belong in the portal as the wedding pipeline's top-of-funnel — leads booked today are revenue 12–18 months out (the ultimate leading indicator).

### Zola
- **Free listing; pay-to-connect per lead** (credits) or flat monthly/annual unlimited plans ([Zola for Vendors](https://www.zola.com/for-vendors), [Zola cost FAQ](https://www.zola.com/faq/360002891772-what-does-it-cost-to-be-listed-on-zola-), [Johnson Jones Group Zola vs The Knot](https://johnsonjonesgroup.com/zola-vs-the-knot/)). Zero-risk: list free, pay only for fit leads.
- **Bonus data:** the [Zola Wedding Cost Index](https://www.zola.com/expert-advice/zola-wedding-cost-index) (avg venue $8,573; range $6,900–$10,300) is free market-pricing intelligence for Harbor Lights package pricing.

### Wedding demand seasonality
- Use free Google Trends ("NH wedding venue", "barn wedding New England") + The Knot inquiry data to model the Dec–Feb engagement-season inquiry spike and time ad spend; no paid tool needed.

---

## 7. Golf (Harbor Lights)

### GolfNow / TeeOff (NBC Golf)
- **What it provides:** tee-time marketplace + GOLF Business Solutions tech; bookings auto-populate the tee sheet ([GolfNow Business](https://www.golfnow.com/golfnow-business), [Teesnap integration](https://www.teesnap.com/blog/the-golfnow-integration/)).
- **The trap:** the **barter model** — courses hand over 1–2 tee times/day that GolfNow sells (Hot Deals) keeping 100%; that can equal **~$100K+/yr in retail value** for a public course, and discount-trained golfers resist direct full price ([Golf Course Technology deep dive](https://www.golfcoursetechnologyreviews.org/blog/trading-tee-times-for-tech-a-deep-dive-into-golfnows-barter-model-with-paul-sampliner), [Your Nice Shot](https://www.yourniceshot.com/blogs/news/is-golfnow-worth-it-for-your-golf-course-pros-cons-and-hidden-costs), [Growth GCC](https://growthgcc.com/blog/the-golfnow-trap--take-back-control-of-your-club)). Courses are migrating to SaaS tee sheets to escape barter ([Easy Tee](https://easyteegolf.com/articles/is-golfnow-worth-it/)).
- **Verdict:** avoid barter; if already on it, quantify the give-away in the portal (barter rounds × rack rate) — that alone is a strategic insight.

### Lightspeed Golf
- **What it provides:** tee sheet + POS + dynamic pricing; **Partner API (V2)** reads tee sheet, pricing, customers and can book/modify/check-in/pay ([Lightspeed Golf Partner API docs](https://partner-api.docs.chronogolf.com/), [Lightspeed Golf](https://www.lightspeedhq.com/golf/)).
- **Cost:** from **$325/mo** usage-based; no free tier ([Capterra](https://www.capterra.com/p/151997/Chronogolf/)).
- **Strategic edge:** a real API means *rounds-booked pacing, utilization by daypart, and dynamic pricing yield* can flow straight into the portal — golf becomes the most instrumentable outdoor business in the portfolio.

---

## 8. Ski / Outdoor Demand (South Peak @ Loon)

### Ikon/Epic pass economics as a demand signal
- Loon is **Ikon** (7 days full / 5 days Base), not Epic ([Ikon–Loon](https://www.ikonpass.com/en/destinations/loon-mountain), [Loon season passes](https://www.loonmtn.com/season-passes/ikon-pass)).
- 2025–26 trend: Epic pass units down ~3% with a 13% visitation decline amid weak Western snow, while Alterra sells ~1M Ikon passes vs Vail's ~2M Epic; Ikon raised prices 4–6% vs Epic's 7% ([PeakRankings 2026-27 shakeup](https://www.peakrankings.com/content/epic-vs-ikon-vs-mountain-collective-vs-indy-2026-27), [Vail Daily](https://www.vaildaily.com/news/ikon-pass-2025-26-launch-price-sale/), [Deseret News](https://www.deseret.com/lifestyle/2026/04/06/vail-alterra-ski-resort-lawsuit-lift-ticket-ikon-epic-season-pass-prices/)).
- **Edge:** Ikon momentum + Loon's Ikon access = destination-skier demand tailwind for South Peak real estate and rentals. Track pass price announcements (March) and Vail's quarterly pass-sales disclosures (free, public) as a leading indicator for winter bookings and buyer sentiment.

### OnTheSnow / Mountain News Data & AI
- **What it provides:** real-time snow reports, lift/trail status, resort weather via the **Mountain News Partner API** — snowfall history and conditions for Loon and every NH competitor ([Mountain News Partner API](https://partner.docs.onthesnow.com/), [Snowreport API](https://partner.docs.onthesnow.com/api-reference/ski-resort-snowreport-api), [Mountain News Data/AI](https://www.mountainnews.com/data-ai/)).
- **Access/cost:** fee-based partner API (media/government/finance oriented); public RSS was shut off years ago ([SnowPro Portal](https://snowproportal.com/updates/on-the-snow-blocks-public-api)). Alternative: [Ski API](https://skiapi.com/) (indie, cheaper) or NOAA/NWS snowfall (free — you already have weather APIs).
- **Note:** Liftopia effectively collapsed post-COVID; its data model is gone — don't plan around it.
- **Edge:** correlate snowfall-at-Loon with rental pacing, restaurant covers, and real-estate inquiry volume — "every 6-inch storm = X% lift in weekend covers" is portal gold and free-ish via NOAA.

### Strava Metro & AllTrails
- **Strava Metro is free** — but only to *qualified organizations*: urban/trail planners, governments, trail nonprofits, academics; it provides segment-level pedestrian/bike trip counts hourly-to-yearly ([Strava Metro](https://metro.strava.com/), [FAQ](https://metro.strava.com/faq), [academic program](https://stories.strava.com/articles/introducing-strava-metro-for-academic-researchers)). A private hospitality company won't qualify directly — partner with the town of Lincoln, a trail association, or the local chamber to access it (e.g., [Whitefish Legacy Partners used it for trail-economy questions](https://metro.strava.com/case-studies/whats-new-with-strava-metro)).
- **AllTrails:** consumer heatmaps show trail crowding ([TechRadar comparison](https://www.techradar.com/features/strava-vs-alltrails-how-do-the-activity-apps-compare)) but there is **no business data product/API** — use qualitatively for content targeting (which trailheads to name in ads), not for the portal.

### Visit NH / state tourism statistics (free)
- NH Division of Travel & Tourism publishes **travel-impact data, monthly travel-trends reports (e.g., June 2025 PDF), and the NH Travel Impact Online Tool** sortable by region/county ([Visit NH research](https://www.visitnh.gov/industry-members/industry-resources/research), [travel impacts](https://www.visitnh.gov/industry-members/industry-resources/research/travel-impacts), [June 2025 Travel Trends PDF](https://www.visitnh.gov/getmedia/273430b3-c2f5-4b1b-9038-a3414a0a912c/New-Hampshire-Travel-Trends-June-2025.pdf)).
- Context worth encoding: visitor volume 34.7M person-nights (2019) → 41.2M (2023), spending $5.9B → $7.2B; **2025 saw a Canadian-visitor falloff** hitting NH tourism ([Granite State News Collaborative](https://www.collaborativenh.org/granite-solutions-coronavirus-1/2025/11/24/tourism-in-new-hampshire-where-does-it-stand-in-wake-of-the-falloff-in-number-of-canadian-visitors), [Boston Globe](https://www.bostonglobe.com/2025/05/22/metro/nh-summer-travel-canada-tourists-expectations-tourism/), [NHES trade & tourism chapter](https://mm.nh.gov/files/uploads/nhes/documents/vs25-ch10-trade-tourism.pdf)).
- **Edge:** free quarterly context layer for the portal; the Canada falloff specifically argues for reweighting ad geo-targeting toward Boston/CT/NY drive markets.

---

## 9. Real Estate (South Peak sales, 55+ condos, custom builder)

### Zillow / Redfin / Realtor.com (what's current)
- Zillow's public API is effectively **closed to most developers** (business model shifted to transactions) ([RealtyAPI 2026 guide](https://www.realtyapi.io/blog/how-to-get-property-data-from-zillow-using-an-api-2026-guide)); however **Zillow Research data (ZHVI, ZORI rent index) remains free CSV downloads** ([Zillow Research data](https://www.zillow.com/research/data/), [Zillow developers/public data](https://www.zillowgroup.com/developers/public-data/)).
- **Redfin Data Center** still offers downloadable market data; **Realtor.com Data Library** gives free weekly/monthly inventory and "market hotness" at metro/county/ZIP level ([GWU research guide](https://libguides.gwu.edu/c.php?g=1454849&p=11272938)).
- **Edge:** free monthly ingest of ZIP-level price, inventory, days-on-market and *hotness* for Lincoln NH, the 55+ condo towns, and builder territory — demand-side context for real-estate marketing pacing.

### ATTOM Data
- **What it provides:** national property data API — deeds, mortgages, sales, AVMs, plus **300M+ building permits from 2,000+ jurisdictions** ([ATTOM property data API](https://www.attomdata.com/solutions/property-data-api/), [ATTOM permit data](https://www.attomdata.com/data/property-data/nationwide-building-permit-data/), [developer docs](https://api.developer.attomdata.com/docs)).
- **Cost:** entry ~**$95/mo** reported; real deployments are custom-quoted ([Oreate ATTOM pricing analysis](https://www.oreateai.com/blog/navigating-attom-data-api-pricing-what-to-expect-for-2025/6b2a14a54029154bd57b762132d25bee), [Datarade profile](https://datarade.ai/data-providers/attom/profile)).
- **Edge:** recent-sale + new-owner data in builder territory = direct-mail/geo-targeted lead lists (new land purchases without structures = custom-home prospects).

### Building permits as a builder leads signal
- **Free:** the [Census Building Permits Survey](https://www.census.gov/construction/bps/index.html) — monthly, at **state, CBSA, county and permit-issuing-place level**, released ~17 working days after month end, downloadable CSV ([about BPS](https://www.census.gov/construction/bps/about.html), [release schedule](https://www.census.gov/construction/bps/schedule.html)); HUD republishes county-level permits as open GIS data ([HUD Open Data](https://hudgis-hud.opendata.arcgis.com/datasets/HUD::residential-construction-permits-by-county/about)). This tells you *where* residential construction demand is heating up — free market timing for the builder and the furniture store.
- **Paid record-level:** [Shovels.ai](https://www.shovels.ai/) — permit records + contractor profiles from 1,800+ jurisdictions, **from ~$599/mo** ([Shovels pricing docs](https://docs.shovels.ai/docs/knowledge-base/getting-started/pricing-structure), [PermitStack comparison](https://permit-stack.com/blog/building-permit-data-api-pricing-compared.html)). Record-level permits = named leads (homeowner just permitted a renovation → furniture store + builder prospect). Worth a trial *only if* NH/MA jurisdiction coverage checks out — many small New England towns are paper-based; verify Grafton County coverage before paying.

### Local MLS
- NEREN (New England Real Estate Network) IDX/RETS feeds are broker-access; the portfolio's brokerage arm can pull inventory/absorption directly at nominal MLS fees. Use for on-market comp dashboards rather than buying third-party feeds.

---

## 10. Consumer Spend Intelligence — SMB reality check

- **Bloomberg Second Measure:** transaction panel of 20M+ consumers covering 3,000+ companies — built for **investors and enterprises**, priced accordingly (Bloomberg terminal/enterprise licensing) ([Second Measure](https://secondmeasure.com/), [Bloomberg data spotlight](https://www.bloomberg.com/professional/insights/data/data-spotlight-transactions-fundamentals-more/)).
- **Earnest Analytics:** now merged into **Consumer Edge**; row-level card data for institutional clients ([Earnest data for companies](https://www.earnestanalytics.com/data-for-companies), [Earnest credit card data](https://pages.earnestanalytics.com/earnest-credit-card-data)).
- **Affinity Solutions:** bank-direct purchase data from 150M+ cards; unpublished enterprise pricing ([Affinity Solutions](https://www.affinity.solutions/our-data/), [Datarade profile](https://datarade.ai/data-providers/affinity-solutions/profile)).
- **Mastercard SpendingPulse:** daily metrics refreshed weekly with 5–7-day lag, county-level granularity, travel & hospitality vertical; sold via Mastercard/AWS Marketplace at unpublished enterprise pricing ([SpendingPulse](https://www.mastercard.com/us/en/business/insights-intelligence/economic-market-insights/solutions/spendingpulse.html), [travel & hospitality edition](https://www.mastercard.com/us/en/business/insights-intelligence/economic-market-insights/solutions/spendingpulse/travel-and-hospitality.html), [AWS Marketplace listing](https://aws.amazon.com/marketplace/pp/prodview-q27tc3dgqlhew)).
- **Verdict: not realistic for SMB.** These are five-to-six-figure institutional products. The *free substitute*: Mastercard's public [SpendingPulse press summaries](https://www.mastercard.com/us/en/business/industry-segment/small-medium-business/small-business-navigator/spendingpulse-reports.html) and Visa/Mastercard holiday-spend releases as quarterly narrative context, plus Toast's own benchmark reports for restaurant spend trends. Skip the category as a paid integration.

---

## 11. UGC & Influencer

### TINT
- UGC aggregation + **rights management** (legal usage rights workflow), influencer discovery, analytics; plans start **~$99/mo** (Starter: 1 user, 2 social connections) ([Influencer Hero UGC platform roundup](https://www.influencer-hero.com/blogs/best-user-generated-content-ugc-platforms---features-review-pricing), [Capterra TINT](https://www.capterra.com/p/178705/TINT/), [G2 TINT](https://www.g2.com/products/tint/reviews)).

### Flowbox
- Europe-leading UGC platform; collects/moderates/distributes UGC with rights-request workflows and e-commerce embeds; **custom pricing** based on site traffic/domains ([Flowbox](https://getflowbox.com/), [Flowbox UGC platforms guide](https://getflowbox.com/blog/ugc-platforms/), [Gartner Peer Insights](https://www.gartner.com/reviews/product/flowbox-ugc-platform)).
- **Fit:** hospitality UGC (guest photos of the marina sunset, wedding shots at Harbor Lights) is the portfolio's cheapest high-converting creative. One TINT-class subscription shared across all brands beats per-brand tools. Rights management matters most for wedding photos (photographer copyright).

### Instagram Collab + Partnership Ads (free/native)
- Collab posts surface on both accounts' feeds, doubling organic reach at $0 ([Sticki collab ads guide](https://www.sticki.com.au/post/instagram-collab-ads-what-are-they-and-how-brands-creators-can-win-with-this-ad-type)); partnership ads (renamed from branded content ads, May 2023) deliver on average **19% lower CPA and 13% higher CTR**, and Meta is rolling out a **Partnership Ads API and Creator Discovery API** with performance insights in the Partnership Ads Hub ([Marketing Dive](https://www.marketingdive.com/news/meta-streamlines-brands-creator-partnerships-with-ai-powered-updates/807629/), [Instagram help](https://help.instagram.com/116947042301556), [Strike Social](https://strikesocial.com/blog/instagram-partnership-ads-branded-content-ads/), [Aspire guide](https://www.aspire.io/blog/instagram-branded-content-101)).
- **Local influencer discovery:** for a portfolio this size, skip $500+/mo discovery SaaS — use Meta's native Creator Discovery API/Hub (free within Ads Manager) plus manual scouting of NH/Cape hashtags; measure via partnership-ad insights already flowing into your Meta integration.

---

## 12. Search / AI-Answer Extras (all free — do all of them)

### Bing Webmaster Tools + Bing Places (bing.com/forbusiness)
- **Free.** October 2025: Microsoft unified Bing Places, Microsoft Ads and Webmaster Tools at bing.com/forbusiness, with a **Citations Builder that syncs business data across Bing, ChatGPT and the Microsoft ecosystem**; Bing is what ChatGPT uses for web answers ([MaaS 2026 guide](https://www.trymaas.com/blog/apple-business-connect-apple-maps-marketers-2026/), [Local Dominator Bing Places guide](https://localdominator.co/bing-places-for-business/), [Pluspoint](https://www.pluspoint.io/blog/enhancing-local-seo-with-apple-maps-and-bing-places)).
- **Edge:** as diners/guests shift to asking ChatGPT "best waterfront restaurant near X," Bing-sourced business data is the pipe. Ten minutes per property; near-zero competitor adoption locally.

### Apple Business Connect
- **Free** ([businessconnect.apple.com](https://businessconnect.apple.com/)); Apple Maps is the default on iPhone, and **ChatGPT's browsing references Apple Maps for local business info**; Siri/AI assistants surface Apple listings ([MaaS guide](https://www.trymaas.com/blog/apple-business-connect-apple-maps-marketers-2026/), [Neil Patel](https://neilpatel.com/blog/apple-business-connect/), [Uberall multi-location guide](https://uberall.com/en-us/resources/blog/apple-maps-business-listing)). Supports logos, cover photos, Showcases (offers).
- **Edge:** affluent iPhone-heavy hospitality demographic; every property should have a claimed, media-rich listing. Free impression/click analytics can feed the portal.

### Yelp Fusion API
- Metered self-serve API: **Starter $7.99 / Plus $9.99 / Enterprise $14.99 per 1,000 calls**, 30-day free trials, 300–500 calls/day quotas ([Yelp plan docs](https://docs.developer.yelp.com/docs/plans), [Yelp data pricing](https://business.yelp.com/data/resources/pricing/)); pricing shift angered developers in 2024 ([TechCrunch](https://techcrunch.com/2024/08/02/yelps-lack-of-transparency-around-api-charges-angers-developers/)).
- **Edge:** cheap programmatic pull of your + competitors' Yelp ratings/review counts into the portal (a few hundred calls/week ≈ dollars/month).

### TripAdvisor Content API
- **First 5,000 calls/month free**, then tiered pay-as-you-go; location details + up to 5 reviews/5 photos per location ([TripAdvisor Content API](https://developer-tripadvisor.com/content-api/), [FAQ](https://tripadvisor-content-api.readme.io/reference/faq)).
- **Edge:** free tier covers weekly rating/review-velocity tracking for every portfolio property *and* competitor set — hospitality's most trusted review source for travelers.

### Waze Ads
- Local pins from **$2 CPM, ~$60/mo minimum**; $200–500/mo test budget is meaningful for a single location; now folded into the Google ecosystem via Performance Max ([DataLatte Waze guide](https://datalatte.pro/blog/waze-ads-local-business-guide), [Promodo](https://www.promodo.com/blog/advertising-on-waze-everything-you-need-to-know), [ThePricer](https://www.thepricer.org/how-much-does-it-cost-to-advertise-on-waze/)).
- **Edge:** literal drive-by capture for the restaurants/brewpub/furniture store on Route-traffic corridors; a documented case drove a 57% lead increase for a local advertiser ([Search Engine Land case study](https://searchengineland.com/case-study-waze-local-ads-drove-a-57-increase-in-leads-to-local-auto-dealer-303117)). Cheap test, not a data source.

---

## 13. Ops Leading Indicators — the unifying layer

The strategic frame: **social and GA4 metrics are lagging or coincident; bookings-on-the-books are leading.** The portal should elevate a "pacing panel" per business:

| Business | Leading indicator | Source | Lead time |
|---|---|---|---|
| Restaurants | Covers on books next 14/30 days vs LY | OpenTable/Resy/SevenRooms exports ([Resy Analytics](https://helpdesk.resy.com/resy-analytics-BJdQMvX8_)) | 1–4 weeks |
| Hotel | Booking pace & window vs LY; RevPAR index | PMS + STR STAR ([Engine guide](https://engine.com/business-travel-guide/star-report-hotel)); optionally forward data via [Demand360](https://www.amadeus-hospitality.com/solutions/business-intelligence/demand360/) | 2–12 weeks |
| Marinas | Slip reservation pacing & lead flow vs plan | [Dockwa Insights](https://marinas.dockwa.com/business-insights) | 2–8 weeks |
| Vacation rentals | Occupancy pacing vs market | [Key Data](https://www.keydatadashboard.com/products/prodata) / [PriceLabs](https://hello.pricelabs.co/market-dashboards/) | 4–16 weeks |
| Weddings | Inquiries + tours booked | The Knot/Zola storefront metrics | 12–18 months |
| Golf | Rounds booked, utilization by daypart | [Lightspeed Golf API](https://partner-api.docs.chronogolf.com/) | 1–3 weeks |
| Ski real estate | Ikon pass momentum, snowfall, NH tourism trend | Public Vail/Alterra disclosures ([PeakRankings](https://www.peakrankings.com/content/epic-vs-ikon-vs-mountain-collective-vs-indy-2026-27)), NOAA, [Visit NH](https://www.visitnh.gov/industry-members/industry-resources/research) | 1–6 months |
| Builder | Permit volume in territory; new land sales | [Census BPS](https://www.census.gov/construction/bps/index.html), county registry/[ATTOM](https://www.attomdata.com/data/property-data/nationwide-building-permit-data/) | 3–12 months |

When pacing is soft with 3+ weeks of runway, marketing can act (offers, ads, email) *before* the soft week arrives — that is the structural advantage over competitors reading last month's Instagram reach.

---

## 14. Other Genuinely Differentiating Finds

### PredictHQ (event-impact intelligence)
- Verified event data across 18+ categories, ML-ready features claimed to improve forecasts ≥10%, Forecasts API up to +20% accuracy; hotels use it for event-driven occupancy pricing ([PredictHQ APIs](https://www.predicthq.com/apis), [products](https://www.predicthq.com/products), [dynamic pricing guide](https://www.predicthq.com/blog/the-definitive-guide-to-ai-powered-dynamic-pricing)). **Pricing:** custom/enterprise only ([Software Advice](https://www.softwareadvice.com/scm/predicthq-profile/)). For NH/Cape markets, a *free* substitute — manually curated calendars (Loon events, NASCAR at NHMS, Highland Games, bike week, town festivals) loaded into the portal — captures 80% of the value at 0% of the cost. Watchlist, don't buy.

### Ferries & access-route data (Cape properties)
- The **Steamship Authority** publishes schedules and live travel status ([schedules](https://www.steamshipauthority.com/schedules), [travel status](https://www.steamshipauthority.com/traveling_today/status)); the [Cape Cod Commission's ferry survey program](https://www.capecodcommission.org/about-us/newsroom/five-years-of-ferry-surveys-data-collection-to-preserve-critical-federal-funding/) (35,000 interviews) shows regional passenger-volume data exists publicly. Monthly SSA board reports include traffic statistics — a free proxy for island/Cape visitor flow. (Note: Three Suns *Captiva* is FL — the equivalent there is Lee County tourist development tax (bed-tax) receipts, published free monthly by the county.)

### School vacation calendars (free, decisive for New England hospitality)
- Massachusetts public schools take **February vacation (Presidents' Day week) and April vacation**; these weeks drive ski-country lodging demand ("book as far ahead as possible" for NH ski areas) ([Boston Discovery Guide](https://www.boston-discovery-guide.com/winter-break-in-boston.html), [Ask MetaFilter on ski-break geography](https://ask.metafilter.com/361179/Where-is-ski-break-February-break-a-thing), [New England Inns & Resorts](https://www.newenglandinnsandresorts.com/inspiration/the-blog/spring-skiing-in-new-england)). Load MA/CT/NY/NJ vacation calendars into the portal as demand-calendar overlays — NY's mid-winter break differs from MA's, effectively giving Loon *two* peak February weeks to price and staff differently.

### Zillow Research / Realtor.com free downloads (§9) and Census BPS (§9) — restated here because they are the rare *free, monthly, ZIP-level* datasets almost no local competitor operationalizes.

---

# TOP 10 RECOMMENDATIONS (impact vs. cost/effort)

| # | Integration | Cost | Effort | Primary beneficiary | Why it wins |
|---|---|---|---|---|---|
| 1 | **Google Hotel free booking links + Hotel Center reporting** | $0 (needs connected booking engine) | Low | Hotel | Direct bookings at 0% commission; "Official site" label; [15–25% of paid volume free](https://digitalfoxllc.com/blog/hotel-metasearch-vs-direct.html) |
| 2 | **Apple Business Connect + Bing/forbusiness (all properties)** | $0 | Low | All | Default-map iPhone visibility + [ChatGPT/AI answer plumbing](https://www.trymaas.com/blog/apple-business-connect-apple-maps-marketers-2026/); near-zero local adoption |
| 3 | **Dockwa Insights pacing feed** | Add-on, modest | Low | Marinas (+ dockside dining) | [Occupancy pacing, ADR, lead flow](https://marinas.dockwa.com/business-insights) — the waterfront's earliest demand signal |
| 4 | **Reservation pacing exports (Resy/OpenTable/SevenRooms) into portal** | $0 incremental | Medium | Restaurants | Covers-on-books vs LY beats every social metric as a decision trigger (§13) |
| 5 | **PriceLabs Market Dashboards (Lincoln NH + Captiva)** | [$9.99/dashboard/mo](https://hello.pricelabs.co/market-dashboards/) | Very low | Rentals | Cheapest daily STR market data anywhere |
| 6 | **Census Building Permits Survey + Zillow/Realtor.com free downloads** | $0 | Low-medium (ETL) | Builder, real estate, furniture | [Free monthly place-level permits](https://www.census.gov/construction/bps/index.html) + ZIP-level market hotness = lead-territory radar |
| 7 | **STR STAR report (monthly) for the hotel** | Low thousands/yr | Low | Hotel | [The benchmark](https://www.costar.com/products/str-benchmark) — RevPAR index is the one hotel KPI that proves marketing works |
| 8 | **AirDNA Professional (2 markets)** | [~$25–40/mo each](https://www.airdna.co/pricing) | Very low | Rentals, South Peak RE | Rate/occupancy comps + Rentalizer for acquisition pitches to owners |
| 9 | **TripAdvisor Content API (free tier) + Yelp Fusion (Starter)** | ~$0–20/mo | Medium (API build) | All hospitality | Automated own-vs-competitor rating/review-velocity tracking ([TripAdvisor](https://developer-tripadvisor.com/content-api/), [Yelp](https://docs.developer.yelp.com/docs/plans)) |
| 10 | **Demand-calendar layer: Visit NH data + school vacation calendars + Ikon/Epic pass trends + curated local events** | $0 | Medium (curation) | All NH businesses | Free leading demand context ([Visit NH](https://www.visitnh.gov/industry-members/industry-resources/research), [PeakRankings](https://www.peakrankings.com/content/epic-vs-ikon-vs-mountain-collective-vs-indy-2026-27)) that no local competitor systematizes |

**Honorable mentions (fund if budget remains):** Lighthouse Rate Insight for the hotel; Zola free listing + pay-per-lead for Harbor Lights (do the free listing regardless); TINT at ~$99/mo for portfolio-wide UGC rights; Lightspeed Golf API if/when the tee sheet moves there; a $200–500/mo Waze pin test for road-visible venues.

---

# SKIP THESE (for now) — and why

| Source | Reason to skip |
|---|---|
| **Placer.ai** | Real cost for a multi-location portfolio is [$12K–$50K+/yr](https://softwarefinder.com/analytics-software/placer-ai); insight is interesting but rarely actionable weekly at this scale. Revisit for a specific site-selection decision. |
| **Earnest/Consumer Edge, Bloomberg Second Measure, Affinity Solutions, Mastercard SpendingPulse (paid)** | Institutional/investor products with enterprise pricing; [built for hedge funds and national brands](https://secondmeasure.com/), not a regional operator. Free press summaries give the macro narrative. |
| **PredictHQ** | [Custom enterprise pricing](https://www.softwareadvice.com/scm/predicthq-profile/); a curated local-events calendar captures most value free. Watchlist for when the portal adds real forecasting models. |
| **Shovels.ai** | [$599/mo floor](https://docs.shovels.ai/docs/knowledge-base/getting-started/pricing-structure) and uncertain small-town NH jurisdiction coverage; free Census BPS + county registry work first. |
| **GolfNow barter deal** | The trade of 1–2 daily tee times can cost [~$100K+/yr in retail value](https://www.yourniceshot.com/blogs/news/is-golfnow-worth-it-for-your-golf-course-pros-cons-and-hidden-costs) and trains discount behavior. |
| **OpenTable third-party data egress** | [$250–$1,000 per location fees](https://thehustle.co/opentable-reservation-tech-sevenrooms) plus "system of record" lock-in terms; use native exports or choose an open system (SevenRooms/Resy). |
| **Amadeus Demand360** | Excellent data, but chain-oriented pricing is disproportionate for 29 rooms before STR/Lighthouse are exhausted. |
| **OnTheSnow/Mountain News partner API** | [Fee-based media/enterprise API](https://partner.docs.onthesnow.com/); NOAA snowfall (already in your weather stack) + Loon's public snow report page cover the need. |
| **Strava Metro (direct)** | [Free but restricted to qualified planning/nonprofit orgs](https://metro.strava.com/faq); pursue via town/trail-association partnership instead of direct application. |
| **AllTrails** | No business data product or API; consumer heatmaps only — use editorially. |
| **Snag-A-Slip as a data source** | Fine as a secondary listing channel, but analytics are thin vs. [Dockwa Insights](https://marinas.dockwa.com/business-insights); don't build portal plumbing on it. |
| **Paid influencer-discovery SaaS** | Meta's native [Creator Discovery/Partnership Ads Hub](https://www.marketingdive.com/news/meta-streamlines-brands-creator-partnerships-with-ai-powered-updates/807629/) now does discovery + performance free inside a stack you already run. |

---

## Sources consulted

1. https://www.placer.ai/pricing
2. https://softwarefinder.com/analytics-software/placer-ai
3. https://www.capterra.com/p/199858/Placer-ai/
4. https://www.oreateai.com/blog/understanding-the-cost-of-placerai-what-you-need-to-know/a4189949cff62b13a96c1ac5f2b2acbe
5. https://www.tontitown.com/wp-content/uploads/2026/05/8D.-Placer.ai-comparison.pdf
6. https://www.airdna.co/pricing
7. https://www.airdna.co/
8. https://www.bnbcalc.com/reviews/airdna-review-2026
9. https://learn.10xbnb.com/airdna-review/
10. https://awning.com/post/airdna-review
11. https://www.keydatadashboard.com/
12. https://www.keydatadashboard.com/products/prodata
13. https://www.hostfully.com/blog/str-business-intelligence-tools/
14. https://hello.pricelabs.co/market-dashboards/
15. https://help.pricelabs.co/portal/en/kb/articles/market-intel-dashboard
16. https://www.costar.com/products/str-benchmark
17. https://www.costar.com/products/str-benchmark/resources/faqs
18. https://www.costar.com/article/1969001935/what-the-2025-numbers-are-really-telling-us-about-boutique-hotels
19. https://engine.com/business-travel-guide/star-report-hotel
20. https://www.hospitalitynet.org/news/4127272.html
21. https://www.littlehotelier.com/blog/running-your-property/star-report/
22. https://chekin.com/en/blog/str-report-for-hotels/
23. https://www.mylighthouse.com/platform/pricing
24. https://www.mylighthouse.com/platform/rate-insight
25. https://hoteltechreport.com/revenue-management/market-intelligence-tools/lighthouse-rate-insight
26. https://www.d-edge.com/googles-free-booking-links-the-secret-weapon-for-hotels-in-the-battle-for-direct-bookings/
27. https://minihotel.io/blog/google-hotels-complete-guide/
28. https://digitalfoxllc.com/blog/hotel-metasearch-vs-direct.html
29. https://www.sojern.com/blog/google-eliminated-commission-bidding--heres-how-to-make-metasearch-work-for-your-hotel
30. https://apycue.com/blog/how-to-win-direct-bookings-on-google-hotel-metasearch
31. https://www.amadeus-hospitality.com/solutions/business-intelligence/demand360/
32. https://hoteltechreport.com/revenue-management/market-intelligence-tools/amadeus-demand360
33. https://marinas.dockwa.com/business-insights
34. https://marinas.dockwa.com/marina-software
35. https://marinas.dockwa.com/marina-software-pricing
36. https://www.capterra.com/p/147452/Dockwa/
37. https://www.snagaslip.com/snag-a-slip-for-marinas
38. https://www.snagaslip.com/frequently-asked-questions/
39. https://platform.opentable.com/documentation/
40. https://support.opentable.com/s/article/What-is-OpenTable-s-Consumer-API?language=en_US
41. https://www.restaurantbusinessonline.com/technology/opentable-will-require-restaurants-make-it-their-primary-reservations-system
42. https://thehustle.co/opentable-reservation-tech-sevenrooms
43. https://hospitalitytech.com/debate-who-owns-restaurants-data-heats-opentable-makes-changes
44. https://www.restaurantdive.com/news/opentable-blocks-data-sharing-with-competitors/550662/
45. https://sevenrooms.com/platform/integrations-apis/
46. https://resy.com/join/reservations/
47. https://helpdesk.resy.com/resy-analytics-BJdQMvX8_
48. https://business.yelp.com/resources/articles/online-restaurant-reservation-systems/?domain=restaurants
49. https://www.selecthub.com/restaurant-reservations-software/resy-os-vs-yelp-for-restaurants/
50. https://www.theknotww.com/press-releases/the-knot-worldwide-announces-new-platform-features-to-drive-wedding-vendor-success
51. https://www.businesswire.com/news/home/20240730891687/en/The-Knot-Worldwide-Announces-New-Platform-Features-to-Drive-Wedding-Vendor-Success
52. https://www.fullybookedvenue.com/the-ultimate-guide-to-the-knot-vendor-pricing/
53. https://www.fullybookedvenue.com/is-the-knot-worth-it-for-vendors/
54. https://curate.co/blog/the-knot-advertising-cost/
55. https://www.zachnicholz.com/blog/is-advertising-on-weddingwire-amp-theknot-worth-the-money-a-long-term-professional-review
56. https://www.zola.com/for-vendors
57. https://www.zola.com/faq/360002891772-what-does-it-cost-to-be-listed-on-zola-
58. https://johnsonjonesgroup.com/zola-vs-the-knot/
59. https://www.zola.com/expert-advice/zola-wedding-cost-index
60. https://www.golfnow.com/golfnow-business
61. https://www.teesnap.com/blog/the-golfnow-integration/
62. https://www.golfcoursetechnologyreviews.org/blog/trading-tee-times-for-tech-a-deep-dive-into-golfnows-barter-model-with-paul-sampliner
63. https://www.yourniceshot.com/blogs/news/is-golfnow-worth-it-for-your-golf-course-pros-cons-and-hidden-costs
64. https://growthgcc.com/blog/the-golfnow-trap--take-back-control-of-your-club
65. https://easyteegolf.com/articles/is-golfnow-worth-it/
66. https://partner-api.docs.chronogolf.com/
67. https://www.lightspeedhq.com/golf/
68. https://www.capterra.com/p/151997/Chronogolf/
69. https://www.ikonpass.com/en/destinations/loon-mountain
70. https://www.loonmtn.com/season-passes/ikon-pass
71. https://www.peakrankings.com/content/epic-vs-ikon-vs-mountain-collective-vs-indy-2026-27
72. https://www.vaildaily.com/news/ikon-pass-2025-26-launch-price-sale/
73. https://www.deseret.com/lifestyle/2026/04/06/vail-alterra-ski-resort-lawsuit-lift-ticket-ikon-epic-season-pass-prices/
74. https://partner.docs.onthesnow.com/
75. https://partner.docs.onthesnow.com/api-reference/ski-resort-snowreport-api
76. https://www.mountainnews.com/data-ai/
77. https://snowproportal.com/updates/on-the-snow-blocks-public-api
78. https://skiapi.com/
79. https://metro.strava.com/
80. https://metro.strava.com/faq
81. https://metro.strava.com/case-studies/whats-new-with-strava-metro
82. https://stories.strava.com/articles/introducing-strava-metro-for-academic-researchers
83. https://www.techradar.com/features/strava-vs-alltrails-how-do-the-activity-apps-compare
84. https://www.visitnh.gov/industry-members/industry-resources/research
85. https://www.visitnh.gov/industry-members/industry-resources/research/travel-impacts
86. https://www.visitnh.gov/getmedia/273430b3-c2f5-4b1b-9038-a3414a0a912c/New-Hampshire-Travel-Trends-June-2025.pdf
87. https://www.collaborativenh.org/granite-solutions-coronavirus-1/2025/11/24/tourism-in-new-hampshire-where-does-it-stand-in-wake-of-the-falloff-in-number-of-canadian-visitors
88. https://www.bostonglobe.com/2025/05/22/metro/nh-summer-travel-canada-tourists-expectations-tourism/
89. https://mm.nh.gov/files/uploads/nhes/documents/vs25-ch10-trade-tourism.pdf
90. https://www.zillow.com/research/data/
91. https://www.zillowgroup.com/developers/public-data/
92. https://www.realtyapi.io/blog/how-to-get-property-data-from-zillow-using-an-api-2026-guide
93. https://libguides.gwu.edu/c.php?g=1454849&p=11272938
94. https://www.attomdata.com/solutions/property-data-api/
95. https://www.attomdata.com/data/property-data/nationwide-building-permit-data/
96. https://api.developer.attomdata.com/docs
97. https://www.oreateai.com/blog/navigating-attom-data-api-pricing-what-to-expect-for-2025/6b2a14a54029154bd57b762132d25bee
98. https://datarade.ai/data-providers/attom/profile
99. https://www.census.gov/construction/bps/index.html
100. https://www.census.gov/construction/bps/about.html
101. https://www.census.gov/construction/bps/schedule.html
102. https://hudgis-hud.opendata.arcgis.com/datasets/HUD::residential-construction-permits-by-county/about
103. https://www.shovels.ai/
104. https://docs.shovels.ai/docs/knowledge-base/getting-started/pricing-structure
105. https://permit-stack.com/blog/building-permit-data-api-pricing-compared.html
106. https://secondmeasure.com/
107. https://www.bloomberg.com/professional/insights/data/data-spotlight-transactions-fundamentals-more/
108. https://www.earnestanalytics.com/data-for-companies
109. https://pages.earnestanalytics.com/earnest-credit-card-data
110. https://www.affinity.solutions/our-data/
111. https://datarade.ai/data-providers/affinity-solutions/profile
112. https://www.mastercard.com/us/en/business/insights-intelligence/economic-market-insights/solutions/spendingpulse.html
113. https://www.mastercard.com/us/en/business/insights-intelligence/economic-market-insights/solutions/spendingpulse/travel-and-hospitality.html
114. https://aws.amazon.com/marketplace/pp/prodview-q27tc3dgqlhew
115. https://www.mastercard.com/us/en/business/industry-segment/small-medium-business/small-business-navigator/spendingpulse-reports.html
116. https://www.influencer-hero.com/blogs/best-user-generated-content-ugc-platforms---features-review-pricing
117. https://www.capterra.com/p/178705/TINT/
118. https://www.g2.com/products/tint/reviews
119. https://getflowbox.com/
120. https://getflowbox.com/blog/ugc-platforms/
121. https://www.gartner.com/reviews/product/flowbox-ugc-platform
122. https://www.marketingdive.com/news/meta-streamlines-brands-creator-partnerships-with-ai-powered-updates/807629/
123. https://help.instagram.com/116947042301556
124. https://strikesocial.com/blog/instagram-partnership-ads-branded-content-ads/
125. https://www.aspire.io/blog/instagram-branded-content-101
126. https://www.sticki.com.au/post/instagram-collab-ads-what-are-they-and-how-brands-creators-can-win-with-this-ad-type
127. https://www.trymaas.com/blog/apple-business-connect-apple-maps-marketers-2026/
128. https://businessconnect.apple.com/
129. https://neilpatel.com/blog/apple-business-connect/
130. https://uberall.com/en-us/resources/blog/apple-maps-business-listing
131. https://localdominator.co/bing-places-for-business/
132. https://www.pluspoint.io/blog/enhancing-local-seo-with-apple-maps-and-bing-places
133. https://docs.developer.yelp.com/docs/plans
134. https://business.yelp.com/data/resources/pricing/
135. https://techcrunch.com/2024/08/02/yelps-lack-of-transparency-around-api-charges-angers-developers/
136. https://developer-tripadvisor.com/content-api/
137. https://tripadvisor-content-api.readme.io/reference/faq
138. https://datalatte.pro/blog/waze-ads-local-business-guide
139. https://www.promodo.com/blog/advertising-on-waze-everything-you-need-to-know
140. https://www.thepricer.org/how-much-does-it-cost-to-advertise-on-waze/
141. https://searchengineland.com/case-study-waze-local-ads-drove-a-57-increase-in-leads-to-local-auto-dealer-303117
142. https://www.predicthq.com/apis
143. https://www.predicthq.com/products
144. https://www.predicthq.com/blog/the-definitive-guide-to-ai-powered-dynamic-pricing
145. https://www.softwareadvice.com/scm/predicthq-profile/
146. https://www.steamshipauthority.com/schedules
147. https://www.steamshipauthority.com/traveling_today/status
148. https://www.capecodcommission.org/about-us/newsroom/five-years-of-ferry-surveys-data-collection-to-preserve-critical-federal-funding/
149. https://www.boston-discovery-guide.com/winter-break-in-boston.html
150. https://ask.metafilter.com/361179/Where-is-ski-break-February-break-a-thing
151. https://www.newenglandinnsandresorts.com/inspiration/the-blog/spring-skiing-in-new-england
