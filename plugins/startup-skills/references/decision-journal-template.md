# Decision Journal & Structural Override Protocols

Structural decision-quality protocols. Kill criteria, pre-mortems, mediating assessments, calibration tracking, sycophancy circuit-breakers, the Tenth Man rule. These are not awareness exercises — they are enforcement mechanisms. The plugin's thesis: **structural override of bias, not awareness of bias.**

## Decision Journal (Shane Parrish / Farnam Street)

For every major decision (raise, pivot, hire, kill, pricing change), log the following to `STARTUP-STATE.md` under `## Decision Journal`:

- **Date**: ISO date (YYYY-MM-DD).
- **Decision**: One sentence.
- **Physical/emotional state**: tired / clear / stressed / energized. State predicts judgment quality more than founders admit.
- **Expected outcome**: The specific thing you predict happens.
- **Confidence**: Percentage range (e.g., 60–70%). The word "definitely" is forbidden (see calibration).
- **Alternatives considered**: 2–3 alternatives and one sentence each on why rejected. Fewer than two = decision is not ready.
- **Key assumptions**: What would have to break for this to fail. Bayes priors live here.
- **Review date**: Default 6 months from decision date.
- **At review**: actual outcome, prediction error (in percentage points), and an explicit split: *what was knowable at decision time* vs. *what was luck/variance*.

Source: Shane Parrish, *Decision Journal* (fs.blog/decision-journal) and the Farnam Street template (fs.blog/wp-content/uploads/2017/02/decision-journal_draft3.pdf).

## Annie Duke's Kill Criteria (*Quit*, 2022)

Format: **"If [measurable state] is not true by [specific date], we quit."** Examples:

- "If we don't have 10 paying customers by Sept 1, we shut down the SMB segment."
- "If retention week-4 is below 20% after 3 product iterations, we pivot."
- "If we haven't closed a $50k contract by end of Q2, the enterprise motion is dead."

Pre-committed in writing. Witnessed by an advisor or cofounder. Stored outside the founder's unilateral control (shared doc, advisor's inbox). Reversal requires written justification *plus a steelman of the original commitment* — i.e., the founder must argue the case for quitting before being allowed to overturn the trigger. Without this, kill criteria collapse into aspirations.

## Monkeys vs. Pedestals (Annie Duke, *Quit*)

- **Monkey** = the genuinely hard problem: will customers pay, does the model work, can we acquire below CAC ceiling.
- **Pedestal** = surrounding work that feels productive but does not address core risk: logo, landing page, incorporation, hiring an advisor, picking a stack.

**Rule**: test the monkey FIRST. Ban pedestal work until the monkey is at least partially trained. Pedestal-building creates sunk cost (Section above on kill criteria explains why this is corrosive) — the longer the pedestal stands without a trained monkey, the harder quitting becomes.

## Outcome quality vs. decision quality — "resulting" (Annie Duke)

A good decision can yield a bad outcome (negative variance). A bad decision can yield a good outcome (luck). Judging decisions by outcomes destroys learning, because variance is mistaken for skill in both directions.

**Score the decision process separately from the outcome**, every retrospective. Write both lines:

> Process: 8/10 (information available was used; alternatives steelmanned; kill criteria set in writing).
> Outcome: 3/10 (lost the deal).
> Lesson: process was sound; outcome was negative variance. Repeat the process.

When process is 3/10 and outcome is 8/10, the lesson is *don't trust the win* — it was luck. Source: Annie Duke, *Thinking in Bets* and *Quit* (annieduke.com, behavioralscientist.org).

## Gary Klein's Pre-Mortem — full protocol

Source: Gary Klein, *Performing a Project Premortem*, HBR 2007 (hbr.org/2007/09/performing-a-project-premortem; gary-klein.com/premortem). 20–30 minutes, facilitated.

1. **Setup**: full team present, plan briefed in 5 minutes.
2. **Imagined fiasco**: "It is 12 months from now. This project is a catastrophic failure. We are out of money. Why?" Past tense matters — past tense unlocks specifics ("we ran out because…"); future tense ("might fail") generates vague hedges.
3. **Silent generation, 3 minutes**: each person writes every reason it failed. Alone. No talking. Silence is non-negotiable — it kills cascade and HiPPO bias.
4. **Round-robin consolidation**: each person reads ONE reason; facilitator records. Next person, one reason. One item per round prevents dominant voices from setting the frame.
5. **Revisit the plan**: pick the top 3 most-concerning failure modes. For each, define a concrete mitigation OR an explicit kill criterion (Section above).
6. **Repeat at every inflection**: raise, launch, key hire, major pivot.

## Mediating Assessments Protocol — MAP (Kahneman/Sibony/Sunstein, *Noise*, 2021)

Source: *Noise: A Flaw in Human Judgment* (en.wikipedia.org/wiki/Noise:_A_Flaw_in_Human_Judgment); Kahneman/Lovallo/Sibony, *A Structured Approach to Strategic Decisions*, MIT Sloan Review (sloanreview.mit.edu/article/a-structured-approach-to-strategic-decisions/).

- Decompose any major decision (raise, pivot, key hire, pricing reset) into **5–7 independent dimensions**.
- Score each dimension *before* discussing the holistic call. Independence prevents the global gut from contaminating the parts.
- Aggregate **mechanically** — sum, weighted sum, or a defined rule — not by re-feeling the decision.
- **Delay intuition until the end.** The founder's primary failure mode is collapsing all factors into one gut feeling at minute zero. MAP forces the gut to wait.

## Independence rule (Kahneman/Sibony/Sunstein, *Noise*)

Advisors must give **written assessments before hearing each other or the founder**. Otherwise the first opinion anchors all others — cascade noise dominates and three advisors produce one opinion in triplicate.

Implementation: a 5-question email to 3 advisors. Each replies independently within a deadline. Compile, then discuss. The "I think Mark already said it better" reply is the failure signal; rerun the protocol.

## The Tenth Man rule (IDF Ifcha Mistabra, post-Yom Kippur 1973)

Source: themindcollection.com/the-tenth-man-rule-devils-advocacy. When 9 analysts agree, the 10th is **required** to argue the opposite — seriously, often for an extended assignment. Role-based, not personality-based: assigned by rotation, not picked because someone "likes to disagree."

For startup-skills: when the system and the founder agree, **require an articulated counter-case before proceeding.** Mandatory, not optional. The skill loading this protocol will not advance past convergence without a written contrarian pass.

## Tetlock calibration (*Superforecasting*)

Source: Tetlock, *Superforecasting* (goodjudgment.com/informed-practice-superforecasting); Edge Master Class 2015 (edge.org/conversation/philip_tetlock-edge-master-class-2015-a-short-course-in-superforecasting-class-ii); Brier score (en.wikipedia.org/wiki/Brier_score).

- **Forbidden words**: "definitely," "obviously," "no doubt," "no question."
- **Force probability ranges on every founder claim**: 60–70%, not "very likely."
- **Track every prediction**: date + claim + probability + resolution + outcome.
- **Compute Brier score** over time. The goal is a calibration table: "when I say 80%, I am right ~80% of the time."
- Tetlock's Good Judgment Project: superforecasters improved ~6% with structured training. Small numbers compound over hundreds of bets.

## Bayesian updating practice

After every customer interview or material metric, write a one-liner: ***"Prior: X%, posterior: Y%, evidence: Z."*** Many small updates, occasional large ones. The founder failure mode is anchoring on the initial thesis and dismissing disconfirming evidence as outliers; the journal entry makes that dismissal visible.

## Forbidden phrases — linguistic interventions

| Phrase | Replace with |
|--------|--------------|
| "Obviously" / "definitely" / "no question" | An explicit probability or confidence range. |
| "Everyone wants this" | Cite N + methodology + dissenter quotes. |
| "Just need to ship faster" | A falsifiable metric with a date. |
| "Trust me" | Banned in decision contexts. State the evidence. |
| "We're different" | Trigger forced reference-class identification (outside view; see `bias-sentinel.md`). |

## Steelman-first ritual

Before any decision, the proposer must give the **strongest version of the opposite decision**. Decision proceeds only if the proposer can articulate the opposite convincingly. House rule: **"No critique without a steelman first."** This is also the gate for reversing a kill criterion (Annie Duke section above).

## Sycophancy circuit-breaker (every N=5 turns)

LLM sycophancy is the system's primary failure mode. Empirical reference: SycEval, *Sycophancy in LLMs* (arxiv.org/abs/2502.08177). Silent self-check every 5 turns:

- Have I disagreed with the founder substantively in the last 5 turns?
- Have I pushed back on at least one specific claim with a specific counter?
- If praise was given, was it quantified (with evidence) or just affirming?

If all three are "no" → force a contrarian pass. State it out loud:

> "Pausing for a contrarian pass — I have been agreeing too much. The strongest case against what we just decided is: …"

**Not optional.** A skill that goes 5 turns without disagreement is no longer doing its job.

## Where this is used

Loaded as the enforcement-override library by `bias-sentinel.md`, and consumed directly by `pivot-decision`, `pmf-audit`, `mvp-architect`, `signal-audit`, and the planned `founder-resilience` skill. Where `bias-sentinel.md` names biases as they appear, this file is the set of pre-committed structures that prevent the biases from steering the decision in the first place.

WROTE: /Users/hunter/Documents/GitHub/startup-skills/plugins/startup-skills/references/decision-journal-template.md (128 lines)
