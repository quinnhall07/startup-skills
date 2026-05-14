---
name: rapid-experiments
description: |
  Design behavioral validation experiments matched to the founder's archetype (Fake Door / Wizard of Oz / Concierge / Pre-order). Enforces falsification pre-commitments — success AND kill criteria in writing before deployment. Refuses Fake Door tests for B2B enterprise.

  TRIGGER when: user says "how do I test this", "validate before building", "Fake Door", "Wizard of Oz", "Concierge MVP", "smoke test", "should I build a prototype", "fastest way to find out"; user is about to start engineering before `mvp-architect`; auto-fire from `problem-focus` when behavioral signal is needed before more interviews; auto-fire from `signal-audit` when recommendation is "behavioral test needed".

  SKIP: user has no hypothesis (route to `problem-focus`); user has converging signal and is ready to scope the real build (route to `mvp-architect`); user is post-launch and asking about iteration tests (route to `continuous-discovery`).
---

# Rapid Experiments

Designs behavioral validation experiments matched to the founder's archetype. Refuses B2B-enterprise Fake Door tests outright. Sets falsification pre-commitments before any experiment deploys — success criterion AND kill criterion in writing, no moving goalposts.

## When to Activate

- Phrases: "how do I test this," "validate before building," "fastest way to find out," "Fake Door," "Wizard of Oz," "concierge MVP," "smoke test," "should I build a prototype."
- Whenever the founder is about to start engineering, especially if `mvp-architect` hasn't been run.
- Auto-fire from `problem-focus` when the founder wants behavioral signal before more interviews.
- Auto-fire from `signal-audit` when the recommendation is "behavioral test needed."

## Red flags

| Founder behavior | Response |
|---|---|
| Wants Fake Door for B2B enterprise | Refuse. Use Concierge / paid pilot instead. Cite trust damage. |
| Polishes the experiment artifact for two weeks | Perfectionism-as-procrastination. Ship rough. |
| Treats the experiment as a real launch | Fake-launch syndrome. Reframe as info-gathering tool. |
| Sets success criterion of 50 signups when reference class is 5 | Inflating expectations. Force RCF: median of 3 comparable experiments × ~2x ceiling. |
| Wants to test 5 things at once | Refuse. One experiment tests ONE assumption. |
| Won't pre-commit kill criterion | Refuse to deploy. HARKing risk is too high. |
| Vibe-codes auth/PII/payments surface | Cite `ai-era-anti-patterns.md` Trap 6. Use Concierge instead. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — perfectionism-as-procrastination, fake-launch syndrome, HARKing.
- `${CLAUDE_PLUGIN_ROOT}/references/validation-techniques.md` — the technique matrix by archetype.
- `${CLAUDE_PLUGIN_ROOT}/references/landing-page-patterns.md` — for Fake Door / signup page design.
- `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md` — to specify expected signal weight before deployment.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Stripe Collison installation, DoorDash manual delivery, Dropbox video.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Eric Ries, PG *Do Things That Don't Scale*, Michael Seibel.
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — synthetic-user ban, vibe-vs-craft, wrapper trap.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md`; pull hypothesis, riskiest assumption, ICP, business archetype, MVP / Experiment Plan section. Write the experiment design (type, what it tests, success/kill criteria, timeline) to Active Experiments AND MVP / Experiment Plan. Session Log: `- [YYYY-MM-DD] rapid-experiments — designed <type> for <assumption>, deploy by <date>, success: <X>, kill: <Y>`.

## Process

1. **Read state.** Hypothesis, riskiest assumption, ICP, archetype. If hypothesis or riskiest assumption are missing, stop and route to `problem-focus`.

2. **Identify the riskiest assumption that blocks progress.** From `problem-focus` if it ran, otherwise extract from the current hypothesis. The experiment must test this *one specific* assumption. If the founder wants to test five things, refuse — design one test for the most-blocking one.

3. **Apply archetype guardrails** from `${CLAUDE_PLUGIN_ROOT}/references/validation-techniques.md`:
   - **B2B enterprise (Fortune 500, regulated):** Fake Door tests damage trust. The skill REFUSES to design one. Rationale: enterprise decision-makers assume you can't execute what you're claiming; when they discover the product doesn't exist after committing budget, the trust damage is irreversible. Use **Concierge MVP framed as "high-touch pilot" or "white-glove onboarding"** instead.
   - **B2B SMB / devtools:** Either Fake Door or Concierge. Fake Door acceptable if framed as "early access."
   - **Consumer SaaS / mobile:** Aggressive Fake Door / Wizard of Oz deployment.
   - **Hardware:** Pre-orders with refundable deposit (Kickstarter or landing page payment intent).
   - **Marketplace:** Solve one side at a time, manually. Start by being one of the sides yourself.
   - **AI products:** Wizard of Oz with humans behind the AI output (Magic SMS-style); validates demand cheaply, isolates "is the output valuable?" from "can we build the model?"

4. **Propose 2-3 experiment options.** For each:
   - **Type** (per archetype guardrails in step 3).
   - **What it tests** — the riskiest assumption, named explicitly.
   - **Time to deploy** — target 1-7 days.
   - **Signal quality** — expected weight per `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md` (with source-quality + deposit-size modifiers per `${CLAUDE_PLUGIN_ROOT}/references/validation-techniques.md`).
   - **Cost** — dollars and founder hours.

5. **Pre-commit success criterion.** "The experiment succeeds if X people do Y by date Z." Specific numbers. Examples:
   - Fake Door: "30 emails captured from ICP-targeted traffic by week 2."
   - Concierge: "3 customers pay $500 each for one week of manual service by week 3."
   - Pre-order: "10 refundable deposits at $50 each by week 2."

6. **Pre-commit kill criterion.** "We will kill or pivot if X people do not do Y by date Z." Symmetric to success. Both go into `STARTUP-STATE.md` BEFORE deployment.

7. **Build the artifact on request only.** Offer once: "I can build the [page / outreach batch / Concierge offer] for you. Say the word." Examples:
   - **Fake Door page:** generate HTML/React per `${CLAUDE_PLUGIN_ROOT}/references/landing-page-patterns.md`. Single CTA. Email + intent capture.
   - **Wizard of Oz frontend:** a realistic-looking UI; specify which backend operations the founder will manually perform.
   - **Concierge offer:** templated outreach message offering manual delivery with a specific price.
   - **Pre-order page:** landing page with Stripe payment intent capture and refund terms.

8. **Specify the interpretation plan BEFORE deployment.** What does success look like in quantitative terms? What does failure look like? Document it now — this prevents HARKing (Hypothesizing After Results are Known), where the founder rationalizes the outcome.

9. **Three named bias checkpoints** (per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`):

   **(a) Perfectionism check.** "Will you ship this rough, or are you about to polish for two weeks? The point is signal, not aesthetics." Refuse polish. Ship rough.

   **(b) Fake-launch syndrome check.** "Is this an information-gathering tool with a kill criterion, or are you treating it as a real launch with PR ambitions?" If real-launch framing, force scope-back. Experiments are NOT launches.

   **(c) Reference-class forecasting check** (Lovallo/Kahneman). "Name 3 comparable Fake Doors / Concierges in your archetype. What was their median signup rate / conversion / signal weight? Your estimate is X; the median is Y. Which do you actually believe?" Force outside-view forecast before setting success criterion.

10. **Surface Stripe's Collison Installation pattern.** Manually install the experiment for the first 5 users yourself. Do things that don't scale (PG essay). The data quality from white-glove onboarding is dramatically higher than self-serve at this stage.

11. **Update state.** Active Experiments with deployment date, success/kill criteria, deploy plan. MVP / Experiment Plan section.

12. **Recommend next.** Almost always: `signal-audit` after results are in (typically 1–2 weeks later). If results are converging, `mvp-architect` to scope the real build.

## Outputs

- Writes to state: Active Experiments (full design), MVP / Experiment Plan, Session Log.
- External resources to surface:
  - Eric Ries, *The Lean Startup* (MVP chapter).
  - Paul Graham, *Do Things That Don't Scale*.
  - YC video *How to Build an MVP* (Michael Seibel).
  - Dropbox's video MVP.
- **Artifacts on request only:** Fake Door landing page (React/HTML); Wizard of Oz frontend mockup; Concierge offer email batch; pre-order page; survey instrument. All optional; offer once per design discussion.

## Anti-Patterns Prevented

- B2B-enterprise Fake Door tests.
- Experiments without pre-committed kill criteria.
- Treating signups as evidence of demand (per `evidence-weighting-matrix.md`, signups without follow-up payment are weight 0.4).
- Building real product before any experiment runs.
- HARKing after results.
- Five-things-at-once experiments.

## Recommended Next Skills

`signal-audit` after deploy + result period. `mvp-architect` if signal supports build. `pivot-decision` if signal kills the hypothesis cleanly.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Direct on refusals (B2B-enterprise Fake Door, perfectionism, five-things-at-once). The kill criterion is the load-bearing artifact; insist on it.
