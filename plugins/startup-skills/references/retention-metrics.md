# Retention Metrics — Cohort Diagnosis for Pre- and Post-PMF

Diagnose and fix cohort retention. Retention is the missing diagnostic between "Sean Ellis survey says 35%" and "we still don't grow" — the score measures stated love; cohort curves measure revealed behavior, and the second is the one that compounds.

Attributions: Casey Winters ([Guide to Finding PMF](https://www.caseyaccidental.com/p/caseys-guide-to-finding-product-market-fit), [What is Good Retention](https://caseyaccidental.com/what-is-good-retention)); Andrew Chen ([The Power User Curve](https://andrewchen.com/power-user-curve/)); a16z ([Power User Curve](https://a16z.com/the-power-user-curve-the-best-way-to-understand-your-most-engaged-users/)); Brian Balfour / Reforge ([PMF Collapse](https://www.reforge.com/blog/product-market-fit-collapse)); Mercury ([Measuring PMF](https://mercury.com/blog/measuring-product-market-fit)).

## Definitions — non-negotiable

**Cohort retention** = % of a day-1 cohort still *active* on day N. Not MAU/DAU. Not "logged in." Cohort means same signup week, tracked forward.

**Active** = performed the *core action* at least once in the window. The core action is product-specific and binary:
- Pinterest: saved a pin
- Grubhub: placed an order
- Slack: sent a message in a shared channel (not a DM to self)
- Figma: edited a file with ≥1 collaborator
- Notion: created or edited a page in a shared workspace

If you cannot name the core action in one sentence, the retention dashboard is meaningless. Fix the definition before fixing the curve.

## Cohort retention benchmarks by archetype

Numbers are floors for "plausible PMF," not targets. Below the floor, scaling and paid acquisition are frozen.

| Archetype | D7 | D28 | D90 | PMF shape |
|---|---|---|---|---|
| Consumer mobile | 20–35% | 8–15% | 4–8% | Flat by D60 = PMF |
| Consumer web | 25–40% | 12–20% | 6–12% | Flat by D60–D90 |
| B2B SaaS | 40–60% | 25–40% | 15–30% | NRR matters more than D90 post-month-3 |
| Devtools (PLG) | 35–50% | 20–35% | 12–25% | Flat by D90, then expansion |
| Marketplace (demand-side) | 15–25% | 5–10% | 2–5% | Frequency-dependent; weight by category purchase cadence |
| Games | 20–35% | 5–10% | 1–3% | D1/D7/D30 industry standard |

If the founder reports numbers materially above these benchmarks on a small cohort (<200 users), suspect measurement error before celebrating. Common bug: counting "logged in" as active.

## The smile-vs-frown curve (Andrew Chen / a16z)

Plot the histogram of users by *number of active days* in a 28-day window. Buckets: 1, 2, 3, …, 27, 28.

- **Smile (healthy).** Mass at 1 (trialers), small middle, fat tail at 27–28 (power users who use it every day). The right-side tail is the population that drives WoM, retention, and monetization.
- **Frown (anti-PMF).** Mass piled in the middle (users active 3–10 days/month), thin or absent tail at 27–28. Looks like "engagement" in aggregate; is actually no one who can't live without you.

Andrew Chen's three "magic metrics" for PMF — all three required, not any one:
1. Cohort retention curve **flattens** (does not asymptote to zero).
2. Active users / registered users **> 25%**.
3. Power user curve is **smile-shaped**, not frown-shaped.

Facebook anchor: 60%+ of MAUs return daily. That is the tail end of the smile when a category-defining product hits PMF. Most products will never see this; the shape, not the magnitude, is the diagnostic.

## Cohort retention curve shape over time (Casey Winters)

Plot cohort retention by signup month: % of each monthly cohort performing the key action in month 1, 2, 3, 4, … Each cohort is a line.

- **PMF.** Lines decay then **flatten by month 3**. The flat asymptote is the long-term retained share.
- **No PMF.** Lines continue decaying past month 3 toward zero. There is no asymptote.

Casey's rule: if curves do not flatten by month 3, the product does not retain. Adding acquisition spend pours water into a bucket whose hole is the entire bottom.

## Activation analysis — the day-1 lookback

Of users who came back on day 7, what did they do on **day 1** that churned users didn't? Run the cross-tab on every event in the day-1 session.

The pattern is usually obvious: retained users hit the **core value moment** on day 1. Churned users saw the signup confirmation and bounced. The "aha event" is whatever predicts day-7 return with the highest lift.

Classic examples:
- Facebook: 7 friends in 10 days.
- Slack: 2,000 messages sent by a team.
- Dropbox: 1 file in 1 folder on 1 device.

The onboarding redesign target is "get users to the aha event in session 1." Anything else in onboarding is decoration.

## Brian Balfour PMF Treadmill / Collapse (Reforge)

PMF is not a static achievement. Customer expectations rise — and under AI substitution, they rise exponentially. A product that had PMF in 2022 can lose it in 2024 without changing a line of code.

Reference cases:
- **Chegg.** Lost ~87% of market cap (peak ~$12B → ~$1B by 2024) as ChatGPT reset student expectations for homework help. Same product, same users, expectations re-baselined.
- **Stack Overflow.** Traffic and question volume dropped sharply post-ChatGPT (publicly reported declines of ~35–50% on key engagement metrics). The JTBD "get a working code snippet" was substituted in <30 seconds.

**AI-substitution test.** Is your core JTBD now achievable in ChatGPT/Claude in <30 seconds with a generic prompt? If yes, you are on the treadmill. The retention curve will start decaying from the right edge (power users first — they substitute fastest).

## Anti-PMF retention signals

| Founder claim | What's actually happening | Diagnostic |
|---|---|---|
| "Customers say they love it but don't refer" | Stated love, no behavior. Sean Ellis score is inflated by politeness. | Pull actual referrer share. <30% organic acquisition = no real love. |
| "High activation, low retention" | Onboarding hacks dopamine; product doesn't deliver. | D30 / D1 ratio. If <0.15 for B2B SaaS or <0.10 for consumer, the product is a slot machine, not a tool. |
| "Churn reasons = 'got busy / priorities shifted'" | Polite for "not valuable enough." Customers don't quit oxygen because they got busy. | Re-interview churned users with Mom Test framing. Ask what they're doing *instead*. |
| "Champion-dependent renewals" | Single-threaded sale. Product hasn't earned organizational love. | If champion leaving = churn, the product is a personal preference, not infrastructure. |
| "Sales cycles lengthening" | Positioning is breaking; competition or expectations shifted. | Mercury data: healthy PMF cycles **shrink 20–40% over 90 days**. Lengthening cycles = PMF erosion. |

## AI-product-specific retention (token-cost-aware)

Inference cost makes traditional SaaS retention math wrong. A retained user can destroy you faster than a churned one.

- **LTV / inference-cost ratio ≥ 3x.** Target floor. If a power user's annual COGS exceeds 1/3 of their ARR, unit economics collapse at scale — and power users are the ones you most want to retain.
- **Margin per active user, trend by cohort age.** Should *improve* as cohorts mature (better prompts, cached context, model downgrades). Flat or declining margin per active user = no real moat; you are subsidizing usage indefinitely.
- **Cost-per-retained-user, not cost-per-signup.** CAC on signups is the wrong KPI for AI products. CPRU = (acquisition spend) / (users still active at D90). It captures the joint cost of acquisition + the inference burn during the trial window.

## Magic (case study)

Magic launched February 2015 as an SMS concierge: text any request, a human fulfills it. Viral Hacker News launch, massive press, signups exploded in the first week. Within months it became clear that day-4 retention was below 5% and unit economics didn't work — each fulfillment cost more than users would pay. The company effectively shut down the consumer concierge and pivoted (eventually to staffing/services). **Lesson: viral attention is not retention.** A launch-week graph that looks like PMF is curiosity. Watch week 4, not week 1. The Magic founders did the right thing — they killed it rather than scaling a hole.

## Where this is used

Loaded by `pmf-audit` (cohort curve is the behavioral counterpart to the Ellis score), `signal-audit` (refuses to count launch spikes or vanity engagement as evidence), `pivot-decision` (flat-by-month-3 vs. decaying-past-month-3 is the continue/pivot input), `continuous-discovery` (activation cross-tab feeds the next round of interviews), and `mvp-architect` (defines the core action and aha event before any feature work).
