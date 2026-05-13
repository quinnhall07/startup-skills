# Evidence Weighting Matrix

Every statement, action, or observation from a prospective customer is classified on a 0.0–1.0 scale before it lands in the Evidence Log. **Behavioral signal weighs more than attitudinal signal, always.** This is the operational core of the Aggressive Epistemic Auditor stance: it converts the founder's natural overweighting of polite responses into a math the system can enforce.

Attribution: aligned with Rob Fitzpatrick, *The Mom Test*. Specific weights are this project's calibration of Fitzpatrick's principles. The Dinnr case study (UK food-startup that failed despite attitudinal validation) is the canonical cautionary example.

## The matrix

| Weight | Category | Example statement / observation                                          | Why |
|--------|----------|--------------------------------------------------------------------------|-----|
| 0.0    | Attitudinal weak (politeness)        | "Sounds cool, I'd use it."                                   | Hypothetical + leading. Politeness response. |
| 0.0    | Hypothetical pricing                 | "I'd pay $20/month for that."                                | Pricing without offer is anchor-to-compliance. |
| 0.1    | Feature wishlist                     | "You should add X."                                          | Customer doing your job. Treat X as a clue about deeper pain, not as a roadmap. |
| 0.2    | Generic problem agreement            | "Yeah, that's a problem."                                    | Acknowledgment without specifics. |
| 0.3    | Specific past anecdote (low-cost)    | "I dealt with this once a year ago."                         | Real but low-frequency; not yet acute. |
| 0.4    | Email signup (no payment)            | Submits email on Fake Door landing page.                     | Low-cost behavior. Signal exists but weak. |
| 0.5    | Specific past anecdote (high-frequency) | "I deal with this every week."                            | Real, recurring — worth pursuing further. |
| 0.6    | Time-cost shown                      | "Last week I spent four hours on this in Excel."             | Concrete behavioral cost the customer has paid. |
| 0.6    | Trial signup with usage              | Customer uses a free trial at least twice in two weeks.      | Repeat use is behavior. |
| 0.7    | Internal referral                    | "Let me introduce you to my colleague who handles this."     | Customer spending social capital. Real behavior. |
| 0.8    | Workflow displacement                | "Here, let me show you our internal workflow / spreadsheet." | Customer trusts you with their actual process. |
| 0.8    | Pre-order with refund option         | Customer pays a small deposit (refundable).                  | Money + reversibility; still strong. |
| 0.9    | Letter of intent (B2B)               | LOI signed pre-product, with specific conditions.            | Real commitment; not yet absolute. |
| 1.0    | Cash for service (no product yet)    | "Can I pay you $500 to do this for me manually this week?"   | Behavioral absolute. The customer is buying the value before the product exists. |
| 1.0    | Renewal / repeat purchase            | Customer pays a second time after using the product.         | The strongest signal in the matrix. |

## How to apply

1. **At interview debrief**, classify every distinct statement against the matrix. Multiple weights per conversation is normal — one customer might produce a 0.1 (wishlist), a 0.6 (time-cost), and a 0.0 (compliment) in the same hour.
2. **Compute the mean weight** of evidence in the log when assessing PMF stage in `signal-audit`. Pre-signal cohorts run mean < 0.3. Early signal: 0.3–0.5. Converging: 0.6+.
3. **Count high-weight signals (0.8+)** as the commitment density measure. Below 3 of these from ICP-targeted conversations, scaling/paid acquisition is forbidden.
4. **Never average compliments away.** A 1.0 + a 0.0 is not a 0.5; log both. The matrix is for classifying individual statements, not for collapsing the evidence into a single number prematurely.

## The Dinnr counter-example

Dinnr was a UK food-tech startup that ran extensive customer development. Every interview reported strong interest. The founder shipped, expecting the validated demand to convert. It didn't — almost no one bought. The post-mortem revealed that the founder had collected attitudinal responses ("I'd love a service like that") and treated them as behavioral validation, never extracting commitment in the room. Had the founder applied this matrix, the entire pre-launch evidence log would have been mean weight ~0.1. The founder would have known not to ship.

Read the Dinnr post-mortem in any of the public versions when this lesson feels abstract. It is the most expensive version of believing politeness data.

## Refusing the founder's lobbying

Founders will lobby for higher weights. "But they were so enthusiastic!" Enthusiasm is not a row in the table. If a statement doesn't fit a category, weight it at 0.0 until it does. The matrix is non-negotiable; that's the point.

## Where this is used

- `discovery-coach` DEBRIEF mode classifies every statement against this matrix before writing to the Evidence Log.
- `signal-audit` computes the per-stage thresholds against this matrix.
- `rapid-experiments` (v0.3) uses the matrix to specify the *expected weight* of a designed experiment before it's deployed (a Fake Door produces 0.4 evidence; a Concierge produces 0.8).
- `pmf-audit` (v0.4) supplements this matrix with the Sean Ellis 40% survey for products with active users.
