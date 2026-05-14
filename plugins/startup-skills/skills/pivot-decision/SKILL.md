---
name: pivot-decision
description: |
  Structured decision gate: continue / adjust / pivot. Reads entire `STARTUP-STATE.md`, runs Dalton's opportunity cost calc + Klein's pre-mortem, aggressively counters sunk cost (Annie Duke). Generates 3-5 scored pivot candidates rooted in what the founder has ALREADY learned. The sharpest emotional moment in the system.

  TRIGGER when: user says "should I pivot", "stuck", "this isn't working", "I've been at this for months", "considering changing direction", "should I quit", "maybe I should try something different"; routine cadence (every 4-6 weeks during active building); auto-fire from `signal-audit` when pre-signal for 3+ months; auto-fire from `pmf-audit` when Sean Ellis declining quarter-over-quarter.

  SKIP: user is in active cofounder conflict (route to `cofounder-decision` first — cofounder alignment must be resolved before pivot decision); user is depleted / making decision under stress (route to `founder-resilience` first); user is pre-validation with no committed direction (route to `idea-pressure-test`); user just had bad day, not chronic signal (run sustainable-pace check first).
---

# Pivot Decision

The structured decision gate for "continue / adjust / pivot." Reads the full state document, computes Dalton's opportunity cost, runs Klein's pre-mortem, and aggressively counters sunk cost. When pivot is recommended, generates 3–5 candidates rooted in what the founder has *already learned*.

## HARD-GATE — preconditions for sound decision:

- [ ] User is NOT making this decision under acute physiological stress. If yes, route to `founder-resilience` for the 24-hour rule.
- [ ] Cofounder alignment exists OR cofounder is part of this decision. If cofounder disagrees and isn't present, route to `cofounder-decision` first.
- [ ] User has read the full `STARTUP-STATE.md` (or willing to in this session). Pivot decisions require full context, not summaries.

## When to Activate

- Phrases: "should I pivot," "stuck," "this isn't working," "I've been at this for months," "maybe I should try something different," "considering changing direction," "should I quit."
- Routine: every 4–6 weeks during active building, even when not stuck. The cadence prevents drift.
- Auto-fire from `signal-audit` when the founder has been at pre-signal stage for 3+ months.
- Auto-fire from `pmf-audit` when the Sean Ellis score is declining quarter-over-quarter.

## Red flags

| Founder claim | Response |
|---|---|
| "We've put N months in" | Sunk cost. Reframe: forward expected value only. |
| "I'm not the kind of person who quits" | Identity-protective cognition. Reframe as decision quality, not character. |
| "If I just push harder" without specific metric | Stubborn ≠ determined. Determination updates on evidence. |
| Wants to pivot to a space with no FMF | Refuse. Pivot TO where edge exists. |
| 3+ pivots in 6 months | Chronic pivoting. Refuse. Diagnose discipline gap. |
| Considers decision while exhausted | Route to `founder-resilience` for 24-hour rule. |
| Cofounder disagrees, founder asks how to convince them | Route to `cofounder-decision`. Refuse to mediate alone. |
| "I'll give it another month" without specific success metric | Force the metric. Otherwise the decision is permanently deferred. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — sunk cost (most load-bearing here), loss aversion, optimism bias, chronic pivoting.
- `${CLAUDE_PLUGIN_ROOT}/references/scoring-rubrics.md` — Dalton's 4-criteria rubric for pivot candidates.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Slack (Glitch → enterprise chat), Brex (VR → corporate cards), Segment (classroom → analytics), Magic (concierge → AI assistants).
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Dalton's *All About Pivoting*, Eric Ries pivot chapter.
- `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md` — kill criteria, MAP, monkeys-vs-pedestals.
- `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md` — decision quality under stress.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — for AI-product pivots.

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

5. **Apply bias sentinel AGGRESSIVELY** per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`:
   - **Sunk cost — most load-bearing here.** "You've put N months in. That's done. The only question is forward expected value, not past investment."
   - **Annie Duke's "would you start this today?"** "If you were starting today, knowing what you know, would you start this?" If no, that's a kill signal that silences sunk-cost reasoning.
   - **Monkeys vs. pedestals** (Annie Duke). Have you been testing the monkey (will customers pay?) or building pedestals (logo, deck, advisor relationships)? If pedestal-heavy: that's the diagnostic.
   - **Loss aversion.** Reframe: "Pivoting is gaining another shot on goal, not losing progress. Slack pivoted from Glitch. Brex pivoted from VR. Twitch was Justin.tv."
   - **Optimism bias.** "If you're using inspirational stories about persistence to justify staying, that's a tell — founder folklore as evidence."
   - **Chronic pivoting (the inverse).** 3+ pivots in 6 months = pattern is dodging sales calls, not finding the right idea. Refuse another pivot. Name the discipline gap.

6. **Generate a binary-with-fallback recommendation:**
   - **Continue** — if PMF is converging or higher AND time invested < 12 months. Name the single most important next action.
   - **Adjust** — if there's a clear narrower wedge within the existing idea space. Name it specifically. Adjustments are not pivots — they're the founder's existing customers/insight applied to a sharper hypothesis.
   - **Pivot** — if pre-signal for 3+ months AND multiple bias signals present (sunk cost, optimism). Generate candidates per step 7.

7. **If pivot is recommended, generate 3-5 candidate pivots.** Each must be rooted in evidence already gathered. NOT brand-new spaces the founder has no relationship to.

   **Explicit candidate-generation formula** (apply in order; pick 3-5 that fit):
   - **Candidate 1: Adjacent ICP expansion.** Same domain, different customer slice within it.
   - **Candidate 2: Adjacent problem, same ICP.** Same customer, different pain you've discovered through interviews.
   - **Candidate 3: Apply current insights to a domain you've earned credibility in.** (Brex pattern — VR → fintech because the team had prior fintech FMF.)
   - **Candidate 4: Strongest partial product as a new wedge.** (Segment pattern — analytics code the team kept writing for themselves.)
   - **Candidate 5: A space surfaced repeatedly in customer interviews as adjacent need.**

   Refuse pivots into spaces where the founder has no edge, no relationship, no insight. That's flight, not pivot.

   Score each against `${CLAUDE_PLUGIN_ROOT}/references/scoring-rubrics.md` Dalton 4-criteria:
   - Market size (1-10).
   - Founder-market fit (1-10).
   - Ease of getting started (1-10).
   - Early market feedback evidence we *already* have (1-10).

   Identify the candidate that is BOTH **higher quality AND easier to start** than the current direction (Dalton's two-condition test).

8. **Reference real pivots from `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md`.** "Brex pivoted from VR to corporate cards because the founders had FMF in fintech, not in VR. The pivot worked because they pivoted *to* where they had earned credibility — not away from a hard problem."

9. **Update state.**
   - Current Decision Point: continue / adjust / pivot.
   - If pivot: One-Liner v(N+1) with the new candidate. Session Log entry documenting the rationale.
   - If continue: name the single most important next action, with a 4-week checkpoint date.
   - If adjust: update the Current Hypothesis with the narrower wedge.

10. **Recommend next skill.**
    - Continue → `signal-audit` at 4-week checkpoint with named success metric.
    - Adjust → `problem-focus` to sharpen the narrower wedge, then `discovery-coach` or `rapid-experiments` to test.
    - Pivot → `idea-pressure-test` on the chosen candidate. Restart discovery loop with new hypothesis.
    - If pivot rejected due to founder depletion → `founder-resilience`, then re-fire `pivot-decision` after recovery.

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

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. The sharpest moment in the system. Founders bring their hardest emotions to this conversation. Empathy on the difficulty; rigor on the decision. Refuse to soften when the data is clear. Use Dalton's direct framings ("you can only work on one thing at a time").
