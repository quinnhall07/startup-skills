---
name: pricing-model
description: >
  (startup-skills) Use when the founder is thinking about pricing, revenue model, or monetization. Fires on "what should I charge," "free vs paid," "should I do freemium," or "should I charge upfront." Forces a commit to charging from day one. Refuses B2B freemium pre-PMF. Refuses free trials when money-back guarantees fit better. Writes the committed price into the state document.
---

# Pricing Model

Forces a commit to charging from day one. Selects revenue model by archetype. Refuses B2B freemium pre-PMF. Refuses free trials when money-back guarantees fit better. Computes the implied math (how many customers at this price to hit $1M ARR; how many conversations needed) and writes the committed price into the state document.

## When to Activate

- Phrases: "what should I charge," "how should I price," "free vs paid," "should I do freemium," "SaaS vs usage-based," "should I charge upfront," "money-back guarantee," "free trial," "what's the revenue model."
- Whenever the Pricing section of `STARTUP-STATE.md` is empty.
- Auto-fire before `mvp-architect` (pricing changes MVP shape) and before `outreach-engine` (pricing changes funnel math).

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md` — the rules and revenue models by archetype.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — freemium-as-cowardice, undercharging.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Stripe premium pricing, Scribd 4-year free experiment.
- `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md` — the implied conversion math at each price point.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Gustav, Lenny Rachitsky on pricing.

## State Document Protocol

Read `STARTUP-STATE.md`; pull ICP, archetype, hypothesis. Update Pricing section completely at completion. Session Log: `- [YYYY-MM-DD] pricing-model — committed <model> at <price>, first-paid-customer hypothesis: <X>`.

## Process

1. **Read state.** ICP, business archetype, hypothesis.

2. **Invoke `market-intel`** for competitor pricing if not already done. Pull 5–10 competitor price points across the closest comparable products.

3. **Surface the revenue models on the table** for this archetype, per `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md`:
   - **B2B SaaS:** subscription (most common); usage-based for devtools/infra; enterprise contracts for high-ACV.
   - **B2C subscription:** monthly subscription as default.
   - **Marketplace:** take-rate (15–20% start); listing fees if supply is constrained.
   - **One-time:** pre-orders, hardware, downloadable.
   - **Services-to-product:** charge as consulting first; productize once you've solved 5+ customers manually.
   - **Freemium:** only when free users generate genuine network/data value.

4. **Apply YC's pricing rules** from `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md` — these are non-negotiable in this skill:
   - **Charge from day one.** Cite Scribd's 4-year free experiment (lost 90% of users when they started charging, but went from $0 to a real business). Pre-revenue users are not validation.
   - **Price high enough to signal value.** Cite Stripe's premium pricing at launch.
   - **Free trials are almost always wrong.** Money-back guarantees usually better. The skill REFUSES to recommend a free trial without a specific reason that money-back can't satisfy.
   - **For B2B: avoid freemium pre-PMF.** Pollutes signal, burns runway. The skill REFUSES B2B freemium pre-PMF.
   - **For B2C: freemium can work IF free users generate genuine network/data value.** Otherwise treat as a tax.

5. **For each candidate price point, compute the implied math:**
   - Path to $1M ARR: $1M / (price × 12) = customers needed.
   - Cross-reference with `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md`: at typical 3–5% cold close rate, how many ICP conversations does that take?
   - Surface this math explicitly. The founder will see whether the price + funnel combo is feasible.

6. **Commit a price.** Single number, written into `STARTUP-STATE.md`. Do not allow "we'll figure it out later" — pricing changes the MVP shape and the outreach approach. If the founder won't commit, refuse to proceed; route back to `idea-pressure-test` or `problem-focus` because the value prop isn't sharp enough to price.

7. **Define the first-paid-customer hypothesis.** Who pays first? Why? What they get? Specific named ICP segment + amount + offer. Examples:
   - "Heads of sustainability at 5 named Series B-C tech startups pay $1,200/month for the v1 emissions dashboard."
   - "10 indie dental offices pay $79/month for the scheduling + insurance integration."

8. **Bias sentinel pass.** Especially:
   - **Freemium-as-cowardice.** Founder afraid to ask for money. Name it.
   - **Undercharging to "build initial momentum."** Destroys value perception. The $20/month founder cannot become the $200/month founder without losing the initial customers.
   - **"We'll figure pricing out later."** Refuse. Pricing decisions are not deferrable without consequence.

9. **Surface trade-offs honestly.** If the founder commits to a B2C price that needs 833 customers in 12 months, name it as the hard path. If they commit to an enterprise price needing 9 customers in 12 months, name that as a different hard path (long sales cycles, custom security review). Each archetype has a flavor of difficulty; choose the one with the founder's actual ICP relationships.

10. **Update state.** Pricing section fully populated: model, price, first-paid-customer hypothesis, money-back vs free-trial decision.

11. **Recommend next.**
    - `mvp-architect` if MVP scoping is next (pricing input changes scope).
    - `outreach-engine` if outreach is next (pricing input changes funnel math).
    - `discovery-coach` (PREPARE) if the price needs validation in the next batch of interviews (add a behavioral commitment ask at the new price).

## Outputs

- Writes to state: Pricing section (model, price, first-paid-customer hypothesis, money-back vs trial decision).
- External resources to surface:
  - YC video *How to Get Your First Customers* (Gustav, sections on pricing).
  - YC video *Setting KPIs and Goals* (Divya, sections on charging and PMF).
  - First Round Review pricing articles.
  - Lenny Rachitsky's newsletter on pricing.
- **Artifact on request only:** A Pricing Decision Memo (markdown) — captures the model, the chosen price, the math, the alternatives considered, the rationale. Offer once.

## Anti-Patterns Prevented

- B2B freemium pre-PMF.
- Free trials when money-back works better.
- "We'll figure it out later."
- Pricing below competitors to "build initial momentum."
- Pricing without computing the path to $1M ARR.
- Skipping the first-paid-customer hypothesis.

## Recommended Next Skills

Per step 11. Almost always `mvp-architect` or `outreach-engine` next.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Direct on refusals (freemium, free trial, deferring the decision). Cite Scribd and Stripe by name when the founder hedges. The committed number is the artifact; everything else is conversation.
