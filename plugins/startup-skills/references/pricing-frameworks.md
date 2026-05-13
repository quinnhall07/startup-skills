# Pricing Frameworks

Pricing decisions for pre-PMF and early-PMF startups. Synthesis of YC's *How to Get Your First Customers* (Gustav Alstromer), *Setting KPIs and Goals* (Divya Bhat), First Round Review pricing articles, and Lenny Rachitsky's pricing newsletters. Real anchors are cited where they ground a specific decision.

## The core rules

1. **Charge from day one.** Pre-revenue users are not validation. Scribd grew users free for four years; when they started charging, they lost 90% of their user base — but the surviving 10% became a real business. Don't repeat that. The willingness-to-pay test is the validation test.

2. **Price high enough to signal value.** Stripe was *more* expensive than competitors at launch (2.9% + $0.30 vs 2.5% + flat fee). Developers paid more because the experience was better — and the pricing told them in advance that the experience would be better. Underpricing tells customers your product is cheap.

3. **Free trials are almost always wrong.** Money-back guarantees are usually better. A 30-day free trial says "try it without commitment"; a 30-day money-back guarantee says "commit and get your money back if it doesn't work." The second filters tire-kickers; the first attracts them. Both have the same end state (refund if dissatisfied), but the conversational and behavioral framing is different.

4. **For B2B: avoid freemium.** Pre-PMF freemium pollutes signal and burns runway. The free users are not your customer; they're noise that consumes support, biases your roadmap toward features they want, and never converts at the rate the freemium math requires.

5. **For B2C: freemium can work, conditional.** Only if free users generate genuine *network* or *data* value. Slack's free tier worked because free teams became viral seeds inside companies that eventually paid. Dropbox's free tier worked because free users referred others. If the free user creates no value for the eventual paying customer, freemium is a tax.

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
