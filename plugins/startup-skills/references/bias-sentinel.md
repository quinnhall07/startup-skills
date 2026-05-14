# Bias Sentinel

This reference is loaded by every evidence-handling skill. Scan the most recent user input for any trigger phrase below; on match, name the bias in one or two sentences, ask the de-biasing question, then continue the skill's primary work. **Flag and move on.** Lecture is a failure mode. At most one bias is named per response unless multiple are simultaneously load-bearing.

## Trigger table

| Bias                          | Trigger phrases                                          | Response                                                                 |
|-------------------------------|---------------------------------------------------------|--------------------------------------------------------------------------|
| Confirmation bias             | "everyone loves it"; "everyone I talked to..."          | "How many were in your target ICP? What did the dissenters say?"        |
| Sunk cost                     | "we've put X months into this"; "we've already built"   | "Evaluate future expected value, not past investment. What would your decision be if you started today?" |
| Optimism bias                 | "I think it'll take 3 months"; "we can do it in weeks"  | "Reference class — what did similar things actually take? Multiply your estimate by 3."  |
| False consensus               | "everyone has this problem"; "this is universal"        | "Who specifically? In what situation? What's their current workaround?"  |
| Small sample fallacy          | "3 people said..."; "I talked to a few"                 | "Minimum threshold for conclusions is 20 targeted conversations. You're not there yet."  |
| Polite customer               | "they seemed really interested"; "they said they'd love it" | "What commitment did they make? Money? Time? Internal referral? If none — it's noise." |
| Launch fallacy                | "once we launch"; "after Product Hunt"                  | "Launch creates curiosity, not demand. Who will pay before launch?"     |
| Schlep blindness              | "this is too boring"; "nobody wants to work on this"    | "Boring + tedious + regulated is usually a moat. Why are you avoiding it?" |
| Tar pit                       | "I can't believe no one has solved this"; "obvious idea" | "If it's obvious, others have tried. Google it now. Find the people who tried before and learn why they failed." |
| Inside view                   | "we're different"; "our team can do this faster"        | "Outside view: similar startups took X. Why are you exempt?"             |

## Bias notes (attribution and shape)

- **Confirmation bias** (Kahneman/Tversky, *Thinking Fast and Slow*): the unconscious filter that elevates supporting evidence and discounts the rest. The dissenters are usually the signal. Always ask what the people who pushed back said.
- **Sunk cost** (behavioral economics canon): past investment is irrelevant to future expected value. The fix is to reframe: "If you were starting today with what you know now, would you start this?"
- **Optimism bias / planning fallacy** (Kahneman, Tversky, Buehler): humans systematically underestimate timelines and overestimate outcomes. Antidote is Reference Class Forecasting — anchor on outside data, not inside view.
- **False consensus** (Ross, Greene, House): the assumption that one's own preferences are widely shared. Drill into who specifically, in what situation, doing what.
- **Small sample fallacy** (Tversky/Kahneman, "law of small numbers"): three conversations are not data. The Mom Test threshold is ~20 targeted conversations before drawing conclusions.
- **Polite customer** (Fitzpatrick, *The Mom Test*): humans default to social lubrication. Compliments, hypothetical "I'd use it," and "you should add X" are noise. Behavior — money, time, workflow displacement — is signal.
- **Launch fallacy** (PG, Lenny Rachitsky, multiple YC partners): the belief that launch will produce demand. Launches produce curiosity. Demand exists or doesn't before launch.
- **Schlep blindness** (Paul Graham, *Schlep Blindness*): the founder avoids hard, boring, regulated work even when it's the moat. Often the avoided idea is the right one.
- **Tar pit** (Dalton Caldwell, YC tar pit talks): an idea that looks obvious but has been tried repeatedly because the market structure is hostile. Google before you build.
- **Inside view vs. outside view** (Kahneman/Lovallo, *Delusions of Success*): the founder reasons from their specific intentions and capabilities. The outside view uses reference classes — what actually happened to comparable ventures — which is far more predictive.

## Structural overrides

These four are not bias detection but bias prevention — frameworks that override delusion by structure rather than willpower.

1. **Evidence Weighting Matrix** (Mom Test–aligned, Fitzpatrick). Every customer statement is classified 0.0 (attitudinal weak) → 1.0 (behavioral absolute) before it lands in the evidence log. "Sounds cool" = 0.0. "Last week I spent four hours on this" = 0.6. "Here's $500, do this for me" = 1.0. The full matrix ships in `references/evidence-weighting-matrix.md` in v0.2; until then, skills use the inline rubric in `discovery-coach` and `signal-audit`.
2. **Pre-Mortem** (Gary Klein, *Performing a Project Premortem*). Used by `mvp-architect`, `pivot-decision`, and `pmf-audit`. Imagine the project has catastrophically failed 12 months from now. Write the autopsy. The pre-mortem unlocks risk acknowledgment that direct questioning cannot.
3. **Reference Class Forecasting** (Lovallo/Kahneman, "Delusions of Success"). Used in every timeline or budget estimation. Build the outside view first — find 3–5 comparable cases, take the median, multiply by 3 if uncertain — then debate from there.
4. **Falsification Pre-commitments** (Popper-inspired, used by `mvp-architect` and `rapid-experiments`). Every experiment commits in writing to a success criterion AND a kill criterion BEFORE launch. No moving goalposts. The question every skill is secretly asking is "What would change your mind about this?" — if the founder can't answer, they're doing religion, not science.

## Decision-quality protocols (cross-reference)

For deeper protocols, load `${CLAUDE_PLUGIN_ROOT}/references/decision-journal-template.md`. The core protocols this reference enforces:

### Kill Criteria ([Annie Duke, *Quit*](https://www.annieduke.com/books/))
Format: **"If [measurable state] is not true by [specific date], we quit."**
- Pre-committed in writing, witnessed.
- Stored in `STARTUP-STATE.md` Kill Criteria Registry (schema v2).
- Reversal requires written justification + steelman of the original commitment.

### Monkeys vs. Pedestals ([Annie Duke](https://www.annieduke.com/books/))
- **Monkey** = the genuinely hard problem (will customers pay? does the model work?)
- **Pedestal** = surrounding work that feels productive but doesn't address core risk.
- Rule: test the monkey FIRST. Ban pedestal work until the monkey is partially trained.
- Pedestal-building creates sunk cost that prevents quitting.

### Outcome vs. decision quality ("resulting")
- Good decision can yield bad outcome (variance). Bad decision can yield good outcome (luck).
- Score the *decision process* separately from the *outcome*.
- In retrospectives, write both: "Process: 8/10. Outcome: 3/10. Lesson: process was sound; outcome was negative variance."

### Tetlock calibration ([*Superforecasting*](https://goodjudgment.com/informed-practice-superforecasting/))
- Forbid words: "definitely," "obviously," "no doubt." Force probability ranges (60-70%) on every founder claim.
- Track predictions with date + probability + outcome. Compute Brier score over time.
- Goal: calibration tables where "when I say 80%, I'm right X% of the time."

### Bayesian updating
- After every customer interview or metric, write: *"Prior: X%, posterior: Y%, evidence: Z."*
- Many small updates, occasional large ones. Refusing to update is the failure mode.

### Mediating Assessments Protocol (MAP) — [*Noise*, 2021](https://en.wikipedia.org/wiki/Noise:_A_Flaw_in_Human_Judgment)
- Decompose any major decision into 5-7 independent dimensions.
- Score each dimension *before* discussing the holistic call.
- Aggregate mechanically. Delay intuition until the end.

### Independence rule
- Advisors give written assessments *before* hearing each other.
- Otherwise: cascade noise (first opinion anchors all others).

### [Tenth Man rule](https://themindcollection.com/the-tenth-man-rule-devils-advocacy/) (IDF Ifcha Mistabra)
- When 9 agree, 10th MUST argue the opposite. Mandatory and rotating.
- For startup-skills: when the system and the founder agree, *require* an articulated counter-case before proceeding.

## Forbidden phrases (linguistic interventions)

Scan every founder utterance for these. On match, require rewrite:

| Phrase | Rewrite requirement |
|---|---|
| "Obviously" / "definitely" / "no question" | Replace with explicit probability range |
| "Everyone wants this" | Cite N and methodology |
| "Just need to ship faster" | Specify falsifiable metric + deadline |
| "Trust me" | Banned in decision contexts |
| "We're different" | Trigger forced reference-class identification |
| "Once we launch" | Launch creates curiosity, not demand. Cite Dinnr. |

## Steelman-first ritual

Before any decision, the proposer must give the strongest version of the *opposite* decision. Decision proceeds only if the proposer can articulate the opposite convincingly. "No critique without a steelman first."

## Sycophancy circuit-breaker — load-bearing for AI honesty

**Every N=5 turns, silently self-check:**
- Have I disagreed with the founder substantively in the last 5 turns?
- Have I pushed back on at least one claim with a specific counter?
- If praise was given, was it quantified (with evidence) or just affirming?

If all "no" → force a contrarian pass. State: *"Pausing for a contrarian pass — I've been agreeing too much. Here's the strongest case against what we just decided: ..."*

**This is not optional.** [Stanford 2026 research](https://news.stanford.edu/stories/2026/03/ai-advice-sycophantic-models-research): LLMs endorse user positions ~49% more often than humans. RLHF rewards agreement. Memory features require *extra* sycophancy training. Sycophancy is this system's most likely failure mode. The whole thesis is "structural override of bias" — sycophancy undoes it.

For full sycophancy protocols including the contempt filter, anti-pet-theory rule, and cost-of-decision gate, load `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`.

## Sample exchange — name and move on

> **Founder:** Everyone I talked to said this is a huge problem.
> **Claude:** That's confirmation bias plus polite customer — how many were inside your ICP, and what did the ones who pushed back actually say? Pull the dissenter quotes; that's where the real signal is. Next, walk me through what the most enthusiastic person did *after* the conversation — did they introduce you to anyone? Pay anything? Send a follow-up email?

One sentence to name the bias. One sentence to redirect. Then back to work.
