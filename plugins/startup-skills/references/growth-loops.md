# Growth Loops, Unit Economics, and the Four Fits

The operating reference for the post-PMF transition. PMF means a segment is desperate for the product; it does not mean the business works. This file covers the connective tissue: whether the product fits a channel, whether the channel fits the revenue model, whether the model fits the market, and whether the unit economics survive contact with growth.

Attributions: Brian Balfour (Reforge, *Four Fits*); David Skok (*For Entrepreneurs*); a16z (*16 Startup Metrics*); Bessemer Venture Partners (*Cloud 100 Benchmarks*); First Round Capital (*Levels*). Specific company numbers cited inline.

## Brian Balfour's Four Fits

Source: [Brian Balfour, *Four Fits for $100M+ Growth*](https://brianbalfour.com/essays/product-market-fit-isnt-enough) and [Reforge, *Four Fits in Action*](https://www.reforge.com/blog/four-fits-in-action). When growth stalls despite "good product," misfit is almost always one of the latter three fits — not Market↔Product.

| Fit | Question | Failure mode |
|---|---|---|
| **Market ↔ Product** | Does a meaningful segment feel desperate desire? | Sean Ellis <40%. PMF audit. |
| **Product ↔ Channel** | Products are built for channels; channels don't bend. | Product requires education → cannot grow via viral or SEO. |
| **Channel ↔ Model** | Does the channel's CAC reconcile with the model's ARPU? | High-touch sales with $20 ARPU. PLG with $50k contracts. |
| **Model ↔ Market** | Does this segment prefer to pay this way? | SMB asked for annual prepay. Enterprise asked for usage-based with no commit. |

Each fit changing forces re-evaluation of the others. Move from SMB to enterprise (Market shift) → channel must shift from PLG to sales-led → model must shift from monthly self-serve to annual contracts → product must shift toward admin controls, SSO, audit logs. Founders who change one without the others get stuck.

## Viral coefficient (k)

> **k = (avg invites per user) × (avg % who accept and activate)**

Calculate explicitly from instrumentation, never guess.

| k | Meaning | Examples |
|---|---|---|
| **k > 1** | Exponential. Each user brings >1 new user. | Slack early (2014–2016); Dropbox referral (k ≈ 1.6 at peak per Sean Ellis). |
| **k = 0.4 – 1.0** | Supplemental. Real lift but not the primary engine. | Most B2B SaaS with invite flows. |
| **k < 0.4** | Negligible. Paid acquisition or content must be primary. | Most prosumer tools without network effect. |

k > 1 is rare and time-decays as the obvious adopters exhaust. Slack's viral engine carried them to ~$100M ARR before paid acquisition became material; treating that as the typical case is the mistake.

## NRR (Net Revenue Retention)

> **NRR = (beginning ARR + expansion − churn − contraction) / beginning ARR**

| NRR | Verdict | Source benchmark |
|---|---|---|
| **<90%** | Anti-PMF in B2B regardless of new-logo velocity. | [First Round Levels](https://www.firstround.com/levels) |
| **90–100%** | Losing customers faster than expanding. Re-examine ICP. | Skok |
| **100–110%** | Solid B2B SaaS bottom-up. | Bessemer median |
| **120%+** | Top-quartile B2B. Enterprise PLG targets **130%+**. | Bessemer Cloud 100 |

NRR is the single most predictive number for whether a B2B company compounds. Snowflake and Datadog routinely report 150%+; that is the math behind their valuations, not new-logo growth.

## CAC payback period

> **Payback = (CAC / Monthly Gross Profit per customer) × 12**

Use gross profit, not revenue. Cloud cost and support are real.

| Payback | Verdict |
|---|---|
| **<12 months** | Sustainable. SMB SaaS target (Skok). |
| **12–18 months** | Mid-market acceptable if NRR >110%. |
| **18–24 months** | Enterprise acceptable if NRR >120% and contracts are multi-year. |
| **>24 months** | Money pit. Check the assumptions; you are probably under-counting CAC or over-counting LTV. |

## Growth vs. efficiency — what to actually measure

| Class | Metrics | Stage |
|---|---|---|
| **Growth (often vanity early)** | New users, MAU, raw $ ARR added, signup volume. | Useful only paired with efficiency. |
| **Efficiency (tells you if it's a business)** | LTV:CAC, CAC payback, Magic Number, Rule of 40, gross margin, contribution margin. | Required from Series A onward. |

A startup growing 300% YoY at 0.3 Magic Number is burning to manufacture a growth chart, not building a business. The 2021 cohort that died in 2023 was almost universally this profile.

## David Skok's unit economics floors

Source: [David Skok, *For Entrepreneurs*](https://www.forentrepreneurs.com/).

- **LTV : CAC ≥ 3** — minimum sustainable ratio. Below 3, sales spend destroys value.
- **CAC payback < 12 months SMB / <18 mid-market / <24 enterprise.**
- **Magic Number > 0.75** — (Net new ARR this quarter × 4) ÷ S&M spend last quarter. **<0.5 = stop adding sales reps.** Between 0.5 and 0.75 = current reps are okay, do not scale headcount. >1.0 = aggressively hire.

## Bessemer benchmarks 2024–2025

Source: [Bessemer, *Cloud 100 Benchmarks Report*](https://www.bvp.com/atlas/the-cloud-100-benchmarks-report).

- **Rule of X = Growth Rate × NRR.** A more honest reframe of Rule of 40 for high-growth SaaS; rewards retention-driven compounding.
- **Efficiency Score = Net New ARR / Net Burn.** Above 1.0 means the company generates more new ARR than cash burned. Top-quartile Cloud 100 cohort runs ≥1.5.
- **NRR bands by tier:** baseline 100% / good 110% / great 120%+ / elite (enterprise PLG, infra) 130%+.

## a16z's 16 metrics — what founders misreport

Source: [a16z, *16 Startup Metrics*](https://a16z.com/16-startup-metrics/). Bookmark the full list; two are routinely mis-stated:

- **Report gross profit, not revenue.** A $10M revenue company at 20% gross margin is a $2M gross profit company.
- **Report contribution margin per customer.** Revenue per customer minus variable cost to serve that customer. This is the number that scales.

## AI-era unit economics traps

The 2010s SaaS playbook assumed <10% COGS. AI-native products break that assumption.

- **Token COGS run 30–60% of revenue.** Gross margins of 40–70%, not 80–90%. Public examples in 2024–2025 filings.
- **Flat SaaS pricing while costs scale per-token = silent margin destruction.** Heavy users on flat plans destroy contribution margin; the top 5% of users can be unprofitable in isolation.
- **Power-law usage means the median user subsidizes nothing.** Pricing must reflect usage or cap it.

## Anchor cases

| Company | What worked / failed | Lesson |
|---|---|---|
| **DoorDash** | Day-1 CAC >$5/customer, brutal by 2014 standards. But food orders repeat weekly → LTV >> CAC. Survived and IPO'd. | High CAC is fine if repurchase frequency is high. |
| **Magic (SMS concierge, 2015)** | CAC was sustainable; LTV ≈ $0 because the product was a one-time novelty. | Low CAC with no repeat behavior is still a dead business. |
| **Slack** | k > 1 in first ~2 years; viral team-invite loop carried growth to ~$100M ARR before paid scaled. | Viral can be primary, but only when the product's core action requires inviting others. |
| **Cursor** | Usage-based pricing aligned to value from day 1; margins survive contact with heavy-user power law. | AI-native products that price per-token-of-value avoid the flat-SaaS margin trap. |

## Where this is used

`outreach-engine` reads payback period and Magic Number to gate paid acquisition recommendations. `pmf-audit` references NRR as a post-PMF confirmation signal. `pricing-model` uses CAC payback, LTV:CAC, and AI-era COGS traps to validate pricing proposals. `pivot-decision` checks Four Fits misalignment when growth stalls despite a passing PMF score. `continuous-discovery` uses Model↔Market fit to interpret pricing objections from interviews.
