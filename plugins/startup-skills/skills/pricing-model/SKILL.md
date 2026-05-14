---
name: pricing-model
description: |
  Force a price commit (one number, written to state) before MVP scoping or outreach. Selects revenue model by archetype. Refuses B2B freemium pre-PMF. Refuses free trials when money-back works better. Applies Ramanujam's WTP-before-build framing. AI-aware: surfaces token-cost economics, per-seat erosion, outcome-based pricing.

  TRIGGER when: user says "what should I charge", "how should I price", "free vs paid", "should I do freemium", "SaaS vs usage-based", "should I charge upfront", "money-back guarantee", "free trial", "what's the revenue model"; Pricing section of `STARTUP-STATE.md` is empty; auto-fire BEFORE `mvp-architect` (pricing changes MVP shape) and BEFORE `outreach-engine` (pricing changes funnel math).

  SKIP: pricing is already committed in state AND user is asking about scaling/optimization (route to `pmf-audit` for tier expansion); user is asking about fundraising terms (out of scope); user wants to A/B test prices post-launch (route to `continuous-discovery`).
---

# Pricing Model

Forces a commit to charging from day one. Selects revenue model by archetype. Refuses B2B freemium pre-PMF. Refuses free trials when money-back guarantees fit better. Computes the implied math (how many customers at this price to hit $1M ARR; how many conversations needed) and writes the committed price into the state document.

## HARD-GATE — refuse to defer the decision:

- [ ] User commits a single specific price (one number) to `STARTUP-STATE.md` Pricing section, OR
- [ ] User explicitly states the archetype-exception reason (consumer with viral loop / marketplace pre-liquidity / strong viral-coefficient bottoms-up dev tool)

**If neither**: refuse to proceed. "We'll figure pricing out later" is not acceptable here. Pricing decisions are not deferrable without consequence — they change MVP shape and outreach funnel math.

If founder pushes back: cite Ramanujam's Minivation failure mode. ~90% of pre-PMF B2B founders price too low; the second most expensive mistake is deferring the decision and building the wrong product against an unknown price.

## When to Activate

- Phrases: "what should I charge," "how should I price," "free vs paid," "should I do freemium," "SaaS vs usage-based," "should I charge upfront," "money-back guarantee," "free trial," "what's the revenue model."
- Whenever the Pricing section of `STARTUP-STATE.md` is empty.
- Auto-fire before `mvp-architect` (pricing changes MVP shape) and before `outreach-engine` (pricing changes funnel math).

## Red flags

| Founder claim | Response |
|---|---|
| "Let's start free, charge later" (B2B) | Refuse unless k > 0.4 AND ACV < $5K AND COGS < $0.50/free-user/mo. |
| Free trial without specific reason money-back can't satisfy | Replace with money-back guarantee. |
| Pricing per-seat for AI-product with token COGS | Surface erosion math. Default to hybrid or outcome-based. |
| "We'll figure pricing out later" | Refuse. Force the commit. |
| Pricing below all competitors "for momentum" | Refuse. Destroys value perception. Discount scope or term, never list price. |
| Founder afraid to state a number | Surface freemium-as-cowardice. The number IS the validation test. |
| Single tier, no segmentation | Add 3 tiers (1 : 2.5 : 6 ratio) post-PMF; one tier pre-PMF is fine. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md` — the rules and revenue models by archetype.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — freemium-as-cowardice, undercharging.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Stripe premium pricing, Scribd 4-year free experiment.
- `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md` — the implied conversion math at each price point.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Gustav, Lenny Rachitsky on pricing.
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — token-cost denial trap.
- `${CLAUDE_PLUGIN_ROOT}/references/growth-loops.md` — NRR, CAC payback, unit economics.
- `${CLAUDE_PLUGIN_ROOT}/references/distribution-by-archetype.md` — pricing × archetype × distribution fit.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md`; pull ICP, archetype, hypothesis. Update Pricing section completely at completion. Session Log: `- [YYYY-MM-DD] pricing-model — committed <model> at <price>, first-paid-customer hypothesis: <X>`.

## Process

1. **Read state.** ICP, business archetype, hypothesis.

2. **Pull competitor pricing.** Check `STARTUP-STATE.md` Research Cache. If `market-intel` was last run on this topic <30 days ago, cite cached results. Otherwise, invoke `market-intel` OR manually pull 5-10 competitor price points via: LinkedIn Sales Navigator, Product Hunt, G2, or direct company websites. Both paths acceptable.

3. **Surface the revenue models on the table** for this archetype, per `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md`:
   - **B2B SaaS:** subscription (most common); usage-based for devtools/infra; enterprise contracts for high-ACV.
   - **B2C subscription:** monthly subscription as default.
   - **Marketplace:** take-rate (15–20% start); listing fees if supply is constrained.
   - **One-time:** pre-orders, hardware, downloadable.
   - **Services-to-product:** charge as consulting first; productize once you've solved 5+ customers manually.
   - **Freemium:** only when free users generate genuine network/data value.

4. **Apply pricing rules** from `${CLAUDE_PLUGIN_ROOT}/references/pricing-frameworks.md`. Non-negotiable in this skill:
   - **Ramanujam's WTP-before-build** (the master framing). Don't bolt price onto product; design product around the price. The Minivation trap (right product, priced too low) catches 90% of pre-PMF B2B founders.
   - **Charge from day one** for B2B with bounded users + measurable value. Cite Scribd's 4-year free experiment. **Boundary exceptions**: consumer (massive funnel needed), marketplace (liquidity first), strong viral-coefficient products.
   - **Price high enough to signal value.** Stripe premium pricing at launch.
   - **Free trials almost always wrong.** Money-back guarantees usually better.
   - **B2B freemium: refused pre-PMF** unless k > 0.4 AND ACV < $5K AND COGS < $0.50/free-user/mo.
   - **AI products: per-seat is eroding.** Default to hybrid (platform fee + meter) or outcome-based (10-30% of human-replaced cost, à la Intercom Fin's $0.99/resolution). Per `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` Trap 3 (token-cost denial).

5. **For each candidate price point, compute the implied math:**
   - Path to $1M ARR: $1M / (price × 12) = customers needed.
   - Cross-reference with `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md`: at typical 3–5% cold close rate, how many ICP conversations does that take?
   - Surface this math explicitly. The founder will see whether the price + funnel combo is feasible.

5b. **AI-product gross-margin instrumentation (mandatory if AI-product).** Before committing price, set up: cost-per-request tracking. AI products run 30-60% COGS-to-revenue vs <10% traditional SaaS. Heavy users silently destroy margins. Write to `STARTUP-STATE.md` AI Economics section (schema v2): expected cost per active user, target LTV/inference-cost ratio (≥3x).

6. **Commit a price.** Single number, written into `STARTUP-STATE.md`. Do not allow "we'll figure it out later" — pricing changes the MVP shape and the outreach approach. If the founder won't commit, refuse to proceed; route back to `idea-pressure-test` or `problem-focus` because the value prop isn't sharp enough to price.

7. **Define the first-paid-customer hypothesis.** Who pays first? Why? What they get? Specific named ICP segment + amount + offer. Examples:
   - "Heads of sustainability at 5 named Series B-C tech startups pay $1,200/month for the v1 emissions dashboard."
   - "10 indie dental offices pay $79/month for the scheduling + insurance integration."

8. **Bias sentinel pass:**
   - **Freemium-as-cowardice.** If founder suggests freemium for B2B but can't state why free users generate genuine network or data value, name it directly: "Freemium is a tax on engineering unless free users unlock network effects or data value. You haven't articulated either. So this is fear of asking for money, not a strategy. Let's commit to a paid model instead."
   - **Undercharging "for momentum."** Destroys value perception. The $20/mo founder cannot become the $200/mo founder without losing original customers.
   - **"We'll figure it out later."** Refuse. Pricing decisions are not deferrable.
   - **Minivation** (Ramanujam): right product, right market, priced too low. The dominant pre-PMF founder mistake. Force PSM survey if WTP signal is weak.

9. **Surface trade-offs honestly.** If the founder commits to a B2C price that needs 833 customers in 12 months, name it as the hard path. If they commit to an enterprise price needing 9 customers in 12 months, name that as a different hard path (long sales cycles, custom security review). Each archetype has a flavor of difficulty; choose the one with the founder's actual ICP relationships.

10. **Update state.** Pricing section fully populated: model, price, first-paid-customer hypothesis, money-back vs free-trial decision.

11. **Recommend next.**
    - If MVP scoping is next: `ai-mvp-stack-selection` (if AI-product) → `mvp-architect`.
    - If outreach is next: `outreach-engine`.
    - If pricing needs validation in next batch of interviews: `discovery-coach` (PREPARE) — add a behavioral commitment ask at the new price.
    - For AI-product: ensure token-cost economics are instrumented before MVP scoping.

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
