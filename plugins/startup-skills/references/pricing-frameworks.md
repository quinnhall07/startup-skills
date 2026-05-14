# Pricing Frameworks

Pricing decisions for pre-PMF and early-PMF startups. Synthesis of YC's *How to Get Your First Customers* (Gustav Alstromer), *Setting KPIs and Goals* (Divya Bhat), First Round Review pricing articles, and Lenny Rachitsky's pricing newsletters. Real anchors are cited where they ground a specific decision.

## The core rules

1. **Charge from day one.** Pre-revenue users are not validation. Scribd grew users free for four years; when they started charging, they lost 90% of their user base — but the surviving 10% became a real business. Don't repeat that. The willingness-to-pay test is the validation test.

2. **Price high enough to signal value.** Stripe was *more* expensive than competitors at launch (2.9% + $0.30 vs 2.5% + flat fee). Developers paid more because the experience was better — and the pricing told them in advance that the experience would be better. Underpricing tells customers your product is cheap.

3. **Free trials are almost always wrong.** Money-back guarantees are usually better. A 30-day free trial says "try it without commitment"; a 30-day money-back guarantee says "commit and get your money back if it doesn't work." The second filters tire-kickers; the first attracts them. Both have the same end state (refund if dissatisfied), but the conversational and behavioral framing is different.

4. **For B2B: avoid freemium.** Pre-PMF freemium pollutes signal and burns runway. The free users are not your customer; they're noise that consumes support, biases your roadmap toward features they want, and never converts at the rate the freemium math requires.

5. **For B2C: freemium can work, conditional.** Only if free users generate genuine *network* or *data* value. Slack's free tier worked because free teams became viral seeds inside companies that eventually paid. Dropbox's free tier worked because free users referred others. If the free user creates no value for the eventual paying customer, freemium is a tax.

## Ramanujam — Monetizing Innovation (the master framing)

Attribution: Madhavan Ramanujam, *Monetizing Innovation* (Simon-Kucher, 2016). 72% of innovations miss financial targets. Cause: companies design the product, then bolt on a price. Fix: **design the product around the price**. Have the willingness-to-pay (WTP) conversation *before* writing code. See [Marketing Journal summary](https://www.marketingjournal.org/monetizinginnovation/).

### The four innovation/pricing failure modes
1. **Feature Shocks** — over-stuffed product, customers won't pay for the bloat.
2. **Minivations** — right product, right market, **priced too low**. (Most pre-PMF B2B founders live here.) Reframe: "charge from day one" is a corollary of "design around the price; don't undershoot it."
3. **Hidden Gems** — blockbuster product never brought to market because it sits outside the core.
4. **Undeads** — shipped products with zero demand; should have been killed during WTP interviews.

### Pricing-led development process
- Talk to 30-100 target customers about WTP for each feature *bundle*, not the whole product.
- Segment by WTP, not demographics — willingness-to-pay clusters reveal natural tiers.
- Use WTP as a build/cut gate; if WTP < target margin, kill the feature.

## Patrick Campbell — WTP research methodology (Van Westendorp PSM)

See [Acquired FM pricing episode with Patrick Campbell](https://www.acquired.fm/episodes/pricing-everything-you-always-wanted-to-know-but-were-afraid-to-ask-with-profitwell-ceo-patrick-campbell).

Four-question survey:
1. At what price is it *so expensive* you would never buy? (upper bound)
2. At what price is it *expensive but you'd still consider*? (premium)
3. At what price is it *a bargain*? (value floor)
4. At what price is it *so cheap you'd doubt quality*? (lower bound)

Plot cumulative curves; intersections give **Optimal Price Point (OPP)** and **Indifference Price Point (IPP)**. Accuracy ±20-25%.

### Sample size
- N≥40 per persona for directional.
- N≥150 for stable curves.
- Run by **persona** ("quantified buyer personas"). Never blend WTP across segments — averages lie.

### Layer Conjoint Analysis for feature-level WTP
Force-rank trade-offs across hypothetical bundles to isolate marginal value per feature.

## AI product pricing 2025-2026

See [Bain: per-seat software pricing isn't dead, but new models are gaining steam](https://www.bain.com/insights/per-seat-software-pricing-isnt-dead-but-new-models-are-gaining-steam/) and the [Bessemer AI Pricing and Monetization Playbook](https://www.bvp.com/atlas/the-ai-pricing-and-monetization-playbook).

### Why per-seat is breaking (not dead, but eroding)
- Agents replace seats. If one Fin agent resolves what 5 humans did, who's the "seat"?
- COGS is variable (token cost) — fixed per-seat pricing inverts unit economics under heavy users.
- Bain/Sierra/Pilot data: per-seat AI products show **40% lower gross margins** and **2.3× higher churn** than usage/outcome pricing.

### Four AI pricing patterns in market

| Model | Unit | Examples | Best for |
|---|---|---|---|
| **Consumption / token** | Tokens, API calls | OpenAI API, Anthropic API | Infra / dev tools |
| **Credit-based** | Abstract credits, model-weighted | Cursor ($20 = $20 credits), Copilot (300 premium req/mo) | Mixed-model products |
| **Outcome-based** | Resolved ticket, booked meeting, recovered cart | Intercom Fin ($0.99/resolution), Sierra (per outcome) | Agent products with measurable outcomes |
| **Hybrid** | Platform fee + meter | Most modern SaaS+AI | Default for new launches |

### Token COGS reality check
AI products run **30-60% COGS-to-revenue** (vs <10% traditional SaaS). The "80% gross margin SaaS rule" is broken — AI SaaS lives at 50-70%.

Founders must price *value* not *cost*, but must instrument *cost per request* or die on a heavy user.

### Outcome-pricing formula (Sierra pattern)
Charge **10-30% of human-replaced cost**. Define an outcome contract (e.g. "resolved" = customer confirms or no reopen in 7 days). Refund on failure. See [Sierra: outcome-based pricing for AI agents](https://sierra.ai/blog/outcome-based-pricing-for-ai-agents).

For full AI-era anti-patterns including token-cost denial trap, load `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md`.

## Boundary conditions for "charge from day one"

Existing rule preserved: charge from day one is correct for B2B with bounded users + measurable value.

**Wrong / risky when:**
- **Consumer products** where conversion economics require massive top-of-funnel (a16z, Seibel both note this).
- **Marketplaces / two-sided networks**: liquidity must precede monetization on at least one side.
- **Strong viral-coefficient products** (Slack, Figma, Notion early days): viral spread is the moat — paywalling kills the loop.
- **Bottoms-up dev tools** with strong viral coefficient (k > 0.5).

For these: charge as soon as you've proven the loop, not before.

## B2B freemium gates (when freemium works)

Require **ALL** of:
- Viral coefficient k > 0.4 (each user pulls ≥0.4 new users).
- Sub-$1K ACV.
- Self-serve activation, low marginal COGS per free user (<$0.50/mo).
- Clear "free tier ceiling" forces upgrade (storage, seats, runs).

**Benchmark:** top-quartile B2B freemium converts 5-8%; median 2.6%. If you're not modeling a path to 5%+ within 12 months, don't launch freemium.

**Mental model:** "Free tier is a marketing line item, not a product tier." Budget it as CAC. If freemium CAC-equivalent exceeds paid CAC, kill it.

## The anti-discount rule

Discount **scope** or **term length**, never **list price**. Each 20% discount requires 25% more volume to break even. The $20/month founder cannot become the $200/month founder without losing the original customers.

## Tier ratio rule of thumb

1 : 2.5 : 6 (Starter : Pro : Enterprise) approximates median B2B SaaS. Adjust based on WTP clusters from PSM.

## Rule-of-thumb formulas

- **Value-based price** = 10-25% of customer's quantified gain (cost saved + revenue added).
- **AI outcome price** = (human-cost-replaced) × 0.10 to 0.30.
- **First-customer price** = whatever they'll sign for **minus 0%**. Raise on customer #6.
- **Path to $1M ARR**: $1M / (price × 12) = customers needed. Cross-reference `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md`.

## Revenue models by archetype

| Archetype | Most common model | When to consider alternatives |
|---|---|---|
| B2B SaaS | Subscription (monthly or annual) | Usage-based when value clearly scales with consumption (devtools, infra, AI APIs) |
| B2C subscription | Monthly subscription | Annual with discount once retention is proven |
| Marketplace | Take-rate (10–30% typical) | Listing fees when supply is the constrained side |
| One-time | Hardware, downloadable, course | Hybrid (one-time + maintenance subscription) once renewal is justified |
| Services-to-product | Charge as consulting first; productize after you've solved 5+ customers manually | The pivot moment is when the services delivery becomes repetitive enough to template |
| Freemium | Only when free users create network/data value | Default to paid-only pre-PMF |

## Pricing the first version

A useful starting point: charge the price you think is right, multiplied by 1.5. Customers will push back; that's data. If nobody pushes back, the price was too low.

For B2B: start with monthly subscription unless the value clearly scales with usage. Recommended starting tiers: a single tier at the price point you've committed to. Multiple tiers can come after PMF.

For B2C: a single price. Tier complexity destroys early-stage conversion.

For marketplace: start with take-rate at 15–20%. Adjust based on what each side will tolerate.

## Math — what's the path to $1M ARR?

This sets the floor on pricing. Working backwards:

- **$1M ARR / $100/month = 833 paying customers needed.** Realistic for B2C subscription or low-end SMB SaaS.
- **$1M ARR / $1,000/month = 84 paying customers needed.** Realistic for mid-market SaaS.
- **$1M ARR / $10,000/month = 9 paying customers needed.** Realistic for enterprise SaaS.

The 9-customer enterprise path is dramatically easier than the 833-customer B2C path, even though the dollar target is identical. Underpricing locks the founder into the harder path; correctly-pricing opens the easier one.

Cross-reference: `references/sales-funnel-math.md` for the conversion rates that determine how many conversations each path requires.

## Free trial vs money-back guarantee — when each fits

| Choose | When |
|---|---|
| **Money-back guarantee** | The default for almost all SaaS, especially B2B. Filters tire-kickers. Forces customer to evaluate against value, not just check it out. |
| **Free trial (no card required)** | Almost never. Reserves: pure consumer products with extreme low-touch onboarding (e.g., a calendar add-in where setup is 30 seconds). |
| **Free trial (card required)** | Acceptable middle ground when the activation experience is multi-day and money-back is operationally hard. Convert automatically at end of trial unless cancelled. |

## Common bias firings

- **Freemium-as-cowardice.** Founder afraid to ask for money, so they default to free. Name it: charging is the test.
- **Undercharging to "build initial momentum."** This destroys value perception. Customers attribute price to quality. A $20/month tool is treated as a $20/month tool; you cannot later become a $200/month tool without losing the original customers.
- **"We'll figure it out later."** Pricing changes the MVP shape. The product you build for $99/month is different from the product you build for $9,900/year. Commit now.
- **Skipping the willingness-to-pay test in customer interviews.** Pricing should appear in the closing question of every Mom-Test-aligned interview — but as a behavioral ask ("Would you commit $500 for a one-month pilot?"), not a hypothetical ("Would you pay $X?").

## Real anchors

- **Stripe.** Premium pricing at launch. Did not compete on price.
- **Scribd.** Free for four years, then started charging, lost 90% of users, ended with a real business. Lesson: charging is the test. Doing it earlier saves four years.
- **Superhuman.** $30/month for an email client at a time when Gmail was free. Worked because the HXC (founders / execs / power-users) valued speed above the price.
- **Notion.** Freemium that worked — free users became viral seeds and the conversion rate to paid teams was high enough to justify the support cost.

## Where this is used

`pricing-model` walks through these rules with the founder. `outreach-engine` uses the committed price to compute funnel math. `mvp-architect` uses the price to shape what v1 must do.
