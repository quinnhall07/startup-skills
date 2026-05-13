---
name: pivot-decision
description: >
  (startup-skills) Use every 4-6 weeks during active building, or whenever the founder is stuck or doubting direction. Fires on "should I pivot," "this isn't working," "I've been at this for months," or "considering changing direction." Runs Dalton's opportunity cost calculation and a Klein-style pre-mortem. Aggressively counters sunk cost. Generates 3-5 scored pivot candidates if a pivot is recommended.
---

# Pivot Decision

The structured decision gate for "continue / adjust / pivot." Reads the full state document, computes Dalton's opportunity cost, runs Klein's pre-mortem, and aggressively counters sunk cost. When pivot is recommended, generates 3–5 candidates rooted in what the founder has *already learned*.

## When to Activate

- Phrases: "should I pivot," "stuck," "this isn't working," "I've been at this for months," "maybe I should try something different," "considering changing direction," "should I quit."
- Routine: every 4–6 weeks during active building, even when not stuck. The cadence prevents drift.
- Auto-fire from `signal-audit` when the founder has been at pre-signal stage for 3+ months.
- Auto-fire from `pmf-audit` when the Sean Ellis score is declining quarter-over-quarter.

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — sunk cost (most load-bearing here), loss aversion, optimism bias, chronic pivoting.
- `references/scoring-rubrics.md` — Dalton's 4-criteria rubric for pivot candidates.
- `references/case-studies.md` — Slack (Glitch → enterprise chat), Brex (VR → corporate cards), Segment (classroom → analytics), Magic (concierge → AI assistants).
- `references/external-resources.md` — Dalton's *All About Pivoting*, Eric Ries pivot chapter.

## State Document Protocol

Read entire `STARTUP-STATE.md` — every section, not just recent updates. Update Current Decision Point and (if pivot) the One-Liner with the new candidate. Session Log: `- [YYYY-MM-DD] pivot-decision — recommended <continue/adjust/pivot>, rationale: <X>`.

## Process

1. **Read the entire state document.** Every section. Evidence log in full. Session log in full. This skill is the only one that consumes everything.

2. **Summarize the founder's current state across:**
   - Time invested (weeks since starting).
   - Conversations conducted (count, ICP-targeted).
   - Behavioral signals at 0.6+ weight (count).
   - Attitudinal noise (count, with examples).
   - PMF stage and any Sean Ellis score.
   - Recent direction changes (from session log).
   - Cash runway remaining (if logged).

3. **Apply Dalton's opportunity cost framework.** Cite directly: *"You can only really work on one thing at a time. Working on something not working = not working on something else."*
   - **Expected value of continuing.** Given current PMF stage and evidence quality, what's the realistic probability of reaching $1M ARR in 24 months? Be honest: at pre-signal for 6+ months, this is low.
   - **Expected value of starting fresh.** With what you've learned, your next idea will be at least 2x better. Knowledge compounds across attempts. The 6 months invested are not lost — they trained your judgment.

4. **Run Klein's Pre-Mortem.** Verbatim or close: *"Imagine it's 12 months from now. The startup has catastrophically failed. Write the autopsy. What were the warning signs we ignored? What did we keep doing despite the data?"*
   - The pre-mortem unlocks risk acknowledgment that direct questioning won't. Founders defend present decisions; they critique past decisions freely.

5. **Apply bias sentinel AGGRESSIVELY** per `references/bias-sentinel.md`:
   - **Sunk cost — most load-bearing here.** Name it directly: "You've put 8 months in. That's done. The only question is forward expected value, not past investment." This is the bias that keeps founders in tar pits past the point of any return.
   - **Loss aversion.** Reframe: "Pivoting is gaining another shot on goal, not losing progress. Slack pivoted from Glitch. Brex pivoted from VR. Twitch was Justin.tv."
   - **Optimism bias.** "If you're using inspirational stories about persistence to justify staying, that's a tell — you're using founder folklore as evidence."
   - **Chronic pivoting (the inverse).** If the founder has pivoted 3+ times in 6 months, the pattern is dodging sales calls, not finding the right idea. Name it directly. "Pivoting again isn't the answer. The discipline you're missing is staying with one idea long enough to actually test it."

6. **Generate a binary-with-fallback recommendation:**
   - **Continue** — if PMF is converging or higher AND time invested < 12 months. Name the single most important next action.
   - **Adjust** — if there's a clear narrower wedge within the existing idea space. Name it specifically. Adjustments are not pivots — they're the founder's existing customers/insight applied to a sharper hypothesis.
   - **Pivot** — if pre-signal for 3+ months AND multiple bias signals present (sunk cost, optimism). Generate candidates per step 7.

7. **If pivot is recommended, generate 3–5 candidate pivots.** Each must be rooted in evidence already gathered: existing customer relationships, partial product, accumulated domain knowledge, prior research from `market-intel`. NOT brand-new spaces the founder has no relationship to.

   For each candidate, score against Dalton's 4-criteria from `references/scoring-rubrics.md`:
   - Market size (1–10)
   - Founder-market fit (1–10)
   - Ease of getting started (1–10)
   - Early market feedback evidence we *already* have (1–10)

   Identify the candidate that is **BOTH higher quality AND easier to start than the current direction.** This is Dalton's two-condition test — without both, the pivot is just movement, not progress.

8. **Reference real pivots from `references/case-studies.md`.** "Brex pivoted from VR to corporate cards because the founders had FMF in fintech, not in VR. The pivot worked because they pivoted *to* where they had earned credibility — not away from a hard problem."

9. **Update state.**
   - Current Decision Point: continue / adjust / pivot.
   - If pivot: One-Liner v(N+1) with the new candidate. Session Log entry documenting the rationale.
   - If continue: name the single most important next action, with a 4-week checkpoint date.
   - If adjust: update the Current Hypothesis with the narrower wedge.

10. **Recommend next skill.**
    - Continue → `signal-audit` at the 4-week checkpoint.
    - Adjust → `problem-focus` to sharpen the narrower wedge, then back to `discovery-coach` or `rapid-experiments`.
    - Pivot → `idea-pressure-test` on the chosen candidate. Restart the discovery loop with the new hypothesis.

## Outputs

- Writes to state: Current Decision Point, One-Liner (if pivot), Session Log.
- External resources to surface:
  - YC video *All About Pivoting* (Dalton) — entire video relevant.
  - Eric Ries, *The Lean Startup* — pivot chapter.
  - Brex pivot story (covered in Dalton's video).
  - Slack's pivot from Glitch.
- **Artifact on request only:** Pivot Decision Memo (markdown) — pre-mortem, opportunity-cost analysis, scored pivot candidates, recommended path. Offer once.

## Anti-Patterns Prevented

- Sunk-cost-driven persistence past the data.
- Pivoting *to* a space the founder has no edge in.
- Chronic pivoting as sales-call avoidance.
- Treating attitudinal validation as evidence to continue.
- "I'll give it another month" without a specific success metric for that month.

## Recommended Next Skills

Per step 10.

## Tone

Per `references/tone-and-stance.md`. The sharpest moment in the system. Founders bring their hardest emotions to this conversation. Empathy on the difficulty; rigor on the decision. Refuse to soften when the data is clear. Use Dalton's direct framings ("you can only work on one thing at a time").
