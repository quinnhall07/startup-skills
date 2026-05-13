---
name: rapid-experiments
description: Use when the founder needs to test an assumption fast, before committing to building real product. Fires on phrases like "how do I test this," "validate before building," "fastest way to find out," "Fake Door," "Wizard of Oz," "concierge MVP," "smoke test," or whenever the founder is about to start engineering. Designs a Fake Door, Wizard of Oz, or Concierge MVP based on the hypothesis and market geometry. The system REFUSES to authorize engineering for B2B enterprise without a Concierge MVP first (Fake Door tests damage enterprise trust). For consumer/devtools, aggressively deploys Fake Door / Wizard of Oz. Sets falsification pre-commitments before deployment.
---

# Rapid Experiments

Designs behavioral validation experiments matched to the founder's archetype. Refuses B2B-enterprise Fake Door tests outright. Sets falsification pre-commitments before any experiment deploys — success criterion AND kill criterion in writing, no moving goalposts.

## When to Activate

- Phrases: "how do I test this," "validate before building," "fastest way to find out," "Fake Door," "Wizard of Oz," "concierge MVP," "smoke test," "should I build a prototype."
- Whenever the founder is about to start engineering, especially if `mvp-architect` hasn't been run.
- Auto-fire from `problem-focus` when the founder wants behavioral signal before more interviews.
- Auto-fire from `signal-audit` when the recommendation is "behavioral test needed."

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — perfectionism-as-procrastination, fake-launch syndrome, HARKing.
- `references/validation-techniques.md` — the technique matrix by archetype.
- `references/landing-page-patterns.md` — for Fake Door / signup page design.
- `references/evidence-weighting-matrix.md` — to specify expected signal weight before deployment.
- `references/case-studies.md` — Stripe Collison installation, DoorDash manual delivery, Dropbox video.
- `references/external-resources.md` — Eric Ries, PG *Do Things That Don't Scale*, Michael Seibel.

## State Document Protocol

Read `STARTUP-STATE.md`; pull hypothesis, riskiest assumption, ICP, business archetype, MVP / Experiment Plan section. Write the experiment design (type, what it tests, success/kill criteria, timeline) to Active Experiments AND MVP / Experiment Plan. Session Log: `- [YYYY-MM-DD] rapid-experiments — designed <type> for <assumption>, deploy by <date>, success: <X>, kill: <Y>`.

## Process

1. **Read state.** Hypothesis, riskiest assumption, ICP, archetype. If hypothesis or riskiest assumption are missing, stop and route to `problem-focus`.

2. **Identify the riskiest assumption that blocks progress.** From `problem-focus` if it ran, otherwise extract from the current hypothesis. The experiment must test this *one specific* assumption. If the founder wants to test five things, refuse — design one test for the most-blocking one.

3. **Apply archetype guardrails** from `references/validation-techniques.md`:
   - **B2B enterprise (Fortune 500, regulated):** Fake Door tests damage trust. The skill REFUSES to design one. Use Concierge MVP framed as "high-touch pilot" or "white-glove onboarding."
   - **B2B SMB / devtools:** Either Fake Door or Concierge. Fake Door acceptable if framed as "early access."
   - **Consumer SaaS / mobile:** Aggressive Fake Door / Wizard of Oz deployment.
   - **Hardware:** Pre-orders with refundable deposit (Kickstarter or landing page payment intent).
   - **Marketplace:** Solve one side at a time, manually. Start by being one of the sides yourself.

4. **Propose 2–3 experiment options.** For each:
   - **Type** (Fake Door / Wizard of Oz / Concierge / Pre-order / Cold outreach batch).
   - **What it tests** — the riskiest assumption, named explicitly.
   - **Time to deploy** — target 1–7 days.
   - **Signal quality** — expected weight per `references/evidence-weighting-matrix.md`. E.g., Fake Door produces 0.4 per email; Concierge with payment produces 0.8–1.0; Pre-order with refundable deposit produces 0.8.
   - **Cost** — dollars and founder hours.

5. **Pre-commit success criterion.** "The experiment succeeds if X people do Y by date Z." Specific numbers. Examples:
   - Fake Door: "30 emails captured from ICP-targeted traffic by week 2."
   - Concierge: "3 customers pay $500 each for one week of manual service by week 3."
   - Pre-order: "10 refundable deposits at $50 each by week 2."

6. **Pre-commit kill criterion.** "We will kill or pivot if X people do not do Y by date Z." Symmetric to success. Both go into `STARTUP-STATE.md` BEFORE deployment.

7. **Build the artifact on request only.** Offer once: "I can build the [page / outreach batch / Concierge offer] for you. Say the word." Examples:
   - **Fake Door page:** generate HTML/React per `references/landing-page-patterns.md`. Single CTA. Email + intent capture.
   - **Wizard of Oz frontend:** a realistic-looking UI; specify which backend operations the founder will manually perform.
   - **Concierge offer:** templated outreach message offering manual delivery with a specific price.
   - **Pre-order page:** landing page with Stripe payment intent capture and refund terms.

8. **Specify the interpretation plan BEFORE deployment.** What does success look like in quantitative terms? What does failure look like? Document it now — this prevents HARKing (Hypothesizing After Results are Known), where the founder rationalizes the outcome.

9. **Bias sentinel pass.** Especially:
   - **Perfectionism-as-procrastination.** The founder will want to polish the experiment artifact. Refuse — ship rough. The point is signal, not aesthetics.
   - **Fake-launch syndrome.** Treating the experiment as a real launch. It's not. It's an information-gathering tool with a kill criterion.
   - **Inflating expected outcomes.** The founder may set the success criterion at "50 signups in week 1" when their realistic ceiling is 5. Force reference-class forecasting per `references/bias-sentinel.md`.

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

`signal-audit` after deploy + result period. `mvp-architect` if signal supports build. `pivot-decision` (v0.4) if signal kills the hypothesis cleanly.

## Tone

Per `references/tone-and-stance.md`. Direct on refusals (B2B-enterprise Fake Door, perfectionism, five-things-at-once). The kill criterion is the load-bearing artifact; insist on it.
