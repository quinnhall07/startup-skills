# Sales Funnel Math

Math the founder must do before any outreach batch. Without it, the outreach volume estimates are fantasies. Source: Gustav Alstromer's *How to Get Your First Customers*, Lenny Rachitsky's first-customer benchmark posts, sales literature on cold-outbound conversion.

## Realistic conversion rates by archetype (2025-2026)

For founder-led early-stage outreach (NOT a sales team, NOT post-PMF):

### B2B SMB SaaS / mid-market

| Stage | Cold | Warm intro | Inbound |
|---|---|---|---|
| Email reply rate | 3-5% (avg), 5-10% (good), 10-15% (elite) | 30-60% | 20-40% |
| Reply → scheduled call | 30-50% | 60-80% | 50-70% |
| Show up to call | 70-80% | 90% | 80% |
| Becomes paying customer | 3-5% of pipeline | 15-25% | 10-20% |
| **Cold → paying** | **~1% of total sends** | — | — |

### B2B enterprise

| Stage | Cold | Warm intro |
|---|---|---|
| Email reply rate | 1-3% (broad) | 30-50% (warm referral) |
| Reply → scheduled call | 20-40% | 50-70% |
| Becomes paying customer | <1% of cold; 10-20% of warm intros | Same |
| **Note**: enterprise sales cycles are 6-12 months. Cold-to-close in <6 months = anomaly. |

### B2C consumer

| Stage | Cold | Inbound |
|---|---|---|
| Generally NOT cold-outreach. | — | — |
| Landing page conversion (Fake Door) | — | 1-5% generic, 10-15% targeted, 20%+ niche-community |
| Free signup → paying | — | 0.5-2% (consumer); 2-5% (consumer with strong activation) |

### Marketplace

- **Liquidity > funnel math.** Solve one side first, then the other.
- DoorDash example: restaurants signed via founder personal calls. Customer-side ads at 5-15% CTR + 10-20% signup conversion.

### AI products (2025-2026 churn-aware)

- Trial signup → paying: 8-15% common (lower than traditional SaaS due to model-market-fit churn).
- D28 retention <30% = model-market-fit, not PMF. Adjust funnel math to filter out novelty signups.

These are reality, not the optimistic numbers founders hope for. The 3–5% cold-to-paid rate is *typical for a founder doing the work themselves with good targeting*. Below 2% means either the targeting is wrong (ICP mismatch) or the messaging is wrong (value prop doesn't land). Above 8% on cold is usually because the cohort is warmer than it looks (alumni network, second-degree connections).

## Deliverability collapse — 2025-2026 baseline

**Feb 2024 Gmail/Yahoo bulk sender rules + Nov 2025 enforcement** materially changed cold email reply rates. Authenticated senders see **2.7× more inbox placement** and **15-20% higher reply rates** than unauthenticated ones.

**Reply-rate benchmarks by sender setup:**
- Custom domain + Outlook: 5.9% (strong baseline).
- Custom domain + Gmail: 3.5% (strong baseline).
- Webmail (`@gmail.com` direct): 1.2-2.1% — borderline failure.

**Tracking pixels correlate with -10 to -15% reply rate** — turn them off.

**Bottom line**: if you're not authenticated (SPF + DKIM + DMARC) and warming up secondary domains, your math is broken before you write the first email.

For deliverability infrastructure, load `${CLAUDE_PLUGIN_ROOT}/references/tool-recommendations.md` cold email section.

## LinkedIn comment-first math (2025-2026)

LinkedIn algorithm changes (late 2025) shifted from Relationship Graph to Interest Graph. Cold-DM tolerance crashed; comment-first now compounds.

| Action | Reply / engagement rate |
|---|---|
| Personalized connection request (with message) | 9.36% reply / 29-45% acceptance |
| Personalized InMail | 18-25% (elite tier 30-40%) |
| Templated mass DM/InMail | <1% |
| **Inbound-Led Outbound**: 50 thoughtful 30-80 word comments on ICP posts per week | ~300% lift in inbound connection requests vs. cold DM blast |

**Channel hierarchy**: connection-request-with-note primary; InMail reserved for high-priority follow-ups when request declined.

## Backwards math from goal

Pick the goal. Compute backwards through the funnel.

**Goal example: 10 paying customers in 8 weeks (B2B SaaS).**

- 10 paying customers / 4% cold close rate = **250 qualified conversations needed**.
- 250 conversations / 5% reply-and-schedule rate from cold = **5,000 cold outreaches**.
- Alternatively, 250 conversations / 25% rate from warm intros = **1,000 warm intros** (much harder to source than to send).

Realistic mix: 2,500 cold outreaches + 500 warm intros across 8 weeks = ~440/week of focused work. This is full-time founder outreach, not a side activity.

If the math says "10,000 cold emails to hit 10 customers," and the founder has 8 weeks, and they're solo, the goal is wrong or the price is wrong. Either re-price up (fewer customers needed) or expand the timeline.

## Updated backwards math example (post-2024 reality)

**Goal: 10 paying customers in 8 weeks (B2B SaaS).**

- 10 paying / 3% cold-to-paid rate (avg founder-led) = **333 qualified conversations needed**.
- 333 conversations / 5% reply-and-schedule from cold = **6,660 cold outreaches**.
- Realistic mix: 4,000 cold (across multiple secondary domains, warmed up) + 500 warm intros + LinkedIn comment-first inbound.
- Across 8 weeks = ~580/week of focused work. **Full-time founder outreach, not side activity.**

If math says "10,000 cold emails in 8 weeks solo" — either re-price up (fewer customers needed) OR narrow ICP further (higher response rate) OR expand timeline.

## Compounding effects of small improvements

Each stage's conversion rate compounds. A founder who improves three stages by 50% each — from 5% reply, 40% schedule, 4% close to 7.5% reply, 60% schedule, 6% close — sees end-to-end conversion go from 0.08% to 0.27%, more than tripling.

Where to focus:

- **Highest leverage: subject line and first sentence.** This is the reply rate. A specific subject ("Saw your team is hiring for X") beats generic ("Quick question") by 3–5x in cold outbound.
- **Next: the offer.** What you're asking for in the email determines schedule rate. "15 minutes to compare notes" beats "would love to connect" — concrete CTAs convert.
- **Last: the qualifying call structure.** Close rate improves with `discovery-coach` PREPARE — knowing what you're testing, knowing the close ask.

## Where founders lie to themselves about funnel health

- **"My open rate is 60%."** Apple Mail Privacy + Google image pre-fetch inflate open rates by 20-50%. Trust reply rate, not open rate.
- **"My LinkedIn DMs are working — I get lots of replies."** Check if those replies are from ICP or from other founders / sales people pitching back. Filter for ICP-only replies.
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
