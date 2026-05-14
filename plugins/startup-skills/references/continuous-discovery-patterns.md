# Continuous Discovery Patterns

Attribution: Teresa Torres, *Continuous Discovery Habits* (2021). The connective tissue between the Mom Test (interview technique) and ongoing post-PMF customer cadence. Discovery is not a sprint that ends at validation — it is a weekly habit that runs for the life of the product. This reference distills the operating patterns; it is not a substitute for the book.

## The definition

Torres, verbatim: *"At a minimum, weekly touchpoints with customers by the team that's building the product, where they conduct small research activities in pursuit of a desired product outcome."*

Four load-bearing words: **weekly**, **by the team**, **small**, **outcome**. Remove any one and the practice collapses into something else — quarterly research, delegated research, big-bang research, or feature-factory research.

## Why this matters

Discovery is not a one-time validation sprint. After PMF, the cohort changes, expectations rise, competitors ship adjacent solutions, and the original problem mutates. Founders who stop interviewing after validation drift out of PMF in 6–18 months — the "PMF Treadmill" pattern documented by Reforge. Cadence beats intensity. One conversation per week for 52 weeks produces more compounding insight than five conversations crammed into one week per quarter.

## The Product Trio

Torres's organizing unit: **PM + designer + engineer interview together.** Not delegated to a researcher. Not summarized in a Notion doc. The three roles sit in on the same call so the team building the product hears the customer in their own voice.

- Engineers who attend interviews make better implementation calls without specs — they have absorbed the customer's mental model directly.
- Designers who attend interviews stop designing for the wrong workflow.
- PMs who attend interviews stop relying on the salesperson's narration.

For pre-PMF startups the trio is **founder + cofounder + first-engineer-hire**. If your team is two people, both attend. If you are solo, *you* attend every interview yourself — never delegate to a contractor.

## Opportunity Solution Tree (OST)

Four-tier visual artifact, maintained continuously, updated after every interview:

- **Outcome** (top, single, measurable). E.g., "increase weekly active retention by 10 points by Q3." One outcome per tree. Not "delight customers" — a number with a deadline.
- **Opportunities** (children). Customer needs, pains, desires, expressed in *customer language*. NEVER solutions. "I can't tell which alerts are real" is an opportunity; "add severity filtering" is not.
- **Solutions** (grandchildren). Multiple per opportunity — the discipline is to generate 3+ solutions per opportunity before committing to any one. Treats solutions as cheap and disposable.
- **Assumption tests** (leaves). Small experiments under each candidate solution.

The hard rule: **opportunities must be discovered, never invented.** They come *only* from interview stories. If you cannot point at an interview snapshot for a given opportunity, it does not belong on the tree.

## Story-based interviewing (Torres)

The opening prompt: **"Tell me about the last time you [did the behavior]."** This is the structural sibling of Fitzpatrick's past-behavior rule, but with a sharper instruction: anchor on a specific story, not a general pattern.

- **Narrow story.** "Tell me about the last time you watched Netflix on the go."
- **Market-scoped story.** "Tell me about the last time you did something fun." (For early exploration when the use case isn't pinned.)
- **Opportunity-scoped story.** "Tell me about the last time you had to choose a new show." (For drilling into a known opportunity.)
- **Redirect on generics.** If the customer says "I usually like…" or "Normally I…" — redirect: *"That specific time — what happened?"* Customers default to summary; specificity is where the data lives.
- **Talk budget.** Interviewer talks <20% of the call. If you find yourself explaining, stop. If you find yourself agreeing, stop. The customer's silence is their thinking.

## Interview snapshots

A Torres artifact — one page per interview — produced within 24 hours of the conversation while it's fresh:

- **Participant info.** Role, industry, demographics, ICP fit score.
- **Key quote.** The strongest verbatim line from the call. One sentence. Customer's words, not yours.
- **Story timeline.** What happened, in order. Not the customer's summary — the actual sequence of events from the story they told.
- **Surfaced opportunities.** Each pain/need extracted, mapped onto a node of the OST.
- **Surprises.** What contradicted your expectations going in. This field is the most valuable and most often skipped.

Stored in a binder (physical or Figma board) so the trio can flip through and pattern-match recurring themes across interviews. The snapshot is the unit of memory; the OST is the unit of structure.

## Five assumption categories (Torres)

Before building any solution, classify the assumptions underneath it:

- **Desirability.** Do customers actually want this? (Mom Test territory.)
- **Viability.** Can we build this sustainably as a business? Unit economics, GTM cost, retention.
- **Feasibility.** Can we build this technically, in our context, on our stack, in our timeframe?
- **Usability.** Can users figure out how to use it without a tutorial?
- **Ethical.** *Should* we build it? Externalities, dark-pattern risk, vulnerable-user risk.

Map the proposed solution onto each. Identify the riskiest assumption. Run the smallest possible test against that one. Do not test all five at once; do not skip ethical because it's uncomfortable.

## Assumption mapping via story-mapping

Imagine the solution exists in production. Walk a customer through the steps required to extract value from it — from discovering it through to repeat use. At each step, ask: *"What needs to be true for this step to happen?"* Each answer is an assumption.

Most assumptions live in the steps the team takes for granted. ("They'll know to click the button." "They'll trust us with their data." "Their manager will approve the spend.") These are the failure points that kill features the team thought were obvious wins.

## The independence check

Feedback triage rule for inbound feature requests: when a customer requests a feature, ask — have you heard this request from **20+ ICP-targeted users independently**, or just from this one person? If just this person, the request is a clue about *their specific use case*, not a product mandate. Drill into the underlying job (Fitzpatrick / Christensen JTBD); do not add the feature to the roadmap.

The single loud customer is the most expensive false signal in post-PMF roadmapping.

## Build-measure-learn velocity

Ries's loop (*The Lean Startup*, 2011), applied at Torres cadence. Pre-PMF, the team should be shipping **2–3 real experiments per week**. If it takes a week to ship one experiment, you are moving too slowly — the cycle time, not the experiment quality, is the bottleneck. Post-PMF the velocity slows (experiments get larger and more carefully instrumented) but discovery cadence continues unchanged.

## AARRR / Pirate Metrics

Dave McClure's funnel: Acquisition → Activation → Revenue → Retention → Referral.

- **Pre-PMF.** Focus on Acquisition + Activation + WTP (willingness to pay). Retention and referral data are too sparse to be load-bearing yet.
- **Post-PMF.** Retention and referral become the load-bearing metrics. If retention is flat, you have a discovery problem, not a marketing problem.

## I-Corps 100-interview standard

The rigorous threshold for deep technical/scientific founders. Steve Blank's NSF I-Corps program: **100 customer interviews, 7–10 weeks, update the Business Model Canvas weekly.** ~9,330 scientists trained, ~1,400 teams launched as of public reporting. The 100-interview number is non-arbitrary — it is the empirically observed threshold at which technical founders' priors actually update.

## Sources

- Torres, *Opportunity Solution Trees*: https://www.producttalk.org/opportunity-solution-trees/
- Torres, *Best Customer Interview Questions*: https://www.producttalk.org/best-customer-interview-questions/
- Torres, *Story-Based Customer Interviews*: https://www.producttalk.org/2024/04/story-based-customer-interviews/
- Blank, *Lean LaunchPad*: https://leanlaunchpad.stanford.edu/people/steve-blank
- Interaction Design Foundation, *Continuous Discovery*: https://ixdf.org/literature/topics/continuous-discovery

## Where this is used

Loaded by `continuous-discovery` (new skill establishing the weekly cadence and OST), `discovery-coach` (PREPARE mode for story-based scripts, DEBRIEF mode for snapshot extraction), `rapid-experiments` (assumption mapping and the 2–3-per-week velocity target), and `pmf-audit` (independence check and post-PMF retention/referral framing).
