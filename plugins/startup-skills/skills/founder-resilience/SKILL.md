---
name: founder-resilience
description: |
  Decision-quality circuit-breaker. Before any major decision (build / raise / quit / hire / fire / pivot), checks founder physiological/emotional state and defers by 24 hours if depleted. Surfaces sustainable-pace, cofounder-alignment, and loneliness diagnostics. NOT self-care content — this is decision hygiene per Annie Duke and Kahneman.

  TRIGGER when: user is about to make a major irreversible decision AND mentions stress signals ("exhausted", "burnt out", "haven't slept", "I'm done", "this is killing me", "can't think straight"); PMF stage = pre-signal for 3+ months AND user is asking about a major next move; user explicitly asks about burnout, sustainable pace, or "should I keep going"; cofounder breakup is being considered (route to `cofounder-decision` AFTER this skill).

  SKIP: user is not in stress AND not making a major decision (this skill is for high-stakes + depleted intersections); user is asking general productivity/work-style questions (out of scope); user wants therapy (out of scope — route to professional resources).
---

# Founder Resilience

Founders make worse decisions when depleted. The 65%+ of startup decisions that happen under fatigue tend to be the worst decisions. This skill is a circuit-breaker before irreversible moves: if the founder is depleted AND making a high-cost decision, defer 24 hours and surface what changes that decision quality. This is decision hygiene per Annie Duke and Kahneman, not self-care content.

## When to Activate

- User is about to make a major irreversible decision (build / raise / quit / hire / fire / pivot) AND mentions stress signals: "exhausted," "burnt out," "haven't slept," "I'm done," "this is killing me," "can't think straight."
- PMF stage = pre-signal for 3+ months AND user is asking about a major next move.
- User explicitly asks about burnout, sustainable pace, or "should I keep going."
- Cofounder breakup is being considered (run this skill FIRST, then route to `cofounder-decision`).

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md` — sustainable pace, decision fatigue, loneliness diagnostic.
- `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md` — Annie Duke 24-hour rule, MAP, kill criteria.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`
- `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md` — modulate delivery on emotional state, never soften the claim.

## State Document Protocol

Read state. Pull Founder Profile (runway, resource reality, time horizon), recent Session Log (cadence + decisions). Update Founder Profile resilience-flag if surfaced. Session Log: `- [YYYY-MM-DD] founder-resilience — flagged <state>, deferred <decision>, return date: <date>`.

## Process

1. **Read state.** Pull resource reality, runway, recent decisions. Skim Session Log for cadence — if many sessions in a 48-hour window, that's a stress signal.

2. **Three hygiene questions** (per `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md`):
   - "Are you making this decision under physiological stress? (Sleep <6h, illness, family emergency, financial crisis.)"
   - "Is this decision reversible in 30 days?" If NO, escalate audit pressure.
   - "Is your cofounder seeing the same data the same way?" If NO, route to `cofounder-decision`.

3. **The 24-hour rule** (Annie Duke). If stressed AND decision is irreversible: defer 24 hours. State explicitly: "If the decision is right, it'll be the same tomorrow. If it changes after sleep, you were just tired. Either way, sleep is the cheapest intervention."
   - Set a return date in the state document.
   - The system will not facilitate the decision until that date.

4. **Sustainable-pace check** (every 4 weeks). Ask:
   - "Can you maintain your current burn rate (mental + financial) for 18 months?"
   - If no, name the constraint. This is a decision-making input, not an inspirational obstacle.
   - Pace IS strategy.

5. **Cofounder alignment one-liner** (if applicable):
   > "My cofounder and I both believe our biggest risk is _______ and our biggest advantage is _______."
   - If founder cannot answer for cofounder, that's the diagnostic. Route to `cofounder-decision`.

6. **Loneliness diagnostic.** By month 6-12, the founder is often the only person who knows what's at stake.
   - "Who do you talk to about the hard parts of this? Not your team, not your family — peers who've been here."
   - If the answer is "no one," surface venues: YC Bookface, Pavilion, On Deck, MicroConf, niche founder Discords.
   - "Loneliness is the founder's most under-diagnosed problem" (Ben Horowitz framing).

7. **"You are not your company" reframe** (Horowitz, Andreessen). When the founder frames the decision in identity terms ("I'm not the kind of person who Y"), separate: the company is a separate entity; failure is not a reflection on ability; you can hire people smarter than you at parts of the job; the company will eventually not need you for everything — that's success, not failure.

8. **"Would you start this today?" reframe** (Annie Duke, *Quit*):
   - "If you were starting today, knowing what you know, would you start this?"
   - If no, that's a kill signal.
   - This silences sunk-cost reasoning specifically.

9. **Burnout warning signs check.** Surface any that match:
   - You're working but not deciding.
   - You stopped reading critical email.
   - You stopped customer interviews because "I know what they'll say."
   - You feel relieved when meetings get canceled.
   - You're rationalizing why you don't need to update your beliefs.
   If 2+ match: route to a 1-week break before ANY major decision. State this directly.

10. **Bias sentinel pass:**
    - **Sunk cost dressed as resilience** ("I just need to push through one more sprint"). Distinguish grit-on-the-right-problem from grit-on-a-dead-problem.
    - **Identity-protective cognition** ("I'm not the kind of person who quits"). Reframe as decision quality, not character.
    - **Performance burnout-denial** ("I'm fine"). Founders who say "I'm fine" while ticking 3+ burnout signs are not fine.

11. **Update state.** Founder Profile resilience-flag. Defer dates if applicable. Session Log.

12. **Recommend next.**
    - If deferred 24h: the originating skill (where the founder came from) re-fires after deadline.
    - If routed to `cofounder-decision`: explicit.
    - If 1-week break recommended: surface specific re-entry trigger ("come back after Z").
    - Otherwise: return to originating skill with the resilience check logged.

## Outputs

- Writes to state: Founder Profile resilience-flag, defer dates, Session Log.
- No artifacts produced. This skill is a circuit-breaker, not a generator.

## Anti-Patterns Prevented

- Major decisions under physiological stress.
- Identity-laden framing of business decisions.
- "I'm fine" denial while ticking burnout signs.
- Skipping the cofounder-alignment check before major moves.
- Deferring loneliness diagnosis ("I'll find a peer later").
- Sunk-cost dressed as resilience.

## Recommended Next Skills

Per step 12. Usually returns to the originating skill (`mvp-architect`, `pivot-decision`, `pmf-audit`, `cofounder-decision`).

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md` and `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`. **Modulate delivery on emotional state; never soften the claim.** Acknowledge the founder's state first ("I see you're exhausted and runway is short"), then deliver the load-bearing truth ("the data still says X"). Empathy on the difficulty; rigor on the decision. This skill especially earns its place by *being firm about deferring* when the founder wants to push through.
