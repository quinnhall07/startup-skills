# Validation Techniques

A menu of validation methods, with the archetype guidance that determines which fits. The wrong technique for an archetype destroys signal — Fake Door tests damage enterprise trust; Concierge MVPs at consumer-mobile-app scale are impossible. Source: Steve Blank (Customer Development), Eric Ries (Lean Startup), Paul Graham (*Do Things That Don't Scale*), Dropbox / DoorDash / Airbnb early-stage histories.

## The matrix — by archetype

| Archetype | Recommended | Avoid | Why |
|---|---|---|---|
| **B2B enterprise** (Fortune 500, regulated industries) | Concierge MVP framed as "high-touch pilot" or "white-glove onboarding"; Letter of Intent process | Fake Door, anonymous landing pages | Enterprise buyers cannot afford to discover the product doesn't exist after they've committed budget. Trust destroyed once stays destroyed. |
| **B2B SMB / devtools** | Either Fake Door or Concierge. Cold outreach batches with strong CTAs. | Mass Fake Door without follow-up plan | SMB and developer buyers tolerate roughness; honest "early access" framing works. |
| **Consumer SaaS / mobile** | Aggressive Fake Door, Wizard of Oz, video MVPs | Concierge as primary (can't scale to needed sample size) | Users are forgiving; novelty signal needs volume not depth. |
| **Hardware** | Pre-orders on Kickstarter or landing page with refundable deposit | Pure Fake Door (no payment) | Hardware needs financial signal; the cost of being wrong is too high to validate on signups. |
| **Marketplace** | Solve one side at a time, manually. Be the other side yourself. | Building both sides simultaneously | Liquidity is the only marketplace metric. Concentrate supply or demand first; the other side follows. |

## Technique details

### Fake Door

A landing page that describes the product as if it exists, with a single CTA — "Get Access," "Notify Me," "Reserve Spot." Captures email + intent data when the user clicks. The user discovers the product is in early access only after submitting.

- **What it tests:** willingness to opt into solving the problem.
- **Signal weight:** ~0.4 per email (per `evidence-weighting-matrix.md`). Higher (0.6+) if combined with a follow-up payment ask within 48 hours.
- **Time to deploy:** 1–3 days for a single page (Webflow, Carrd, Framer, or hand-coded HTML).
- **When NOT to use:** B2B enterprise (trust damage); regulated industries; any product where the user's discovery that it's not real costs them measurably.

### Wizard of Oz

A real-looking product UI where the founder (or team) manually performs every backend operation. Users believe they're using software; in reality, you're processing each request by hand.

- **What it tests:** whether real users complete the value-receiving action when the UX is good enough.
- **Signal weight:** 0.6–0.8 (behavioral, with actual workflow). Pre-payment WoZ is 0.6; payment + WoZ is 0.8.
- **Time to deploy:** 1–2 weeks for the frontend; the "backend" is your team.
- **When NOT to use:** at any scale where manual processing becomes unsustainable. Calibrate the cap: 5–50 users for a complex workflow; 100–500 for simple.

### Concierge MVP

You explicitly tell the customer that delivery is manual, and you do the work yourself. No technology illusion. The customer experiences the value; you experience the workflow.

- **What it tests:** whether the customer values the outcome enough to pay despite the obvious labor cost.
- **Signal weight:** 0.8–1.0 with payment. The highest-quality signal short of repeat purchase.
- **Time to deploy:** hours. DoorDash's first version was "we'll drive the food to you ourselves" — a phone number and a static webpage.
- **When NOT to use:** when the goal is to test a UX hypothesis (Concierge can't test UX; it bypasses it).

### Pre-order with refundable deposit

A landing page with payment intent capture — a $1, $50, or $500 deposit that's refunded if the product doesn't ship by date X.

- **What it tests:** financial commitment to the problem.
- **Signal weight:** 0.8 (refundable) to 1.0 (non-refundable).
- **Time to deploy:** 1–2 weeks (Stripe + landing page + clear terms).
- **When NOT to use:** consumer products under $10 — the payment friction overwhelms the signal.

### Cold outreach batch

A 50–200 person outreach campaign with a specific, behavioral CTA — pay for a pilot, join a paid waitlist, commit to using the product on a specific date.

- **What it tests:** whether ICP-targeted prospects respond to the value prop in their language.
- **Signal weight:** depends on the CTA. Email open = 0.1. Reply = 0.3. Scheduled call = 0.4. Paid commitment = 1.0.
- **Time to deploy:** 1 week (list + drafts + send).
- **When NOT to use:** broad spray-and-pray; this only works targeted.

### Problem validation post

A post in a relevant community (subreddit, Indie Hackers, LinkedIn group) describing the problem and asking who else has it.

- **What it tests:** whether the problem resonates in the language of the community.
- **Signal weight:** 0.2–0.4. Public comments are mostly attitudinal; DMs and offered intros are signal.
- **Time to deploy:** 1 hour.
- **When NOT to use:** as a substitute for outreach. The community already self-selects for the kind of person who comments.

### Survey

Structured questionnaire to N respondents, typically via Typeform, Tally, or Google Forms.

- **What it tests:** breadth (with thin signal depth).
- **Signal weight:** 0.0–0.2 for "would you" questions; 0.4+ for "have you (in the past)" questions.
- **Time to deploy:** 1–3 days plus distribution time.
- **When NOT to use:** as the primary validation tool. Surveys are weak — they sit between interviews (deep but few) and behavioral tests (objective). They confirm patterns, they don't establish them.
- **Exception:** Sean Ellis 40% Rule survey for post-launch products (see `pmf-audit` in v0.4, forward-references `pmf-scoring.md`).

## Falsification pre-commitments — non-negotiable

Every experiment commits IN WRITING, BEFORE LAUNCH:
- **Success criterion.** "We will continue if X people do Y by date Z." Specific, numerical, time-bound.
- **Kill criterion.** "We will pivot or stop if X people do not do Y by date Z." Also specific.

No moving goalposts. HARKing (Hypothesizing After Results are Known) is forbidden. The criteria go into `STARTUP-STATE.md` under MVP / Experiment Plan before the experiment deploys.

## Where this is used

`rapid-experiments` consults this table to propose 2–3 options for the founder's archetype. `mvp-architect` checks whether `rapid-experiments` has produced behavioral signal before approving a build phase.
