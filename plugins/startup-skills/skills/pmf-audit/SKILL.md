---
name: pmf-audit
description: >
  (startup-skills) Use when the founder has an active product with real users and needs to measure product-market fit. Fires on "do I have PMF," "Sean Ellis survey," "should I scale," or "fundraising readiness." Implements the Sean Ellis 40% Rule and Vohra's Superhuman blueprint. Refuses to authorize scaling or paid acquisition below the 40% threshold.
---

# PMF Audit

The full Sean Ellis 40% Rule implementation plus Rahul Vohra's Superhuman blueprint applied to the founder's own data. Refuses scaling and paid acquisition until the 40% threshold is met. Re-runs quarterly. Distinguishes leading indicator (Ellis) from lagging indicator (Andreessen-style organic pull).

## When to Activate

- Founder has an active product with users who have experienced core value (used ≥2x in last 14 days).
- Phrases: "do I have PMF," "Sean Ellis survey," "is this PMF," "40% rule," "should I scale," "should I fundraise now," "I have users but…", "fundraising readiness."
- Auto-fire from `signal-audit` when post-launch and the founder asks about scaling.

If the founder has no deployed product or no qualifying users yet, route back to `signal-audit` (which handles pre-product evidence) or `discovery-coach` (more interviews).

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — especially surveying the wrong cohort, building for "Not Disappointed" cohort, fundraising before 40%.
- `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md` — full Sean Ellis + Vohra workflow.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Superhuman 22% → 58% case.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Vohra First Round Review, Ellis posts, Andreessen.

## State Document Protocol

Read `STARTUP-STATE.md`. Confirm there is an active product with qualifying users. Update PMF Running Score (Sean Ellis fields) and Competitive Landscape (HXC segment definition). Session Log: `- [YYYY-MM-DD] pmf-audit — Sean Ellis score <X>%, HXC: <Y>, recommendation: <scale/iterate/freeze>`.

## Process

1. **Read state. Confirm prerequisites.** There must be a product with ≥40 active users who have used it 2+ times in the last 14 days. If not, stop and route: `signal-audit` for pre-product evidence; `discovery-coach` for more interviews.

2. **If the user hasn't run the Sean Ellis survey:**
   - Design the survey per `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md`. Core question, four options, the active-user filter.
   - Recommend tools: Tally (free) or Typeform for external delivery; Userpilot or Intercom for in-app.
   - Sample size: 40+ valid responses minimum; aim for 100+.
   - Help the founder write the email sending users to the survey — short, founder-personal, single button.
   - Set the timeline: 1–2 weeks to collect; one reminder at day 7.
   - Stop here. Resume when results arrive.

3. **When results are in, compute the score.**
   - PMF Score = (Very Disappointed / Total Valid) × 100.
   - **≥ 40%:** significant. Leading-indicator threshold met. Authorize scaling experiments. Recommend continuing the survey quarterly.
   - **< 40%:** the system FREEZES scaling and paid acquisition. State directly: "Below 40%. Scaling and paid acquisition are off the table until we lift this. We're returning to Build-Measure-Learn."

4. **Apply Vohra's Superhuman blueprint** per `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md`.
   - **Segment to the HXC.** Cross-tabulate "Very Disappointed" cohort by role, company size, industry, use frequency, geography. Find the segment with the highest internal "Very Disappointed" %. That's the High-Expectation Customer. Write the HXC definition into `STARTUP-STATE.md` Competitive Landscape under "HXC."
   - **Analyze polarity.** Ask the "Very Disappointed" cohort the open-ended follow-up: "What is the main benefit you receive?" Aggregate the verbatim answers. The dominant theme is the core value prop. Superhuman's was speed; the founder's might be different. Write the theme into `STARTUP-STATE.md` One-Liner (Current).
   - **Convert fence-sitters.** Ask the "Somewhat Disappointed" cohort: "What is holding you back from loving this?" Aggregate. The dominant themes become the next product roadmap.
   - **Ignore the rest.** "Not Disappointed" feedback is discarded. State this directly: "Don't build for the Not-Disappointed cohort — it dilutes the product."
   - **50/50 split.** 50% engineering on expanding HXC value; 50% on converting fence-sitters. Apply this split until the next quarterly re-run.

5. **Surface the Andreessen lagging-indicator complement** per `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md`. Look for: support overwhelmed, organic word-of-mouth, peer-to-peer referrals, servers melting. If the Ellis score is high but these are absent after 6+ months, examine the HXC's TAM — the cohort may be too small to produce company-level signal.

6. **Pre-mortem prompt at every full audit** (per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` structural override). "Imagine it's 12 months from now and the company has stalled at this PMF score. Write the autopsy. What was the cause? What evidence would have predicted it?" Use the answer to refine the HXC or the polarity analysis.

7. **Bias sentinel pass.** Especially:
   - **Surveying the wrong cohort.** Including inactive users suppresses the score. Including signups who never experienced value suppresses it. Re-filter if necessary.
   - **Building for "Not Disappointed."** The founder will feel guilty about "ignoring" them. Refuse — this is the single most expensive mistake post-PMF.
   - **Fundraising before 40%.** If the founder asks about a seed or Series A while the score is below 40%, name the gap. Fundraising on a pre-PMF score is selling speculation; serious investors run their own variant of this survey.

8. **Update state.**
   - PMF Running Score: Sean Ellis percentage, sample size, HXC definition, dominant value-prop theme, fence-sitter top 3 objections.
   - Current Decision Point: based on stage.
   - One-Liner: updated to lead with the value-prop theme from polarity analysis.

9. **Recommend next.**
   - **≥ 40%:** `outreach-engine` (now you can scale acquisition). Or `artifact-builder` for fundraising materials, which the system will now produce (vs refuse).
   - **< 40%:** `discovery-coach` (more interviews on fence-sitter objections) AND `rapid-experiments` (test fence-sitter-objection fixes before building them). Return to `pmf-audit` next quarter.
   - **Score declining quarter-over-quarter:** route to `pivot-decision`.

## Outputs

- Writes to state: PMF Running Score (Sean Ellis fields fully populated), HXC definition, value-prop theme, fence-sitter objections.
- External resources to surface:
  - Rahul Vohra, *How Superhuman Built an Engine to Find Product/Market Fit* (First Round Review).
  - Sean Ellis's original 40% Rule posts.
  - Marc Andreessen, *The Only Thing That Matters*.
  - Brian Balfour's PMF essays.
- **Artifacts on request only:** Sean Ellis survey template; custom HXC analysis based on the founder's actual survey results; PMF Status Report (markdown) suitable for cofounders, advisors, or investors. Offer once each at the relevant moment.

## Anti-Patterns Prevented

- Surveying all users including inactives.
- Treating "Somewhat Disappointed" as good signal.
- Building for "Not Disappointed."
- Fundraising before 40%.
- Scaling paid acquisition before 40%.
- One-time PMF measurement (the discipline is quarterly).
- Treating Andreessen-style qualitative as a substitute for the Ellis score (or vice versa — both matter).

## Recommended Next Skills

Per step 9. State explicitly.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Sharp at the freeze decision (the score is below 40% and the founder wants to scale anyway). Vohra's blueprint is operational; treat it as the engine, not a one-time event.
