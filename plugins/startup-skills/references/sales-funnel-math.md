# Sales Funnel Math

Math the founder must do before any outreach batch. Without it, the outreach volume estimates are fantasies. Source: Gustav Alstromer's *How to Get Your First Customers*, Lenny Rachitsky's first-customer benchmark posts, sales literature on cold-outbound conversion.

## Realistic conversion rates

For founder-led early-stage outreach (NOT a sales team, NOT post-PMF):

| Stage | Cold | Warm intro | Inbound (Fake Door, referrals) |
|---|---|---|---|
| Email open | 30–50% | 70–90% | 50–70% |
| Reply | 5–15% | 30–60% | 20–40% |
| Scheduled call | 2–8% | 25–50% | 15–30% |
| Show up to call | 70–80% of scheduled | 90% | 80% |
| Becomes paying customer | 3–5% of pipeline | 15–25% | 10–20% |

These are reality, not the optimistic numbers founders hope for. The 3–5% cold-to-paid rate is *typical for a founder doing the work themselves with good targeting*. Below 2% means either the targeting is wrong (ICP mismatch) or the messaging is wrong (value prop doesn't land). Above 8% on cold is usually because the cohort is warmer than it looks (alumni network, second-degree connections).

## Backwards math from goal

Pick the goal. Compute backwards through the funnel.

**Goal example: 10 paying customers in 8 weeks (B2B SaaS).**

- 10 paying customers / 4% cold close rate = **250 qualified conversations needed**.
- 250 conversations / 5% reply-and-schedule rate from cold = **5,000 cold outreaches**.
- Alternatively, 250 conversations / 25% rate from warm intros = **1,000 warm intros** (much harder to source than to send).

Realistic mix: 2,500 cold outreaches + 500 warm intros across 8 weeks = ~440/week of focused work. This is full-time founder outreach, not a side activity.

If the math says "10,000 cold emails to hit 10 customers," and the founder has 8 weeks, and they're solo, the goal is wrong or the price is wrong. Either re-price up (fewer customers needed) or expand the timeline.

## Compounding effects of small improvements

Each stage's conversion rate compounds. A founder who improves three stages by 50% each — from 5% reply, 40% schedule, 4% close to 7.5% reply, 60% schedule, 6% close — sees end-to-end conversion go from 0.08% to 0.27%, more than tripling.

Where to focus:

- **Highest leverage: subject line and first sentence.** This is the reply rate. A specific subject ("Saw your team is hiring for X") beats generic ("Quick question") by 3–5x in cold outbound.
- **Next: the offer.** What you're asking for in the email determines schedule rate. "15 minutes to compare notes" beats "would love to connect" — concrete CTAs convert.
- **Last: the qualifying call structure.** Close rate improves with `discovery-coach` PREPARE — knowing what you're testing, knowing the close ask.

## Where founders lie to themselves about funnel health

- **"My open rate is 60%."** Email clients pre-fetch images now, inflating open rates by 20–50%. Trust reply rate, not open rate.
- **"They said they'd consider it."** Not a conversation. Count only scheduled-and-completed calls.
- **"I have 30 'in the pipeline.'"** "In the pipeline" usually means "did not respond yet" or "ghosted." Pipeline is `next concrete step on calendar`, not optimistic ambiguity.
- **"My close rate is high."** Often is, on a tiny denominator. 2 closed of 5 conversations is not a 40% close rate; it's two anecdotes.

## CRM threshold

Below ~50 active prospects, a spreadsheet is correct. Airtable or Google Sheets, with columns: name, role, company, contact, outreach date, response status, next concrete step, conversation notes. Above ~50 active, consider Pipedrive or close.com (see `tool-recommendations.md`). HubSpot CRM is free but does too much for pre-PMF; skip until customer count grows.

## The 5% rule

If after 100 well-targeted, well-written cold outreaches the founder cannot get a single qualified conversation, something fundamental is wrong:

1. The ICP is off.
2. The value prop language is off (not in customer vocabulary).
3. The CTA is too vague.
4. The founder is sending to the wrong contact at the company.

Re-run `market-intel` for the customer vocabulary. Re-check the ICP narrowness. Refine and re-send. If a second batch of 100 still produces nothing, the hypothesis itself is suspect — return to `idea-pressure-test` or `problem-focus`.

## What this is NOT

This reference does NOT cover paid acquisition. `outreach-engine` refuses to recommend paid acquisition pre-PMF (per Gustav Alstromer and Sean Ellis). Founder-led organic outreach is the only motion validated for pre-PMF; ads are for post-PMF scaling and require the `pmf-audit` survey to clear first.

## Where this is used

`outreach-engine` uses this math to set outreach volumes from the founder's stated goal. `pricing-model` cross-references it to validate that the chosen price makes the funnel feasible.
