# Startup Assistant Skill Blueprint
## Research Notes, Pattern Analysis & Full Skill System Design

---

## PART 1: RESEARCH NOTES

### What the YC Materials Actually Teach (And What Most People Miss)

Reading all thirteen documents together reveals a tight, internally consistent philosophy that most people absorb piecemeal and therefore misapply. The core thesis, stated plainly: **startups do not take off by themselves. Founders make them take off, manually, through direct human effort that cannot be automated or delegated at the early stage.** Everything else flows from this.

---

### PATTERN 1: The Organic Idea vs. The Manufactured Idea

The single most consistent signal across Paul Graham's essays, Jared's talk, Michael Seibel, and Dalton is that **ideas that are consciously manufactured ("what startup idea should I work on?") are categorically worse than ideas that arise organically from living close to a real problem.**

The mechanism is subtle: when you sit down and try to think of a startup idea, your brain produces *plausible-sounding* bad ideas — things that sound like startups (social network for pet owners, app to coordinate plans with friends) but have structural reasons they can't work. Organic ideas arise when a founder is living at the frontier of a domain, encounters a gap, and builds something to fill it. Apple, Yahoo, Google, Facebook, Airbnb, Stripe — none were meant to be companies at first.

**Quirk:** Most people hear "don't look for ideas" and interpret it as license to wait forever. The actual prescription is to *live in the future of some domain*, stay close to problems, work on interesting things, and let ideas surface. Active positioning, passive noticing.

**Anti-pattern:** "AI is cool, what could I apply AI to?" — This is the canonical solution-in-search-of-a-problem. You'll find a problem, but it'll be superficially plausible rather than real.

---

### PATTERN 2: Founder-Market Fit Is More Important Than the Idea Itself

Repeatedly across sources: the team matters more than the initial idea (YC admits people with no idea), but within that, **founder-market fit** — whether this team is unusually well-positioned to work on this specific problem — is the strongest predictor of success.

PlanGrid: Tracy had worked in construction. The resi founders were real estate + fintech experts. The A-to-B founders drove to truck stops and talked to truckers for months. Brex founders had already built a fintech company in Brazil and had the existing relationships.

**Quirk:** Founder-market fit is not "I'm passionate about this." Passion can be manufactured. FMF is about whether you have asymmetric knowledge, access, or experience that makes you specifically dangerous in this domain. Someone who's never worked in healthcare does not have FMF for a healthcare startup, no matter how excited they are.

**Anti-pattern:** Founders who are "interested in" a space but have no unfair advantage in it. This is where most generic "I want to solve X big problem" ideas come from.

---

### PATTERN 3: The Tar Pit Problem

Dalton's framing is the clearest description of a failure mode that ruins enormous amounts of founder time. Tar pit ideas are ideas that:
- Are superficially plausible
- Solve a widespread, relatable problem
- Have a structural reason they're nearly impossible to solve
- Have attracted many founders before you, none of whom succeeded

The "meet up with friends efficiently" app is the canonical example. It's been submitted to YC for 20 years. Nobody has made it work.

**Why tar pits are dangerous:** The ideas feel like insights ("I can't believe nobody has solved this!") because the problem is real and relatable. But the reason nobody has solved it is that the solution space is actually very constrained (the people who need it most don't cluster anywhere you can reach them; the frequency of use is too low to build a habit; there's no monetization path; etc.).

**Quirk:** Tar pit ideas are not necessarily impossible. They're *much harder than they look*, and the founders who get stuck in them often don't know why they're stuck. The right response when encountering a tar pit candidate is to Google it, find the people who tried before, and talk to them about where they hit walls.

---

### PATTERN 4: The Narrow Well vs. The Broad Puddle

Paul Graham's well metaphor is one of the sharpest conceptual tools in the canon. **You want a small number of people who desperately need what you're making, not a large number who are mildly interested.** A broad puddle evaporates. A deep well sustains.

The implication that most founders miss: **the narrowness is a feature, not a bug.** Facebook was only for Harvard students. Stripe was only for YC startups. Airbnb was only for conference attendees sleeping on air mattresses. Starting narrow isn't failure to think big — it's the correct early strategy because narrow markets give you signal, let you iterate fast, and create the possibility of actually delighting a small group before expanding.

**Anti-pattern:** "Our product is for everyone" — this is almost always a sign that the problem hasn't been sufficiently specified. If everyone could use it, no one desperately needs it.

**Quirk:** Founders consistently underestimate how narrow their initial market should be. When someone says "we're targeting small businesses," that's still 30 million companies in the US. Narrow means 50 specific people in a Slack community.

---

### PATTERN 5: Do Things That Don't Scale — This Is Not a Hack, It's the Method

PG's essay is misread as "it's okay to do unscalable things." The actual point is stronger: **unscalable, manual, human-intensive effort is not a necessary evil of early-stage startups — it is the primary mechanism by which they discover product-market fit and build their initial user base.**

The Stripe "Collison installation" (don't ask if they want to try it, just set it up on their laptop), Airbnb's door-to-door recruiting in NYC, Wufoo's handwritten thank-you notes, Brian Chesky living in 50 Airbnbs — these aren't quaint stories. They're the central mechanism.

**Why this matters for the skill system:** When a user asks Claude "how do I get my first users?" the correct answer is not "run ads" or "post on Product Hunt." It's "manually recruit them one at a time and make each of them insanely happy." This answer sounds wrong and small, but it's right.

**Anti-pattern:** Founders who jump directly to scalable growth channels (SEO, paid ads, referral programs) before they have 10 users who love them. These channels require product-market fit to work — you're optimizing a signal that doesn't exist yet.

---

### PATTERN 6: Sales Is Customer Research Is Product Development

The Gustav talks reveal something important: talking to users, doing sales, and doing product research are not three different activities. **They are the same activity viewed from different angles.** The reason founders should do sales themselves is not just tactical — it's because the information you get from trying to sell something is the most valuable product feedback you can get.

If you can't sell it, you don't understand why people would want it. If you don't understand why people would want it, you can't build it well. Sales and product are inseparable at the early stage.

**Quirk:** Founders who build great products but can't sell them often discover their product isn't actually great — it just solves a problem they understand but their customers don't have.

**Anti-pattern:** "We'll hire a salesperson once the product is ready." This is backwards. You need to sell first to know what to build.

---

### PATTERN 7: The Politeness Problem

Dalton names this explicitly and it's reinforced in Rob Fitzpatrick's Mom Test. **People will almost never tell you your idea is bad.** They will say "interesting," "cool," "I'd maybe use that," "sounds promising." These responses feel like validation but are zero-signal.

The only signals that count are:
- They pay money
- They use it repeatedly without being prompted
- They refer others without being asked
- They express genuine pain when asked about the current situation
- They change their actual behavior because of your product

**Quirk:** The most dangerous validation is from smart, well-connected people who say kind things. Founders routinely mistake "impressive people were nice to me about this" for "this idea is good."

**Anti-pattern:** Building based on user interviews where you asked "would you use this?" — The answer is always yes. The real question is "what would stop you from paying for this today?"

---

### PATTERN 8: The Pivot Timing Problem

Dalton's observation: most founders pivot *too late*, not too early. Loss aversion, sunk cost fallacy, and the seductive nature of "a little bit of traction" all conspire to keep founders working on something that isn't working.

**The uncanny valley of PMF:** A company with zero traction can pivot cleanly because there's nothing to defend. A company with explosive growth clearly shouldn't pivot. The dangerous zone is a company with *some* traction — a few users, one paying customer, 200 signups — because it's just enough to justify staying. This is where most startups die.

**Quirk from cognitive bias research:** Confirmation bias + sunk cost fallacy are particularly lethal in combination. You've invested months into an idea, you're getting some polite interest, you selectively interpret every positive signal as evidence it's working. This is unconscious and systematic. The antidote is predetermined success metrics set *before* you start, not after.

---

### PATTERN 9: The MVP Is Not a Product, It's a Question

The single most misunderstood concept in startup discourse. Michael Seibel makes the key point: **the MVP is not about making a minimal product. It's about running a specific experiment as fast as possible to get a specific answer.**

The question the MVP asks is: "Does this problem exist, and will these people actually change their behavior to solve it?"

Airbnb's first version couldn't handle payments, had no maps, only worked for conferences, and required sleeping on air mattresses. It still answered the question: "Will strangers pay to stay in other strangers' homes?" Yes. Build from there.

**Quirk:** "Minimum" is wildly misapplied. Founders routinely spend 6 months building "MVPs" because they're building a product rather than running an experiment. A real MVP takes 2-6 weeks and tests one hypothesis.

**Anti-pattern:** The "fake Steve Jobs" founder who knows exactly what the perfect product looks like and needs 18 months to build it. Even Steve Jobs needed the iPhone 3 before the iPhone was actually good.

---

### PATTERN 10: The Sales Funnel Is a Numbers Game, Not a Quality Game

Gustav's data: to get 2 paying customers, you may need 500 outreach emails, 20 responses, 10 demos. Most founders send 100 emails, get 0 customers, conclude "sales doesn't work for us." They don't have enough data to reach that conclusion.

**The math failure:** Founders consistently underestimate how many people they need to contact to get a signal. The correct mental model is not "reach the right people" but "cast a wide net to find the right people, because you can't identify them in advance."

**Quirk:** Early adopters don't self-identify. You can't filter for them before you reach out. You have to reach out broadly and let them self-select.

---

### PATTERN 11: Product-Market Fit Is Behavioral, Not Attitudinal

Synthesizing across YC materials and external research: PMF is not measured by what people say about your product. It's measured by what they do.

**Behavioral signals of PMF:**
- Users return without prompting
- Word-of-mouth referrals happen organically
- Revenue grows without proportional increases in sales effort
- You struggle to keep up with demand
- Users complain loudly when you're down (Sean Ellis: 40%+ say "very disappointed" if product disappeared)

**Anti-signals frequently mistaken for PMF:**
- Press coverage and signups
- "Everyone I've shown this to loves it"
- Early sales to friends/network
- First paying customer who needed custom persuasion
- High engagement in first two weeks (novelty effect)

---

### PATTERN 12: The Launch Is Continuous, Not An Event

The head of YC Outreach makes a point that contradicts most startup mythology: **there is no "the launch." Launching is something you do repeatedly.** Airbnb launched three times before it got traction. Robinhood was launched on HN accidentally before they were ready. 

The obsession with a perfect launch is a form of procrastination dressed up as strategy. The real work is iterating quickly after each launch, not perfecting the first one.

---

### COGNITIVE BIAS INVENTORY (From External Research)

These are the specific psychological failure modes that derail early-stage founders:

1. **Confirmation bias** — Seeking evidence that confirms the idea, filtering out disconfirming evidence. *Antidote: Pre-commit to specific falsifiable criteria before testing.*
2. **Sunk cost fallacy** — Continuing bad ideas because of prior investment. *Antidote: Evaluate ideas based on future expected value, not past cost.*
3. **Optimism bias** — Overestimating likelihood of success, underestimating time/cost. *Antidote: Reference class forecasting; ask "what happened to other companies in this situation?"*
4. **Overconfidence** — Believing you understand users better than you do. *Antidote: Make specific predictions, test them, track accuracy.*
5. **False consensus effect** — Assuming your own needs/preferences are widely shared. *Antidote: Talk to at least 10 people who aren't you or your friends before building anything.*
6. **Planning fallacy** — Underestimating how long things take. *Antidote: Add 3x to any timeline estimate.*
7. **Small sample fallacy** — Drawing strong conclusions from 2-3 positive interviews. *Antidote: Talk to 20+ people before concluding anything.*
8. **Anchoring** — Locking into an initial idea and only considering small variants. *Antidote: Explicitly generate 10 alternative solutions before settling on one.*
9. **Loss aversion in pivoting** — Refusing to pivot because it feels like giving up. *Antidote: Reframe: pivoting is gaining another shot on goal, not losing progress.*

---

### KEY FRAMEWORKS FROM EXTERNAL RESEARCH

**The Mom Test (Fitzpatrick):**
- Ask about their life, not your idea
- Ask about the past, not hypothetical futures
- Never present your idea until you've understood their problem
- Three bad data types to avoid: compliments, hypothetical fluff, wishlists
- True validation = money, behavior change, or referrals

**Build-Measure-Learn (Ries):**
- Start with a hypothesis, not a product
- MVP = fastest way to test the hypothesis
- Measure behavior, not opinions
- Learn whether to pivot or persevere based on data
- Speed of iteration is the competitive advantage

**Steve Blank's Customer Development:**
- Customer Discovery → Customer Validation → Customer Creation → Company Building
- "No business plan survives first contact with customers"
- Startups are not small companies; they search for a business model, not execute one

**Sean Ellis PMF Test:**
- Survey users: "How would you feel if you could no longer use this product?"
- 40%+ answering "very disappointed" = approaching PMF
- Below 40% = not there yet, iterate

---

## PART 2: ANTI-PATTERNS MASTER LIST

1. Building before validating (the classic)
2. Validating with opinions instead of behavior
3. Targeting "everyone" as the customer
4. Skipping founder-market fit (excited about a space ≠ prepared for a space)
5. Waiting for the perfect product before first customer
6. Mistaking politeness for market interest
7. Conflating sales funnel size with product quality
8. Launching once and expecting organic traction
9. Hiring sales before understanding sales yourself
10. Pivoting too late because of sunk cost + traction illusion
11. Pivoting too much because execution gets hard
12. Building in isolation without users in the loop
13. Measuring growth instead of retention
14. Funding customer discovery through surveys instead of conversations
15. Treating the MVP as a v1 product rather than an experiment
16. Chasing press/Product Hunt over direct user recruitment
17. Using scalable growth channels before PMF
18. Ignoring "boring" spaces because they're not exciting
19. Avoiding competition (usually means no market)
20. Over-intellectualizing the pivot decision instead of using data
21. Building for a hypothetical future user base instead of the 10 people in front of you
22. Mistaking early adopter enthusiasm for mainstream market signal
23. Not tracking conversion at each step of the sales funnel
24. Writing off sales as "not working" after sending 50 emails

---

## PART 3: THE SKILL SYSTEM

### Design Principles

The skill system is not an information delivery system. It is a **thinking partner with an agenda**: to help the user find a real problem worth solving, validate it without fooling themselves, and build the smallest possible thing to test the hypothesis. Every skill should actively push against the most dangerous cognitive traps, not just provide information.

**Core experience arc:**
```
No idea → Problem space → Problem sharpening → Hypothesis formation →
Customer discovery → Insight synthesis → MVP scoping → First steps
```

Each skill owns one part of this arc and one set of failure modes.

---

### THE 12 SKILLS

---

#### SKILL 1: `startup-readiness-check`

**What it does:**  
Before the user goes anywhere near an idea, this skill runs them through an honest self-assessment. It asks: Why are you doing this? What's your actual worst-case tolerance? What do you know how to do? This isn't gatekeeping — it's grounding. The skill helps users distinguish between "I want to start a startup" (vague) and "I'm prepared to spend 2-4 years manually recruiting users and rebuilding my product six times" (accurate).

**Key behaviors:**
- Asks about prior domain experience without judgment
- Distinguishes between passion and asymmetric knowledge
- Surfaces what the user has to lose and whether they've thought through it
- Doesn't try to motivate or demotivate — stays diagnostic
- Identifies if the user already has relevant founder-market fit without knowing it

**Problems it prevents:**
- Generic "I want to solve a big problem" framing with no actual edge
- Pursuing startup for status reasons without resilience foundation
- Not factoring in opportunity cost of the idea they're leaving behind

---

#### SKILL 2: `idea-generation`

**What it does:**  
Guides users through the organic idea-surfacing process rather than asking them to manufacture ideas. This skill explores the user's full life history — work, frustrations, domains of expertise, things they've hacked together for themselves — to surface latent startup ideas they already have but haven't recognized.

**Key behaviors:**
- Runs a structured interview through past jobs, lived frustrations, and things the user wished existed
- Identifies domains where the user has asymmetric knowledge
- Helps distinguish real problems from made-up ones
- Actively probes for "what do you do today to solve X?" (current workarounds = real demand signal)
- Generates multiple idea candidates before narrowing
- Explicitly avoids the solution-first trap ("AI is cool, what could I apply it to?")

**Problems it prevents:**
- Manufactured/SISP ideas
- Jumping to the first idea
- Ignoring boring spaces and hard-to-start ideas (which are often the best ones)
- Missing organic ideas the user already has from lived experience

---

#### SKILL 3: `idea-evaluation`

**What it does:**  
Runs a structured, honest diagnostic on any candidate startup idea. Uses a synthesis of YC's 10-question framework and Dalton's quality scoring rubric. Produces a clear-eyed assessment, not hype.

**Key behaviors:**
- Tests founder-market fit (not "are you interested?" but "are you specifically positioned?")
- Evaluates market size with the two-category distinction: big now vs. small-but-fast-growing
- Assesses problem acuteness ("what do people do today instead?")
- Probes for tar pit signals (has this been tried before? why didn't it work?)
- Evaluates ease of getting started
- Checks for existing competition as a *positive* signal (no competitors often = no market)
- Identifies the specific new insight that makes this idea viable now vs. 5 years ago
- Gives an honest composite score

**Problems it prevents:**
- Tar pit ideas (ideas that look great but have structural failure modes)
- Ideas with no founder-market fit
- Ideas where "no competition" is mistaken for a good sign
- Ideas where the market is large but homogeneous and the user has no wedge

---

#### SKILL 4: `anti-bias-checkup`

**What it does:**  
A standalone cognitive-bias diagnostic that can be triggered at any point in the process. Most valuable just before a user commits to an idea or after they've done some initial validation. Surfaces the specific psychological traps — confirmation bias, sunk cost, false consensus, small sample fallacy — and gives the user concrete de-biasing questions to answer.

**Key behaviors:**
- Runs through the 9 founder bias types with diagnostic questions for each
- Asks "what would it look like if you were wrong about this?"
- Surfaces the user's emotional investment and separates it from evidence
- Checks if validation methodology is behavioral or attitudinal
- Can be run as a pre-mortem: "Assume the company failed. What was the most likely reason?"

**Problems it prevents:**
- Confirmation bias laundering (designing tests to confirm rather than challenge)
- Mistaking politeness for validation
- Over-weighting small positive samples
- Sunk-cost-driven failure to pivot

---

#### SKILL 5: `problem-sharpening`

**What it does:**  
Takes a vague problem space ("companies want to reduce carbon emissions") and helps the user drill down to a specific, tractable, valuable problem that a startup could actually address. This is the difference between "healthcare is broken" and "ERPs used by independent orthopedic practices have no scheduling integration with insurance pre-auth workflows."

**Key behaviors:**
- Uses repeated "who specifically?" and "in what situation exactly?" interrogation
- Maps the current workflow in detail: who does what, with what tools, how often, at what cost
- Identifies where the most pain is concentrated
- Helps distinguish the user (the person who feels the pain) from the buyer (the person who pays)
- Surfaces adjacent problems to compare acuteness
- Helps the user articulate the problem in the customer's language, not their own

**Problems it prevents:**
- Problems that are too abstract to build a product around
- Solutions designed for a hypothetical customer rather than a specific one
- Missing the buyer/user distinction (especially in B2B)

---

#### SKILL 6: `hypothesis-formation`

**What it does:**  
Converts a sharpened problem into a testable scientific hypothesis. This is the bridge between "I think there's a problem" and "here's the experiment I'll run to find out." Draws heavily on Lean Startup methodology.

**Key behaviors:**
- Formats hypotheses as: "We believe [customer type] has [problem] and will [behavior change / payment] because [insight]"
- Distinguishes the value hypothesis (does this create real value?) from the growth hypothesis (can it spread?)
- Identifies the single riskiest assumption and makes it the first thing tested
- Prevents multi-hypothesis testing (only test one thing at a time)
- Sets pre-committed success criteria: "we'll conclude this is working if X people do Y by date Z"
- Forces specificity about what "success" looks like before testing

**Problems it prevents:**
- Testing everything at once and learning nothing
- Moving goalposts after experiments (HARKing: Hypothesizing After Results are Known)
- Building the whole product to test a hypothesis that a landing page could test in a week

---

#### SKILL 7: `customer-discovery`

**What it does:**  
Teaches the full Mom Test methodology for conducting honest, useful customer interviews. This is one of the highest-leverage skills in the system — bad interviews are far worse than no interviews because they produce false confidence. This skill is interactive: it can help the user *prepare* for interviews (scripting questions), *debrief* after interviews (was that signal real?), and *synthesize* patterns across multiple conversations.

**Key behaviors:**
- Teaches the core rule: ask about their life and past behavior, not their opinions or hypothetical futures
- Provides specific interview question templates for different contexts
- Role-plays as a skeptical interviewer to help users practice
- Identifies bad question types (leading, hypothetical, feature-focused)
- Teaches to recognize and ignore: compliments, wishlists, hypothetical fluff
- Teaches to recognize genuine signal: current workarounds, money already being spent, expressed urgency
- Helps distinguish discovery interviews (pre-product) from validation interviews (post-prototype)
- After an interview, runs a debrief: "what did you hear? what did it actually mean?"

**Problems it prevents:**
- Interviews that collect compliments instead of insights
- Presenting the idea before understanding the problem
- Confusing enthusiasm for evidence
- Stopping at 3 interviews and drawing strong conclusions
- Asking "would you use this?" (universally misleads)

---

#### SKILL 8: `signal-vs-noise`

**What it does:**  
Helps users distinguish genuine market signals from noise after they've done discovery work. This is the hardest interpretive skill in startups — the difference between "this feedback means I'm on to something" and "this feedback means people were being polite." Works on interview transcripts, early user data, sales conversations, and any other evidence the user has gathered.

**Key behaviors:**
- Classifies evidence as behavioral (strong) or attitudinal (weak)
- Applies the Mom Test filter: would this person's answer change if they were your mom?
- Flags false positives: early traction from friends/network, launch day spikes, media attention
- Asks for the customer's current behavior: "what are they using today? how much does it cost? how long have they used it?"
- Tests for desperation: "would they use a worse solution than yours right now?"
- Identifies the friend zone: "they like it but don't need it"
- Summarizes what the user actually learned vs. what they thought they learned

**Problems it prevents:**
- Hallucinating PMF from early traction
- Mistaking politeness for market interest
- The uncanny valley of PMF (small traction that prevents pivoting)
- Building on false validation from non-target users

---

#### SKILL 9: `mvp-design`

**What it does:**  
Helps users design the smallest possible experiment that tests their specific hypothesis. Actively fights scope creep and the "fake Steve Jobs" impulse. The output is not a product spec — it's an experiment design with a clear question, a clear test, and a clear success criterion.

**Key behaviors:**
- Starts with the hypothesis (from skill 6) and works backward to the minimal test
- Asks "what's the fastest way to find out if this hypothesis is true?"
- Proposes alternatives to building (landing page, concierge MVP, manual delivery, Wizard of Oz)
- Helps cut the feature list ruthlessly: "which of these features is required for the hypothesis test? all others wait."
- Sets a hard time constraint (2-6 weeks) and holds to it
- Identifies the specific user segment to test with (the "hair on fire" customer)
- Distinguishes "need to have" from "nice to have" at MVP stage
- Generates the success criteria: "the experiment succeeds if X people do Y"

**Problems it prevents:**
- Six-month MVPs that are actually v1 products
- Testing too many hypotheses at once
- Building for the mainstream customer before the early adopter
- "We'll need this feature eventually" reasoning
- Perfectionism as procrastination

---

#### SKILL 10: `first-customer-playbook`

**What it does:**  
Takes the user from "I have an MVP" to "I have my first 10 paying customers." Covers manual outreach, the sales funnel, email writing, qualifying calls, demos, pricing, and onboarding. Built entirely around the "do things that don't scale" philosophy.

**Key behaviors:**
- Builds the prospecting list with the user (who specifically, how to find them)
- Drafts the outreach email using YC's framework (short, plain text, specific value prop, founder credibility, clear CTA)
- Calculates backwards from goal to required outreach volume
- Sets up a simple tracking system (spreadsheet or CRM)
- Teaches the qualifying call structure: ask first, pitch second
- Advises on pricing (charge from day one; free trials are almost always wrong; money-back guarantee vs. free trial)
- Covers onboarding as part of the sales process, not after
- Identifies the easiest customers first: personal network → startups → small companies → large companies

**Problems it prevents:**
- Launching and waiting for organic growth
- Sending 50 emails and concluding sales doesn't work
- Offering free trials to avoid rejection
- Charging too little and destroying value perception
- Skipping onboarding and producing churn

---

#### SKILL 11: `pivot-or-persevere`

**What it does:**  
Provides a structured, data-driven framework for deciding whether to pivot, and if so, to what. Designed to cut through the psychological fog — loss aversion, sunk cost, optimism bias — that prevents founders from making clear decisions at the right time. Also helps users generate quality pivot candidates and evaluate them using Dalton's quality scoring rubric.

**Key behaviors:**
- Audits the current evidence: behavioral signals vs. attitudinal signals
- Checks for the uncanny valley of PMF: small traction that justifies neither pivoting nor persevering
- Runs the opportunity cost calculation: "given months invested and current signal, what's the expected value of continuing vs. starting fresh?"
- Pre-mortem exercise: "assume this fails — what's the most likely cause?"
- If pivoting: helps generate idea candidates rooted in what was learned
- Scores pivot candidates on Dalton's four criteria (market size, founder-market fit, ease of starting, early market feedback)
- Identifies the pivot that's both higher quality AND easier to start quickly

**Problems it prevents:**
- Pivoting too late due to sunk cost
- Pivoting too early when the idea is good but execution is hard
- Pivoting to whatever seems hot rather than what the current data suggests
- Chronic pivoting (the "dodge the sales call" pivot pattern)
- Not pivoting at all due to inspirational stories about persistence

---

#### SKILL 12: `one-liner-and-positioning`

**What it does:**  
Helps the user craft a precise, jargon-free one-sentence description of what they're building. This is both a communication skill and a diagnostic tool — if you can't describe your product clearly in one sentence, you don't understand it well enough. Covers company description, value proposition, and positioning.

**Key behaviors:**
- Teaches the "what, not why" rule for first descriptions
- Strips jargon, buzzwords, and marketing language
- Pressure-tests the description: "could your grandfather understand this?"
- Tests X-for-Y construction validity (only use if X is a household name AND Y is a large market AND the analogy is actually accurate)
- Helps articulate the specific insight: why is this better than what exists today?
- Generates multiple candidate descriptions and pressure-tests each
- Works backward from "what problem does this solve for whom?" to "here's the sentence"

**Problems it prevents:**
- "Know-how and synergy platforms" (zero-information descriptions)
- Mission-statement framing before product description
- X-for-Y constructions where X is niche
- Descriptions that explain what the company does for the founder rather than the customer

---

### ORCHESTRATION: How the Skills Work Together

The skills are designed to be used in sequence but triggered by user state, not mechanically. The assistant should be able to:

**Entry points:**
- "I have no idea" → Skills 1 → 2 → 3
- "I have an idea" → Skill 3 → 4 → 5
- "I've been talking to users" → Skill 7 (debrief) → 8
- "I've been building for months and nothing is working" → Skill 4 → 11
- "I'm ready to get customers" → Skill 10

**Cross-cutting behaviors (not skills, but assistant behaviors):**
- **Steel-man the user's idea before critiquing it** — Always articulate the best version of an idea before pointing out problems
- **Name the bias before applying the antidote** — When a user is showing confirmation bias, say so explicitly before redirecting
- **Use real anchors** — When making points about market size, timelines, conversion rates, always use real examples (Brex, Stripe, Airbnb) rather than generic advice
- **Don't validate what shouldn't be validated** — If an idea fails the basic tests, say so directly. Diplomatic dishonesty is harmful here.
- **Push toward action** — After any analysis, the output should be an action the user can take in the next 48 hours, not a framework to think about

---

### WHAT THIS SYSTEM IS NOT

- It is not a business plan generator
- It is not a pitch deck assistant
- It is not a market research service
- It is not a cheerleader

It is a rigorous thinking partner that helps users find a real problem, talk to real people about it, and build the minimum necessary thing to find out if they're right — before they've spent six months building something nobody wants.

---

*Sources: YC Startup School (Paul Graham, Michael Seibel, Dalton Caldwell, Jared Friedman, Gustav Alstromer); The Mom Test (Rob Fitzpatrick); The Lean Startup (Eric Ries); The Four Steps to the Epiphany (Steve Blank); First Round Capital research; CB Insights startup failure analysis; behavioral economics literature on founder cognitive biases.*
