---
name: cofounder-decision
description: |
  Cofounder conflict, breakup, mid-flight equity disputes. Distinct from `cofounder-fit` (initial team gap diagnosis). Refuses to help one founder convince the other without both present. Three outcomes: continue with role realignment / one founder exits cleanly / pivot both align on.

  TRIGGER when: user says "cofounder disagrees", "cofounder wants to quit", "should I fire my cofounder", "cofounder fight", "we can't agree on direction", "cofounder breakup", "vesting cliff is coming"; user is asking how to convince another founder of something; founder reports a sustained 2+ week disagreement.

  SKIP: this is an initial team-gap question (no current cofounder, evaluating a candidate) → route to `cofounder-fit`; the conflict is about a specific tactical decision (pricing, pivot, hire) → route to the relevant decision-gate skill first; user wants help drafting a separation agreement (route to legal counsel — out of scope).
---

# Cofounder Decision

Cofounder relationships fail more often than marriages and on faster timelines. When founders disagree for 2+ weeks, the relationship is the load-bearing problem, not the decision they're disagreeing about. This skill mediates toward three structured outcomes: continue with explicit role realignment, one founder exits cleanly, or pivot both align on. Refuses to help one founder convince the other without both present.

## HARD-GATE

- [ ] User confirms BOTH founders will participate in this skill's process (synchronously or async via the same chat).
- [ ] User describes the disagreement as either: data-based (facts to verify) OR preference-based (values to surface), not as one founder's "wrongness."
- [ ] No prior commitment to a specific outcome — both founders willing to consider continue / exit / pivot.

If any unchecked: state directly: "I can't help one founder convince the other. Bring your cofounder into this conversation, OR shift to a question that doesn't require their consent (e.g., 'Should I evaluate the cofounder fit honestly?' — route to `cofounder-fit` instead)."

## When to Activate

- Phrases: "cofounder disagrees," "cofounder wants to quit," "should I fire my cofounder," "cofounder fight," "we can't agree on direction," "cofounder breakup," "vesting cliff is coming."
- User is asking how to convince another founder of something.
- Founder reports a sustained 2+ week disagreement.

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md` — YC rules, separation patterns.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — sunk cost, loss aversion, identity-protective cognition.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md` — Crucial Conversations, contempt filter.
- `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md` — MAP, Tenth Man, Independence rule.
- `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md` — alignment one-liner.
- `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`

## State Document Protocol

Read entire state (Team, Evidence Log, Session Log). Update Team section with conflict log + resolution. Session Log: `- [YYYY-MM-DD] cofounder-decision — diagnosed <type>, outcome: <continue/exit/pivot>`.

## Process

1. **Read state.** Team section, recent Session Log entries, recent decisions where the cofounders disagreed.

2. **Separate value-function check.** Each founder names their real constraint (one at a time, separately):
   - Financial runway personally.
   - Time horizon they can give.
   - Lived expertise tied to the current idea space.
   - Exit value / what success looks like to them.
   - Family / life-event constraints.
   Surface mismatches. Often the conflict isn't about the company — it's about diverging personal constraints.

3. **Factcheck the disagreement.** Is this data or preference?
   - **Data:** "We disagree on whether retention is good." → check evidence log. Resolve with `signal-audit`.
   - **Preference:** "I want to build for SMBs; my cofounder wants enterprise." → no objectively right answer. Surface as preference. Each founder names what would change their mind.
   - **Identity:** "My cofounder doesn't take this seriously." → underlying value conflict. Address directly.

4. **Apply the cofounder alignment one-liner** (per `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md`). Each founder completes separately, in writing:
   > "My cofounder and I both believe our biggest risk is _______ and our biggest advantage is _______."
   Compare answers. Divergence = different theories of the business. Reconcile or surface the irreconcilability.

5. **Per-founder opportunity-cost recalc.** What does each founder give up by continuing? By quitting?
   - Founder A: continues = X years opportunity cost + relationship with B; exits = lose Y equity, gain Z time.
   - Founder B: same calculus.
   - Often the answer is asymmetric — and the asymmetry is the source of the conflict.

6. **MAP — Mediating Assessments Protocol** (per `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md`). Decompose into 5 dimensions: business viability (independent of cofounder), founder-market-fit per founder, working relationship quality, financial constraints, life/family alignment. Each founder scores all 5 BEFORE discussing. Compare scores. Pattern of disagreement reveals the load-bearing dimension.

7. **Tenth Man pass.** If both founders agree on one outcome, REQUIRE one of them to articulate the strongest case for the opposite. (Per `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md` and `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md`.) Prevents premature consensus driven by relationship-preservation.

8. **Generate three structured outcomes:**
   - **Continue with role realignment.** Specific changes: who owns what, decision rights, weekly checkpoint, equity ratio honest. Vesting cliff acknowledged.
   - **One founder exits cleanly.** Per `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md` separation patterns: vesting + buyback per founder agreement, dignity preserved, equity transferred per contract, no surprise to the cap table.
   - **Pivot both align on.** Route to `pivot-decision`. Both must commit to the new direction or the conflict re-emerges in 30 days.

9. **Bias sentinel pass** per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`:
   - **Sunk cost on the relationship** ("we've been at this together for 2 years"). Name it.
   - **Loss aversion** ("I'll lose what we've built"). Reframe per Annie Duke: future expected value, not past.
   - **Identity-protective cognition.** "I'm not the kind of person who quits / fires a cofounder." → name the bias, surface the costs of not deciding.
   - **Contempt filter** (per `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`). Refuse to engage with framing that attacks one founder's character. Critique behaviors, not the person.

10. **Surface the decision-by-default risk.** Cofounder conflicts left unresolved compound. Sunk-cost grows, resentment compounds, the equity dispute gets harder to resolve cleanly. If a decision is deferred, name the cost: "Every additional month without resolution makes a clean exit harder."

11. **Update state.** Team section with conflict diagnosis + chosen outcome + concrete next actions per founder. Session Log.

12. **Recommend next.**
    - Continue → `signal-audit` at 4-week checkpoint to verify the realignment is producing different decisions.
    - Exit → route to legal counsel (out of scope for this skill). Surface the YC founder-agreement separation pattern from `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md`.
    - Pivot → `pivot-decision`.

## Outputs

- Writes to state: Team section (full conflict + outcome log), Session Log.
- **Artifact on request only:** Cofounder Decision Memo (markdown) — the value-function summary, MAP scores, three outcomes, chosen path with rationale. Useful for both founders to revisit in 30 days.

## Anti-Patterns Prevented

- Helping one founder convince the other (without both present).
- Treating preference conflicts as data conflicts (or vice versa).
- Deferring the decision indefinitely.
- Skipping vesting / separation patterns when one founder exits.
- Contempt-laden framing ("my cofounder is lazy / dumb / unmotivated").
- Premature consensus that re-emerges in 30 days.

## Recommended Next Skills

Per step 12.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md` and `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`. The sharpest emotional moment in the system, second only to `pivot-decision`. Empathy on the difficulty of the conversation; rigor on the decision. Refuse contempt-laden framing without compromising the truth of the diagnosis.
