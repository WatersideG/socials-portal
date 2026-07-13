# Waterside Marketing Portal — Critical Review & v3 Changes

**July 12, 2026.** Top-to-bottom review of the v2 portal against current dashboard guidance (Nielsen Norman Group usability research, Stephen Few, Storytelling with Data, Google's data-viz principles, and the SEJ/SEL executive-reporting consensus — full citations in `research/campaigns-ux.md` and `research/seo-publications.md`). Each finding lists the problem, the guidance it violates, and the fix shipped in v3.

---

## The core critique

v2 was information-complete but story-thin. It answered "what are all the numbers?" when the owner's question is "are more people finding us, are they acting, what changed, and what are we doing about it?" The redesign reorganizes every screen around that sentence.

---

## Findings and fixes

**1. The executive view showed 10 KPI cards. Guidance: 3–5 for an owner view.**
Ten cards means nothing is the headline; NN/g eye-tracking shows scanning stops after the first row. *Fix:* four hero numbers that tell the whole story in order — People finding us → Visits → Actions taken → Reputation. Everything else (health score, email revenue, AI share of voice, audience, branded search) moved behind a "More measures" disclosure. The scoreboard table also collapsed behind a click (progressive disclosure).

**2. KPI cards had no trend context.**
A number with a delta but no shape hides direction changes. *Fix:* every hero card carries a 12-week sparkline, delta with its baseline named in words, and a status word — the Few/Knaflic card pattern.

**3. Chart titles named topics, not takeaways.**
"Engagement & traffic trend" makes the reader do the analysis. *Fix:* titles now state the finding ("More people are seeing us than clicking — that's the new normal") and every chart carries a one-line caption saying why it moved and what we're doing.

**4. The paid table had 13 columns; several were diagnostics, not decisions.**
Wide tables fail the 5-second rule and bury the two real questions: is spend on track, and is it working. *Fix:* consolidated to nine columns with a single **Health** column combining pacing, creative fatigue, and ending-soon flags as worded pills. CPC/CPM and relevance diagnostics appear only as exception flags, per Meta's own guidance that they're diagnostics, not KPIs.

**5. The AI view mixed insights, actions, and news without hierarchy.**
The SEJ/SEL executive-reporting consensus is a fixed ritual: **3 highlights, 3 lowlights, 3 next steps.** *Fix:* the view now opens with exactly that, in plain language, before the scored action queue and the news feed.

**6. One metric card rendered a delta as its value (branded search).** Bug. *Fix:* corrected to a proper value + delta card under More measures.

**7. Precision inconsistency.**
Two-decimal percentages on large numbers imply false accuracy (Few: match precision to decision). *Fix:* sub-1% rates keep two decimals (they need them); everything above 10% rounds to whole numbers.

**8. Contrast and color discipline.**
Steel blue (#6E8CAD) fails WCAG contrast for small text on white. *Fix:* steel blue is reserved for accents, borders, and large elements; all reading text is navy (#13416C) or charcoal (#4C4D47). Red/amber/green appear only as status pills, always paired with a word — never color alone (colorblind-safe).

**9. Visual identity didn't match the site it will live on.**
*Fix:* restyled to watersidegroup.com's extracted design system — Nord-Book/Nord-Medium type (Jost fallback, loaded from Google Fonts; Nord resolves automatically when the portal is hosted on the site), navy #13416C headings, steel #6E8CAD accents, warm-charcoal body text, white surfaces, square corners, and the site's outlined uppercase button style (12px, 700, 3px letter-spacing) for controls and tabs.

**10. The verdict was present but visually secondary.** *Fix:* the TL;DR is now the first element on every view that has one, restyled as the brand-navy panel, and always ends with the next move.

**Kept from v2 (already aligned with guidance):** weekday-aligned YoY as the default comparison with baselines named in words; the visibility/clicks decoupling shown as two lines with a plain-English caption; competitor strips with a one-line competitive read; the algorithm-weather annotation strip; evidence attached to every AI insight; attribution honesty footnotes; data-freshness timestamp.

---

## What still needs real data to matter

Sample data can't show: real anomalies worth explaining, actual competitor gaps, true campaign pacing, or genuine AI-citation counts. The layout is now built so that when live feeds land (Phase 1–2 of the spec), every element already has a place and a voice. The three unconfirmed competitor sets (Little Blue, Coffee Cart, Shop at South Peak) remain flagged in-product.
