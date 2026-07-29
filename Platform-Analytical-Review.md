# Waterside Portal — Analytical Top-to-Bottom Review (v11 → v12)

**July 28, 2026.** Every view audited against six questions an owner asks, plus browsability, card story order, segment fit, and actionability. Findings, then what changed.

---

## The test applied to every page

1. How are we doing? 2. What's working? 3. What needs attention? 4. Any urgent tasks? 5. Is our team performing? 6. What content is resonating?

| View | 1 | 2 | 3 | 4 | 5 | 6 | Verdict before v12 |
|---|---|---|---|---|---|---|---|
| Scorecard | ✅ | partial | ✅ | ✅ | ❌ | ❌ | Strong on status, silent on team and content |
| Socials | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | Metrics without consequences |
| Paid Socials | ✅ | ✅ | ✅ | partial | ❌ | partial | Flags exist but don't become tasks |
| Website | ✅ | partial | ✅ | ❌ | ❌ | ✅ | Issue list isn't assignable |
| Reviews | ✅ | ✅ | ✅ | partial | partial | ❌ | Closest to complete |
| Competitors | partial | ✅ | ✅ | ❌ | ❌ | ✅ | No "so what do we do" |
| Revenue | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | Opportunity gaps never become work |
| Customers | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | Demographics with no decisions |
| Insights | partial | ✅ | ✅ | ✅ | ❌ | ✅ | Best actionability, weakest situational awareness |

**The two systemic gaps: nothing answered "is our team performing," and findings across seven views never became assignable work.** Every view had its own private list of problems that died on the page.

---

## Findings and fixes

**1. No page answered all six questions; each answered two or three.** *Fix:* every business view now opens with a **six-question strip** — six compact answers with status colors, each linking to the section that proves it. The strip is the same on every page, so the owner learns one pattern and reads any view in five seconds.

**2. Team performance was invisible.** Publishing cadence existed only inside the portfolio exception table; review response time only inside Reviews; task completion nowhere. *Fix:* a **Team performance** section on every business scorecard — publishing vs. that segment's plan, review response rate and median hours, task completion rate, content output, and SLA breaches, each with a target and a status.

**3. Cards were grouped by data source, not by story.** *Fix:* every view is reordered **verdict → what's working → what needs attention → what to do → detail**. Wins and problems are now separate, labeled blocks rather than a uniform grid the reader has to interpret.

**4. Metrics didn't match the business.** Every segment showed the same funnel labels; a marina and a restaurant were measured identically. *Fix:* segment-specific KPI sets — dining shows covers, reservations, and calls; hospitality shows bookings, inquiries, and length-of-stay signals; real estate shows qualified leads and consultations; marine shows service inquiries, slip demand, and boat-sales leads; retail shows transactions and basket size. Benchmarks and the outcome noun follow the segment everywhere, including the leaderboard and exception table.

**5. Actions were scattered and unowned.** Seven views produced findings; only two produced tasks. *Fix:* a **single task queue** fed by every view — review backlogs, campaign pacing, stale content, revenue gaps, competitor cadence, and intelligence tasks all land in one list with owner, due date, expected impact, and status. Each business scorecard shows its own slice; the portfolio Scorecard shows the cross-business queue.

**6. The platform had no memory and no outside knowledge.** It reported our own numbers back to us. *Fix:* the **Marketing Intelligence** layer (below).

**7. Browsability.** Nine tabs with no hierarchy; long pages with no anchors. *Fix:* the question strip doubles as in-page navigation, sections have consistent headers, and detail moved behind disclosures so every page opens at one screen.

---

## Marketing Intelligence layer (new)

A cumulative feed that learns daily from Search Engine Land, Search Engine Journal, Moz, Semrush, Google Search Central and its news feed, Pew Research, Nielsen, and Google Trends. Each item is stored as a structured card:

**Finding** (with the number) → **What it means for this business** → **Task** (imperative, assignable) → **Source + date** → **Segments it applies to**.

Cards are filtered to the selected business's segment, so a builder never reads restaurant advice. Tasks flow into the same queue as everything else. The feed is cumulative: items persist with their date, so the portal accrues an institutional record of why decisions were made — and the intelligence section shows what changed in the last 30 days alongside what it means for us.

Seeded with verified findings from this project's research (each carries its source and date): the March and May 2026 core updates, Google's Generative AI report in Search Console, GA4's AI Assistant channel, April 2026 review-solicitation policy, FAQ rich-result retirement, the impressions-to-views change at Meta, Instagram Competitive Insights, the "great decoupling" of impressions from clicks, AI-citation click lift, local ranking weights, per-platform engagement medians, retention-to-reach effects, Stories drop-off patterns, carousel performance, and email benchmark shifts after Apple's privacy changes.

**Production ingestion:** a daily job pulls the RSS/news feeds of those sources, an LLM classifies each item by segment relevance and converts it to the card format, and a human approves before it appears. The framework and endpoints are in the developer integration guide.

---

## What did not change, deliberately

Data-integrity work from v6 stays: truthful source statuses, real YTD, funnel stages kept in their own units, per-objective paid costs, estimated-review labeling, and portfolio rollup gating. Nothing in this pass makes a number look more certain than it is.
