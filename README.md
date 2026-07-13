# Waterside Group — Marketing Performance Portal (Prototype)

An owner-and-team marketing decision portal for the Waterside Group portfolio (20 brands + affiliates). **All values are sample data** — every metric carries a source-status chip, and nothing here should drive a decision until its source reads LIVE.

## Run it

Open `waterside-dashboard.html` in any browser. No build step, no server. Mobile-friendly. Styled to watersidegroup.com's design system (Nord type resolves when hosted on the site; Jost fallback otherwise).

## What's inside

| View | What it answers |
|---|---|
| Scorecard (Portfolio) | "Where do I need to pay attention today?" — pulse, company exception table, top five decisions, portfolio opportunities |
| Scorecard (Brand) | Funnel: Seen → Visited → Intent → Outcomes, insights, channel scoreboard |
| Channels | Instagram, TikTok, Facebook, YouTube, Email, Website, Blog, Search & AI, Local & Reviews, Mentions |
| Competitors | Up to 5 researched, named competitors per brand from public data |
| Paid Campaigns | Per-objective costs, pacing, creative fatigue, ending-soon flags |
| Revenue Centers | Real-time sales (Toast) / monthly P&L, Demand-vs-Revenue opportunity scoring, AI-suggested new centers |
| Demographics | Age/gender/geo/device, social vs email audience |
| Insights & Advice | 3×3 summary, benchmark gaps (shown only where they matter), monthly content plan, scored actions, sourced industry news |

## Documents

- `Waterside-Marketing-Dashboard-Spec-v2.md` — full build spec: metrics, formulas (incl. Revenue Center Opportunity Score), integrations, rollout
- `Developer-Integration-Guide.md` — third-party API connections, auth, quotas, P&L import contract, new-brand checklist
- `Portal-Critical-Review.md` — design-review findings and fixes
- `research/` — five research briefs, 850+ cited sources total

## Known prototype limitations

Date-range and comparison selectors regenerate deterministic sample data (volumes scale correctly with range). Config edits are session-only. Insight text is illustrative — production attaches evidence rows. See the on-screen banner and Data Status panel.
