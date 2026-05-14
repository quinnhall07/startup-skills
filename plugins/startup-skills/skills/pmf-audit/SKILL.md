---
name: pmf-audit
description: |
  Full Sean Ellis 40% Rule + Rahul Vohra's Superhuman blueprint applied to the founder's actual data. Refuses scaling and paid acquisition until 40% threshold met. Re-runs quarterly. Distinguishes leading indicator (Ellis) from lagging indicator (Andreessen). Adds Casey Winters retention curves, Andrew Chen power user curve, Brian Balfour Four Fits, AI-product PMF specifics.

  TRIGGER when: founder has active product with ≥40 active users (used ≥2x in last 14 days); user says "do I have PMF", "Sean Ellis survey", "is this PMF", "40% rule", "should I scale", "should I fundraise now", "I have users but...", "fundraising readiness"; auto-fire from `signal-audit` when post-launch and founder asks about scaling.

  SKIP: founder has no deployed product OR <40 active users (route to `signal-audit` for pre-product evidence, or `discovery-coach` for more interviews); founder is at survey-design stage and hasn't sent yet (this skill walks through); founder is in chronic pre-signal (route to `pivot-decision`).
---

# PMF Audit

The full Sean Ellis 40% Rule implementation plus Rahul Vohra's Superhuman blueprint applied to the founder's own data. Refuses scaling and paid acquisition until the 40% threshold is met. Re-runs quarterly. Distinguishes leading indicator (Ellis) from lagging indicator (Andreessen-style organic pull).

## HARD-GATE — prerequisites for this skill to fire:

- [ ] Active product with ≥40 active users (used ≥2x in last 14 days). If not, route to `signal-audit` or `discovery-coach`.
- [ ] User base allows ≥100 valid survey responses. If <40 users in active cohort, surveys are too noisy.

**Frozen decisions until ≥40% Sean Ellis** (non-negotiable, cite Vohra):
- Paid acquisition: FROZEN.
- Sales hiring: FROZEN.
- Major scaling investments: FROZEN.
- Fundraising on pre-PMF score: FROZEN — selling speculation.

If founder pushes back: "Below 40%. Scaling and paid acquisition are off the table until we lift this. Returning to Build-Measure-Learn. The fastest path: `discovery-coach` (DEBRIEF) on the fence-sitter cohort + `rapid-experiments` to test the fence-sitter objection fixes."

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
- `${CLAUDE_PLUGIN_ROOT}/references/retention-metrics.md` — cohort curves, smile vs frown, AI-era retention
- `${CLAUDE_PLUGIN_ROOT}/references/growth-loops.md` — Four Fits, NRR, CAC payback
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — model-market-fit failure mode, token economics
- `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md` — kill criteria, MAP, pre-mortem
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

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

2b. **Email template to users (copy-paste-ready):**

   > Subject: Quick 2-question survey?
   >
   > Hey [name],
   >
   > Quick favor — I'm trying to understand which users get the most value from [product]. Just one core question: How would you feel if you could no longer use [product]?
   > A) Very disappointed
   > B) Somewhat disappointed
   > C) Not disappointed (it isn't really useful)
   >
   > [Link to 60-second survey]
   >
   > Means a lot. Thanks.
   > [Founder name]

   Tools: Tally (free) or Typeform external; Userpilot or Intercom in-app (best response rates).

3. **When results are in, compute the score.**
   - PMF Score = (Very Disappointed / Total Valid) × 100.
   - **≥ 40%:** significant. Leading-indicator threshold met. Authorize scaling experiments. Recommend continuing the survey quarterly.
   - **< 40%:** the system FREEZES scaling and paid acquisition. State directly: "Below 40%. Scaling and paid acquisition are off the table until we lift this. We're returning to Build-Measure-Learn."

4. **Apply Vohra's Superhuman blueprint** per `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md`.

   **Segment to the HXC.** Cross-tabulate "Very Disappointed" cohort by:
   - Role / job title.
   - Company size.
   - Industry.
   - Use frequency / depth.
   - Geography.

   For each segment slice, compute internal "Very Disappointed %". HXC = the slice with the **highest internal %**. Example: if total VD = 33%, but slicing reveals "CTOs at Series B startups in fintech" are 60% VD internally, that's the HXC. Re-score Q1 against HXC-matching respondents only — score often jumps materially.

   Write the HXC definition to `STARTUP-STATE.md` Competitive Landscape under "HXC."

   **Analyze polarity.** Run Q3 ("What's the main benefit?") word/theme analysis on VD cohort. The dominant theme = your core value prop. Update `STARTUP-STATE.md` One-Liner with this theme leading.

   **Convert fence-sitters.** Run Q4 ("What's holding you back?") on Somewhat Disappointed cohort. Top 3 objections = next roadmap.

   **Ignore the rest.** Not Disappointed feedback gets discarded.

   **50/50 split**: 50% engineering on expanding HXC value, 50% on converting fence-sitters.

4b. **Cohort retention + Power User Curve check** per `${CLAUDE_PLUGIN_ROOT}/references/retention-metrics.md`:
   - **Cohort retention curve**: flat by month 3 = real PMF. Decay continuing past month 3 = no PMF regardless of Sean Ellis score.
   - **L7/L28 histogram** (Andrew Chen): smile = real PMF; frown = no PMF.
   - **Anti-PMF signals table** (per `retention-metrics.md`): check against narrative-as-explanation, busy-as-churn-reason, champion-dependency, lengthening cycles, intensifying pricing pushback.

   If Ellis is high but retention shows frown curve: HXC may be too narrow OR top-of-funnel novelty is inflating Ellis. Re-segment.

4c. **AI-product PMF specifics** (only if AI-product) per `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md`:
   - **LTV / inference-cost ratio ≥ 3x**. If a power user's annual COGS exceeds 1/3 of ARR, unit economics collapse at scale.
   - **Margin per active user trend**: should improve with cohort age. Flat or declining = no real moat.
   - **Model-Market-Fit check**: D28 cohort retention <30% (B2B) or <15% (consumer) = model-market-fit (people want to try AI), not PMF (people use YOUR product).
   - **AI-substitution test**: Is your core JTBD now achievable in ChatGPT/Claude in <30s? If yes, you're on the PMF Treadmill — re-segment to HXC for whom your differentiation still holds, OR pivot.

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
   - **≥ 40% AND retention is flat by month 3**: `outreach-engine` (now you can scale acquisition). `positioning-narrative` if not yet committed (positioning drives scaling). `artifact-builder` for fundraising materials (which the system will now produce vs refuse).
   - **< 40%**: `discovery-coach` (DEBRIEF) for more interviews on fence-sitter objections, AND `rapid-experiments` for behavioral tests on fence-sitter-objection fixes. Return to `pmf-audit` next quarter.
   - **Score declining 2+ quarters**: invoke `pivot-decision` immediately. Don't soften.
   - **Score high but retention frown curve**: HXC re-segmentation OR `pivot-decision` if HXC is structurally too small. Load `${CLAUDE_PLUGIN_ROOT}/references/retention-metrics.md`.
   - **Token-cost economics breaking** (AI-product): `pricing-model` to migrate to outcome-based or hybrid.

## Red flags

| Founder behavior | Response |
|---|---|
| Survey all users including inactives | Suppresses score. Re-filter. |
| Treats Somewhat Disappointed as good signal | Build for fence-sitters who cite YOUR value prop only. Ignore generic SD. |
| Builds for Not Disappointed cohort | Refuse. The most expensive mistake post-PMF. |
| Fundraises below 40% | Refuse. Pre-PMF score = selling speculation. |
| Wants to scale paid acquisition below 40% | Frozen. Cite Vohra. |
| Treats one-time PMF measurement as final | Re-run quarterly. PMF is a running score, not a finish line. |
| Skips retention curve check, declares PMF on Ellis alone | Force the cohort retention + L7/L28 check. Ellis without retention is fragile. |
| AI-product Ellis high but D28 retention <30% | Model-market-fit, not PMF. Surface AI-substitution test. |
| Twitter screenshots as evidence | Demand cohort data. Vibes ≠ retention. |

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
