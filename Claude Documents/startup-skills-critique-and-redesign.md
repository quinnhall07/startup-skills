# Startup Assistant Skills — Deep Critique & Redesign
## Brainstorm, Connections, Contradictions, and the Revised System

---

## THE THESIS (Revised)

The original 12 skills lacked a thesis. They had a goal ("help founders build MVPs") but not an argument. Here's the argument:

> **The most expensive mistake in startups is building something people don't want. The second most expensive is discovering this after six months instead of six days. These skills exist to dramatically compress the time between "I have an idea" and "I know whether this idea is real" — by combining the founder's domain intuition with Claude's ability to research, synthesize, pressure-test, and build at scale. The human does what only humans can do: have domain knowledge, build relationships, make judgment calls, and sell. Claude does what only Claude can do: generate competing hypotheses, mine the internet at scale, identify cognitive biases in real time, and build artifacts that test assumptions. The synthesis of these two produces startup insight that neither could reach alone.**

This thesis dictates every design decision below.

---

## PART 1: CRITIQUE OF THE ORIGINAL 12 SKILLS

### Structural Problems (Before Even Looking at Individual Skills)

**Problem 1: They're a pipeline, not a system.**
The 12 skills are organized as a linear sequence, implying people always start at step 1, progress neatly through 12, and exit with an MVP. Real startup work is recursive, non-linear, and messy. A founder who's been building for 3 months and is stuck needs to enter at step 9, not step 1. A technical founder with deep expertise needs to skip straight to problem sharpening. The system must support arbitrary entry points without requiring the user to understand which skill applies to their situation.

**Problem 2: They're passive — they wait for the user to feed them.**
With one partial exception (`idea-generation`), all 12 skills respond to what the user provides. But Claude should be generating its own research in parallel. When a user describes a problem, Claude should be simultaneously:
- Searching Reddit threads where similar problems are being discussed
- Mining G2/Capterra/App Store for complaints about existing solutions
- Looking at job postings to understand what companies are paying to solve this problem
- Checking if similar startups have launched and what happened to them

None of the 12 skills do this. They're consultants, not researchers.

**Problem 3: No shared state.**
As a user works through these skills over a long session, the context becomes incoherent. There's no "startup state document" — a living summary of what's been established, what's been hypothesized, and what's been validated. Without this, every skill starts from scratch, forcing the user to re-explain their situation. Context mush is the silent killer of long AI-assisted sessions.

**Problem 4: Anti-bias is siloed.**
Making `anti-bias-checkup` a standalone skill implies bias is an occasional problem that needs a specific intervention. It isn't. Bias — specifically confirmation bias, sunk cost, optimism bias, and the small sample fallacy — is active in *every conversation*, at every stage. It shouldn't be a skill you invoke; it should be a persistent behavior woven into every skill.

**Problem 5: PMF is not tracked continuously.**
The original system has no concept of a running PMF score. Product-market fit is treated as something you assess at the end, not something you track throughout. But the whole point is to identify PMF signals early and often. Every piece of evidence the user brings — from a user interview, a sales call, a usage pattern — should be logged, classified (behavioral vs. attitudinal), and used to update a running assessment.

**Problem 6: No connection to actual building.**
The original MVP skill produces a spec, but there's no bridge to Claude actually building it. The `writing-plans` + `executing-plans` pathway from the superpowers system exists and is excellent. We're not using it.

---

### Critiques of Individual Skills

**`startup-readiness-check`:** Well-intentioned but potentially patronizing for users who already have an idea and just want to start. More importantly, it front-loads self-assessment before any research, which creates a false premise: the user's self-assessment is based on who they think they are, not on what the market actually needs from them. Better to make this intake-style — gather context, don't gate.

**`idea-generation`:** Relies almost entirely on the user's self-report. This is the weakest skill in the system. Claude should be doing at least 60% of the ideation work — researching the user's professional background, looking at common pain points in their stated domain, mining forums for underserved problems — and presenting findings to the user as prompts. The current version just asks better questions.

**`idea-evaluation`:** Reasonably good, but static. It runs once and produces a score. It should instead be a framework that the whole system updates continuously. The 10 questions should be answered incrementally as evidence comes in, not as a one-time diagnostic.

**`anti-bias-checkup`:** Should not be a skill at all. Should be a persistent behavior.

**`problem-sharpening`:** This is actually one of the strongest, but needs subagent research support. The question "what words do customers use to describe this problem?" should be answered by Claude searching Reddit/forums, not just prompting the user.

**`hypothesis-formation`:** Good but too academic-feeling. Real founders don't think in hypotheses naturally. The skill needs to do the translation work — take what the founder believes and format it as a testable proposition, using their natural language.

**`customer-discovery`:** The methodology is solid (Mom Test-aligned), but it needs an interactive component. Claude should be able to: (a) prepare a custom interview script for the user before they go talk to customers, (b) debrief them after conversations, and (c) synthesize patterns across multiple debriefs. The current version just explains the method.

**`signal-vs-noise` and `customer-discovery`:** These overlap significantly. Both deal with what customer conversations mean. Consolidate into one skill with two modes: preparation and debrief.

**`mvp-design`:** Good scoping logic, but completely disconnected from actual building. Should hand off to `brainstorming` → `writing-plans` → subagent execution. Also lacks rapid validation alternatives — sometimes you don't need to build anything, you need a landing page with a "Sign Up" button.

**`first-customer-playbook`:** The strongest skill in the original set. Concrete, actionable, and fills a real gap. Needs subagent support for prospecting research.

**`pivot-or-persevere`:** Good structure, but needs data. You can't make this decision without looking at your evidence log. It should import from the startup state document, not ask the user to summarize their situation from memory.

**`one-liner-and-positioning`:** This is misplaced at the end. A founder who can't describe their product in one sentence doesn't understand it well enough to validate it. This should come much earlier — and should be refined continuously as understanding deepens.

---

## PART 2: WHAT WE'RE LEAVING ON THE TABLE

### Claude's Unique Capabilities We're Not Using

**1. Parallel internet research (the biggest miss)**
Every time a user describes a problem, Claude should launch a research burst:
- "What are the top Reddit threads about this problem?" → Web search
- "What do people hate about existing solutions?" → Mine G2, Capterra, App Store reviews
- "Has anyone tried to start a company solving this?" → Product Hunt, YC, Crunchbase
- "What jobs are companies posting that signal this pain?" → LinkedIn/Indeed job posting analysis
- "What are the vocabulary terms customers use?" → Forums, community language

In claude.ai, this is done with the web search tool in rapid succession. In Claude Code, this is done with parallel subagents. The key insight is that Claude can do in 90 seconds what would take a founder 3 hours of Googling.

**2. Competitive landscape mining**
Not just "is there competition?" but a full picture: who's building in this space, what are their strengths/weaknesses (from reviews, not marketing copy), what's their pricing, who are their customers, what are they missing. Claude can synthesize this from public sources.

**3. Synthetic ICP generation + validation**
Claude can generate a detailed Ideal Customer Profile based on the problem description, then immediately search for real examples of that profile online (job titles, LinkedIn profiles, communities they belong to, where they ask questions). This gives the founder a research-backed starting point for who to talk to, rather than asking them to generate it from intuition.

**4. Rapid artifact generation**
For validation purposes, Claude can:
- Build a landing page (React/HTML artifact) in under 5 minutes
- Draft 10 variations of an outreach email for A/B testing
- Create a fake demo video script
- Generate survey questions calibrated to detect actual intent vs. polite interest
- Write a pitch deck from scratch (using the PPTX skill)
- Draft a cold email sequence for a specific ICP

**5. Pattern matching across startup archetypes**
Claude has absorbed enormous amounts of startup history. When a user describes their idea, Claude should immediately identify: "This has structural similarities to X, Y, and Z companies at their early stages. Here's what worked, here's what didn't." This is pattern recognition at a scale no human mentor could match.

**6. Devil's advocate mode at will**
Claude can fluently argue against any idea, identify its weakest points, and simulate skeptical investors, resistant customers, or future competitors. This is invaluable for stress-testing assumptions — but it needs to be activated deliberately, not just on request.

**7. Hypothesis stress-testing with synthetic scenarios**
Claude can generate 10 customer personas and walk through how each would respond to the product. Not as prediction, but as a structured way to discover assumptions the founder hasn't made explicit.

---

## PART 3: THE HUMAN-CLAUDE DIVISION OF LABOR

This is arguably the most important design principle and the one most conspicuously absent from the original skill list.

**Only the human can:**
- Have genuine domain expertise and lived experience
- Build real relationships with potential customers
- Actually make sales calls and run customer interviews
- Make judgment calls about what they're willing to sacrifice
- Notice things in physical environments, in-person meetings, body language
- Bring authentic conviction that sells ideas to skeptics
- Ultimately decide to start, pivot, or quit

**Only Claude can:**
- Research the internet at scale in seconds
- Generate 20 competing hypotheses without exhaustion or attachment
- Maintain a perfectly consistent analytical framework across a long conversation
- Apply cognitive bias detection in real time without social awkwardness
- Build functional prototypes in minutes
- Synthesize patterns across hundreds of startup stories simultaneously
- Play multiple adversarial roles (investor, skeptic, competitor) fluently
- Never forget what was established earlier in the conversation

**The synthesis (what neither can do alone):**
- Organic idea surface: the user has the domain intuition, Claude has the market research
- Customer interview prep: the user knows the target, Claude designs the questions and avoids bias
- Signal interpretation: the user was in the room, Claude applies the Mom Test framework to what they heard
- MVP scoping: the user knows what's technically feasible, Claude enforces discipline on scope
- Outreach: the user has the network, Claude drafts the emails and tracks the funnel

Every skill should be explicit about this division. The user should never be asked to do something Claude should be doing, and Claude should never pretend to replace the uniquely human components.

---

## PART 4: SUBAGENT ARCHITECTURE

### In claude.ai (Current Platform)

The web search tool is the primary subagent equivalent. The pattern should be:

1. **Research burst**: When a topic requires internet validation, Claude runs 3-5 targeted searches in rapid succession and synthesizes the results before responding. This should happen automatically, not on request.
2. **Parallel hypothesis testing**: Claude can propose 3 competing interpretations of a market situation and search for evidence for each one simultaneously (using multiple tool calls in sequence, synthesizing before presenting).
3. **Artifact-based research assistants**: Using the stored API credentials in artifacts, Claude can build research tools that run Claude API calls for specific sub-tasks (e.g., "analyze these 20 customer interview quotes and classify them as behavioral vs. attitudinal signals").

### In Claude Code CLI (Building Phase)

Once the validation phase is complete and the user is ready to build:
1. The startup skills hand off a complete spec to `brainstorming`
2. `brainstorming` → `writing-plans` → parallel subagent execution via `subagent-driven-development`
3. True parallel subagents can simultaneously build different components of the MVP
4. The startup context (ICP, hypothesis, success criteria) travels as context into the code

### The Cross-Platform Handoff Protocol
The startup state document (see below) is the artifact that bridges the two platforms. When moving from claude.ai to Claude Code, the user copies the state document and it provides the full context for what's being built and why.

---

## PART 5: PMF AS A RUNNING SCORE

This is where the original system most dramatically underdelivers.

Product-market fit should be tracked as a living score from the first conversation. Every piece of evidence gets classified and weighted:

```
EVIDENCE LOG FRAMEWORK

Type                  | Weight | Examples
----------------------|--------|--------------------------------------------------
Behavioral - payment  | ★★★★★  | "Paid $X for a workaround today"
Behavioral - time     | ★★★★   | "Spends 4 hours/week on this manually"
Behavioral - urgency  | ★★★★   | "We need this before the end of quarter"
Attitudinal - strong  | ★★     | "This is my #1 pain point right now"
Behavioral - referral | ★★★★★  | "I told my colleague about this"
Attitudinal - mild    | ★       | "That's interesting"
Attitudinal - polite  | ✗       | "Sounds cool, I'd maybe try it"
Hypothetical          | ✗       | "I would definitely use that"
```

The skills should maintain this log and surface warnings when:
- The user is making decisions based only on attitudinal evidence
- The evidence sample is too small to draw conclusions (<10 conversations)
- The attitudinal evidence is almost uniformly positive (red flag: everyone is being polite)
- No one has expressed urgency, commitment, or current workaround behavior

The PMF score is not a final grade — it's a compass. Skills reference it throughout: "Based on your current evidence, your PMF score is 3/10 — you have attitudinal interest but no behavioral commitment. Before moving forward, you need [X]."

---

## PART 6: FALSE SIGNAL DETECTION FRAMEWORK

This is a specific set of reasoning patterns that should be built into the `signal-audit` skill and referenced across all others.

**False Signal Type 1: The Enthusiasm Trap**
Symptoms: "Everyone I've shown this to loves it." 
Detection: Ask — was anyone in that group a potential paying customer? Would they pay today? What did they say they'd change?
Response: Enthusiasm without commitment is not a signal. It's a measure of your likability.

**False Signal Type 2: The Small Sample Fallacy**
Symptoms: "3 people said they'd definitely use this."
Detection: 3 people is not data. Even 10 people is barely data.
Response: You need to have had 20-30 targeted conversations before concluding anything about the market.

**False Signal Type 3: Launch Day Spike**
Symptoms: "We got 500 signups in the first week!"
Detection: What's the week-3 retention? Did they come back?
Response: Launch day interest is curiosity, not demand. Return usage is demand.

**False Signal Type 4: The Network Halo**
Symptoms: Users are founders' friends, ex-colleagues, or family.
Detection: Would a stranger pay for this? Have you talked to strangers?
Response: People who like you will try things people who don't know you wouldn't touch.

**False Signal Type 5: The Polite Customer**
Symptoms: Customer meetings end with "send me more info" or "we'd love to see a demo."
Detection: Did they agree to a next step with a specific date and commitment? Did they share internal data or introduce you to colleagues?
Response: Polite customers are not interested customers. Real interest has urgency.

**False Signal Type 6: The Feature Request Mirage**
Symptoms: "Users keep asking for X feature, so they must love the product."
Detection: Are they actually using the core product? Are they paying?
Response: Feature requests mean the product is not yet right, not that it's close.

**False Signal Type 7: Press / Social Attention**
Symptoms: "We got on TechCrunch / Product Hunt."
Detection: How many of those visitors became regular users? How many paid?
Response: Press drives curiosity, not customers. It's almost never correlated with PMF.

---

## PART 7: PERSONALIZATION LAYER

The original system is one-size-fits-all. A first-time founder who's never shipped a product has completely different needs than a technical founder who's been building for years. The system needs a personalization intake that shapes everything downstream.

**Dimensions to capture in intake:**

1. **Startup archetype**
   - B2B SaaS (enterprise vs. SMB)
   - Consumer app
   - Marketplace
   - Developer tools
   - Hardware/physical product
   - Services/consulting with product ambition
   - Content/media
   
   *Why this matters:* B2B sales cycles are radically different from consumer funnels. Hardware has minimum order quantities. Marketplaces have cold start problems. The skills should adapt their advice to the archetype.

2. **Founder profile**
   - Technical (can build)
   - Domain expert (knows the space)
   - Business-oriented (can sell)
   - First-time founder
   - Repeat founder
   
   *Why this matters:* A technical founder with no domain expertise needs idea generation help. A domain expert who can't code needs MVP scoping that doesn't require coding.

3. **Time horizon**
   - "I want something live in 4 weeks" → Skip straight to rapid validation + MVP
   - "I'm exploring for 3 months" → Run the full discovery process
   - "I need to decide whether to quit my job" → Focus on signal quality + evidence accumulation

4. **Resource reality**
   - Solo founder, nights and weekends
   - Full-time with savings runway
   - Team + seed money
   
   *Why this matters:* Time to PMF constraints change what's realistic to test.

5. **Starting point**
   - "I have no idea"
   - "I have a problem I've observed"
   - "I have a product I've been building"
   - "I have paying customers but growth has stalled"

This intake shapes which skills activate, in what order, and at what depth.

---

## PART 8: CONTEXT MANAGEMENT — THE STARTUP STATE DOCUMENT

Long sessions become incoherent. The solution is a living **Startup State Document** — a persistent artifact that every skill reads from and writes to. It travels with the conversation and prevents context mush.

```markdown
# Startup State — [Startup Name / "Unnamed"] — [Date]

## Founder Profile
- Domain expertise: [what you know deeply]
- Technical ability: [can build / needs builder]
- Time horizon: [weeks to MVP]
- Business type: [B2B SaaS / consumer / etc.]
- Starting point: [idea / problem / product / stuck]

## Current Hypothesis
"We believe [customer type] experiences [specific problem] when [specific situation],
and will [pay / switch / change behavior] because [insight about why now]."

## Target Customer (ICP)
- Role/type: 
- Company/context:
- Current workaround:
- Signs of urgency:
- Where to find them:

## Evidence Log
| # | Date | Source | Evidence | Type | Weight | PMF Impact |
|---|------|--------|---------|------|--------|-----------|
| 1 | ... | Interview - Jane | "I spend 3 hours/week on this" | Behavioral | ★★★★ | +2 |

## PMF Running Score
- Behavioral evidence quality: X/10
- Commitment signals: X/10
- Sample size adequacy: X/10
- Current PMF assessment: [pre-signal / early signal / converging / clear]
- Required before next stage: [specific evidence needed]

## False Signals Detected
- [List any signals that have been flagged as low-quality]

## What We Know vs. What We've Assumed
| Item | Status | Source |
|------|--------|--------|
| Problem is real | Assumed | Need validation |
| Customer will pay | Assumed | Need validation |

## Competitive Landscape
- Existing alternatives:
- Why they're insufficient:
- Our specific insight:

## MVP Hypothesis
- What we're building:
- What it tests:
- Success criteria:
- Timeline:

## Current Decision Point
[ ] Still discovering
[ ] Ready to validate
[ ] Ready to build
[ ] Pivot needed
[ ] Building

## Next Action (human)
[Specific thing the founder does next — call 5 people, post in X community, etc.]

## Next Action (Claude)
[Research, draft, analysis Claude should continue in parallel]
```

Every skill begins by reading this document and ends by proposing updates to it.

---

## PART 9: INTEGRATION WITH THE SUPERPOWERS SYSTEM

The superpowers system is designed for development work. Our startup skills are pre-development. But the integration points are significant:

**Adopting superpowers patterns:**
- The `brainstorming` skill's one-question-at-a-time approach with proposed approaches should be used in `founder-intake` and `problem-focus`
- The `brainstorming` visual companion should activate during ICP visualization, competitive landscape mapping, and MVP architecture discussions
- The hard gate pattern ("do NOT proceed until the user approves the design") applies in our system when moving from discovery to building

**Feeding into superpowers:**
- `mvp-architect` produces a spec that hands directly to `brainstorming` → `writing-plans`
- The startup state document becomes the CLAUDE.md equivalent for the development phase
- `outreach-engine` creates email artifacts that connect to Claude's message compose capabilities

**The transition point:**
When the user signals "I'm ready to build," the startup skills formally hand off to the superpowers system. The handoff message should include: the full startup state document, the MVP spec, the ICP (as user context for Claude Code), and a clear success criterion.

**Important nuance:** The existing superpowers are built for Claude Code. Many users of these startup skills will be running in claude.ai. The startup skills must be designed for claude.ai first, with a clear "level up" pathway to Claude Code when they're ready to build.

---

## PART 10: RAPID VALIDATION TECHNIQUES (WHAT CLAUDE CAN DO RIGHT NOW)

This was almost entirely absent from the original skill list. Rapid validation means finding out whether an assumption is true before spending significant time or money.

**Tier 1: Things Claude can do immediately (no user action required)**
1. **Forum mining**: Search Reddit, HN, and niche communities for people complaining about the problem → evidence of pain existence
2. **Competitor review mining**: Analyze top complaints on G2, Capterra, and App Store for existing solutions → evidence of solution gaps
3. **Job posting analysis**: Search for job postings related to the problem → companies actively paying to solve this = real demand
4. **Failed startup research**: Research companies that tried this before → understand structural obstacles
5. **Community language mapping**: Identify exact words/phrases people use when describing the problem → critical for interview scripts and outreach

**Tier 2: Claude builds the validation artifact (user deploys it)**
1. **Landing page** (React/HTML artifact, live in 5 minutes): "Sign up to be notified" + value prop → measures whether anyone cares
2. **Fake door test page**: A product page with a "Buy Now" or "Get Access" button that tracks clicks before the product exists
3. **Survey instrument**: Calibrated to the Mom Test — asks about behavior, not opinions → user deploys to target community
4. **Cold outreach email**: Drafted for a specific ICP with value prop and clear CTA → user sends
5. **Problem validation post**: Drafted for relevant subreddit/LinkedIn/community → post to see response

**Tier 3: Things the human must do (but Claude prepares them for)**
1. Customer interviews (Claude drafts the script, debriefs after)
2. Posting in communities (Claude drafts the post)
3. Direct outreach (Claude writes the emails, analyzes the replies)
4. Demos and sales calls (Claude preps talking points and objection responses)

---

## PART 11: CONNECTING FOUNDERS WITH RESOURCES AND PEOPLE

**What Claude can do:**
- Search for founders who've built similar companies and surface their writing/talks
- Find relevant podcasts episodes (HoIBT, My First Million, YC podcasts)
- Surface relevant communities: specific subreddits, Slack groups, Discords, Indie Hackers threads
- Identify relevant YouTube channels and specific video recommendations
- Draft an outreach message to a specific founder the user wants to connect with
- Search LinkedIn for people with relevant titles in target companies

**Curated resource stack to surface at appropriate points:**
- *The Mom Test* (Fitzpatrick) → when entering discovery phase
- *The Lean Startup* (Ries) → when entering MVP phase
- YC Startup School video library (the exact videos from the knowledge base) → specific videos by topic
- Indie Hackers (specific threads, founder interviews) → community
- *Do Things That Don't Scale* (PG) → when user resists manual customer acquisition
- HN "Ask HN: Who is hiring?" → job posting analysis
- Lenny's Newsletter → go-to-market by company type
- First Round Capital review articles → tactical playbooks by stage

**Human network activation:**
At specific points, the skills should prompt the user to leverage existing relationships:
- "Who in your network works in [target industry]? Even one conversation with a warm intro is worth 10 cold outreaches."
- "Do you have former colleagues who are now founders? They're the easiest first customers for B2B tools."
- "LinkedIn: Here's how to search for [target ICP] in your second-degree network."

---

## PART 12: DATA ANALYSIS OPPORTUNITIES

There are several points where real data analysis — not just research — would dramatically improve outcomes:

**1. Survey response analysis**
After running a problem validation survey, Claude can analyze results, classify responses by signal quality, and generate a PMF assessment with confidence intervals.

**2. Interview transcript analysis**
User pastes 5 interview transcripts. Claude: classifies every statement as behavioral vs. attitudinal, surfaces the highest-signal quotes, identifies patterns across interviews, generates an updated hypothesis based on what was learned.

**3. Conversion funnel analysis**
User provides their landing page metrics (visitors, signups, conversions). Claude: calculates conversion rates, identifies where the funnel breaks, suggests what this means about message-market fit.

**4. Competitive pricing analysis**
Claude can scrape pricing pages and build a positioning map — where the user's proposed price sits relative to existing solutions and what positioning that implies.

**5. Sales funnel tracking**
The first-customer-playbook should include a lightweight tracking framework. Claude can analyze the user's outreach data (X emails sent, Y responses, Z demos, N customers) and calculate conversion rates, identify where to focus improvement.

---

## PART 13: THE MVP BUILDING CHAIN

When the user is ready to build, the flow should be:

```
startup skills → startup state document → brainstorming → writing-plans → 
[if claude.ai] inline execution / [if Claude Code] subagent-driven-development
```

**Artifacts Claude should produce during this phase:**
1. **Landing page** (HTML/React artifact): Tests demand before writing backend
2. **Pitch deck** (PPTX via skill): Forces clarity on problem/solution/market; also useful for investor conversations
3. **Outreach email templates** (Markdown artifact): Ready-to-send for first customer acquisition
4. **MVP spec document** (Markdown or DOCX): Handed to Claude Code for execution
5. **Customer interview guide** (Markdown): Structured for the user's specific ICP

**Platform guide for the building phase:**
- **claude.ai**: Discovery, validation artifacts (landing pages, emails, pitch decks)
- **Claude Code CLI**: Actual product code, server-side logic, database
- **Desktop app**: Intermediate — can access local files, useful for reviewing and editing artifacts
- **Cowork (desktop app, non-technical)**: File management, organizing research documents

The skills should make this transition explicit and frictionless.

---

## PART 14: TARGET AUDIENCES

**Persona A: The Domain Expert**
Industry professional who's observed a pain point. Has deep knowledge but limited startup experience. Entry: `idea-pressure-test` (they have the idea, need evaluation). Needs most: competitive landscape research, ICP definition, customer discovery coaching.

**Persona B: The Technical Builder**
Engineer or product person who can build but doesn't know what to build. Entry: `market-scout` (needs to find a market). Needs most: idea generation driven by domain research, problem sharpening, first customer acquisition.

**Persona C: The First-Time Founder (No Idea)**
Motivated but starting from zero. Entry: `startup-skills-guide` → `founder-intake`. Needs most: the full journey, strong scaffolding, lots of examples.

**Persona D: The Stuck Founder**
Has been building for 3-6 months, not gaining traction. Entry: `signal-audit` + `checkpoint-review`. Needs most: honest evidence assessment, bias detection, pivot evaluation.

**Persona E: The Side Project Builder**
Working full-time, building nights/weekends. Entry: `rapid-validate` (needs fast signal with limited time). Needs most: rapid validation techniques, clear go/no-go criteria.

**Persona F: The B2B Founder**
Building for businesses specifically. Different dynamics than B2C — longer sales cycles, buyer/user distinction, enterprise concerns. Skills should have B2B-specific branches.

---

## PART 15: REVISED SKILL ARCHITECTURE

The 12 original skills become 15 revised skills, reorganized into 5 layers. The number is higher because some skills were too merged (discovery + signal interpretation) and some are new (market-scout, rapid-validate, artifact-builder).

---

### LAYER 0: ORIENTATION (runs once)

**SKILL: `startup-skills-guide`** *(new — replaces nothing)*
The initialization skill. Explains what the system does, what to expect, how it works. Asks the minimum necessary questions to personalize everything downstream. Sets up the startup state document. Most importantly: tells the user what *they* will do and what *Claude* will do.

Run at: Beginning, always. Revisit when user is confused about where they are.

---

### LAYER 1: FOUNDATION (runs once, updates throughout)

**SKILL: `founder-intake`** *(replaces `startup-readiness-check`, expanded)*
Structured intake: domain expertise, technical ability, time horizon, business type, starting point. Generates the founder profile section of the startup state document. Not a gate — a context-builder. Includes Claude's independent research: given what the user describes, what do we already know about this domain?

Run at: Once, at start. Updated when context changes significantly.

**SKILL: `one-liner-workshop`** *(moved from position 12 to position 2)*
Early and continuous. Can't describe it → don't understand it. Forces clarification before any validation work begins. Updated as understanding improves. At the start it's a rough first draft; by the end it's precise.

Run at: Early and repeatedly. Every major insight should sharpen the one-liner.

---

### LAYER 2: DISCOVERY (iterative)

**SKILL: `idea-surface`** *(replaces `idea-generation`, expanded)*
Works in two simultaneous tracks: (1) organic surfacing — structured interview through past experience, lived frustrations, things the user wished existed; (2) independent research — Claude searches for underserved problems in the user's stated domain, mining forums, job postings, and community discussions. Outputs multiple idea candidates for pressure testing.

Run at: When user has no idea, or when exploring adjacent ideas.

**SKILL: `market-scout`** *(new — split from `idea-generation`)*
A dedicated research sprint. Given a domain or problem space, Claude launches parallel searches: Reddit/forums for expressed pain, G2/Capterra for competitor weaknesses, job postings for stated company priorities, failed startups for structural obstacles, funding activity for investor validation. Produces a "market intelligence brief" — not a full competitive analysis, but a fast scan that surfaces what's real.

Run at: Any time independent internet research is needed. Triggered automatically by other skills.

**SKILL: `idea-pressure-test`** *(replaces `idea-evaluation`, expanded)*
Takes an idea and runs it against: founder-market fit, market size and growth, problem acuteness, tar pit detection, competitive landscape, ease of starting, new insight (why now?). Pulls live research from `market-scout` rather than relying on the user's self-report. Produces a scored assessment with the single most important gap to address.

Run at: When the user has a specific idea to evaluate.

---

### LAYER 3: VALIDATION (iterative)

**SKILL: `problem-focus`** *(replaces `problem-sharpening` + `hypothesis-formation`, merged and simplified)*
The hardest skill to do well. Takes a vague problem space and sharpens it until a specific, tractable hypothesis emerges. Uses the ICP builder as a component: who exactly? in what situation? doing what? The output is a testable hypothesis in the standard format. Claude does parallel research to validate that the specific customer type actually exists in the numbers claimed. Includes the buyer/user distinction for B2B.

Run at: After idea pressure test passes basic quality threshold.

**SKILL: `discovery-coach`** *(replaces `customer-discovery` + `signal-vs-noise`, merged with two modes)*
Two modes:
- *Prepare mode*: Given the ICP and hypothesis, generates a custom interview script, coaches on Mom Test methodology, provides examples of good vs. bad questions for this specific context.
- *Debrief mode*: User returns from conversations. Claude analyzes what was heard using the false signal detection framework, updates the PMF score, updates the startup state document, and generates a refined hypothesis.
The bias-sentinel behavior is active throughout — Claude actively flags confirmation bias in how the user describes what they heard.

Run at: Before and after every customer conversation.

**SKILL: `signal-audit`** *(kept but redesigned as a continuous tracker, not a one-time diagnostic)*
The PMF running score. Every time new evidence comes in, runs the evidence log update. Periodically (after 5-10 conversations) generates a full PMF assessment: what do we believe, what's the quality of the evidence, what's still unknown, what would change our conclusion? The false signal detection framework runs here. References the startup state document as its source of truth.

Run at: After every new evidence point. Explicitly triggered for full assessments at decision gates.

---

### LAYER 4: EXECUTION (triggered when validation reaches threshold)

**SKILL: `rapid-validate`** *(new — critical gap in original system)*
When the hypothesis is formed but customer interviews aren't enough, or when the user wants to test before investing in a full MVP. Claude: (1) identifies the riskiest assumption that blocks progress, (2) proposes the fastest test to challenge it, (3) builds the test artifact (landing page, fake door, survey, outreach batch), (4) helps the user deploy and interpret results. Explicitly connected to Claude's artifact-building capability.

Run at: After hypothesis formation, before full MVP commitment. Also when user needs quick signal between interview cycles.

**SKILL: `mvp-architect`** *(replaces `mvp-design`, with build handoff)*
Scopes the MVP against the hypothesis. The key question: what is the minimum necessary to test whether [hypothesis] is true? Ruthlessly cuts features using YAGNI against the hypothesis. Sets success criteria. Identifies who the first users are. Produces the MVP spec document. **Explicit handoff**: when approved, invokes `brainstorming` → `writing-plans` for build execution. Recommends claude.ai for landing page / pitch deck artifacts, Claude Code for actual product.

Run at: When validation evidence is sufficient to commit to building.

**SKILL: `outreach-engine`** *(replaces `first-customer-playbook`, with research support)*
Builds the prospecting list using `market-scout` research (who is the ICP, where do they congregate, how to find them). Drafts custom outreach emails. Calculates backwards from customer goal to outreach volume needed. Tracks the funnel. Advises on pricing from day one. Handles the full sequence from first email to closed + onboarded customer.

Run at: When MVP is ready or nearly ready; also for early "will anyone pay?" validation.

---

### LAYER 5: DECISION (recurring checkpoint)

**SKILL: `checkpoint-review`** *(replaces `pivot-or-persevere`, with evidence integration)*
Reads from the startup state document rather than asking the user to summarize. Runs the opportunity cost calculation against current PMF score. Runs the pre-mortem: "assume this fails in 6 months — most likely cause?" Generates a clear recommendation: continue, adjust, or pivot. If pivot: generates pivot candidates and scores them using Dalton's rubric. If continue: identifies the single most important next action.

Run at: Every 4-6 weeks, or when user is feeling stuck.

**SKILL: `artifact-builder`** *(new — draws on platform capabilities)*
On-demand generation of startup artifacts: pitch deck (PPTX skill), one-pager (Markdown), landing page (React/HTML artifact), outreach email sequence, customer interview guide. Each artifact is generated from the startup state document — it reflects the current validated understanding, not guesswork. This skill also generates founder resources: relevant YouTube videos, book recommendations, community links, specific founder profiles to follow.

Run at: Any time a deliverable artifact is needed.

---

### CROSS-CUTTING BEHAVIOR: BIAS SENTINEL *(replaces `anti-bias-checkup` as a skill)*

Not a skill. A persistent behavior that all skills reference.

**Active biases and triggers:**

| Bias | Trigger phrase | Response |
|------|---------------|----------|
| Confirmation bias | "Everyone I've shown this to..." | Flag: how many were target customers? What was the dissent? |
| Sunk cost | "We've put 6 months into this..." | Flag: evaluate on future expected value, not past investment |
| False consensus | "Everyone has this problem" | Flag: who specifically? in what context? what's the current workaround? |
| Small sample | "3 people said..." | Flag: minimum threshold for conclusions is 15-20 targeted conversations |
| Polite customer | "They seemed really interested" | Flag: what commitment did they make? what was the next step? |
| Optimism bias | "I think it'll take 3 months" | Flag: reference class — what did similar things take? |
| Launch fallacy | "Once we launch, people will..." | Flag: launch creates curiosity, not demand. Who will pay before launch? |

Whenever a trigger appears, the bias-sentinel interrupts (briefly) to name the bias, explain the risk, and ask the de-biasing question. It never lectures — it flags and moves on.

---

## PART 16: WHAT WE'RE STILL MISSING

After this full redesign, there are still gaps worth noting:

**1. Revenue model exploration**
We help founders find customers but don't help them think through pricing and monetization models early enough. Different models (SaaS, usage, marketplace take rate, one-time, consulting-to-product) have dramatically different implications for what the MVP needs to demonstrate.

**2. Cofounder dynamics**
The YC materials emphasize how important cofounders are. The skill system treats founders as solo. There should be guidance on when to find a cofounder, what to look for, and how to split equity/roles.

**3. Financial reality check**
How long can the founder actually run this experiment? Monthly burn rate vs. runway is a real constraint that should inform how aggressively to validate before committing resources.

**4. The post-MVP iteration loop**
After the first MVP, what's the product development cycle? Michael Seibel's post on development cycles is excellent and should be the basis for a `product-dev-cycle` skill that activates after early PMF signals appear.

**5. Network effects / cold start problems**
Marketplaces, communities, and platforms have special dynamics (chicken-and-egg problems) that require different validation strategies than standard B2B or consumer products.

---

## PART 17: GITHUB REPO STRUCTURE

```
startup-assistant/
│
├── README.md                          # What this is, how to install, quick start
├── THESIS.md                          # The argument this system makes
├── JOURNEY_MAP.md                     # Visual: how the skills connect, entry points by persona
├── PLATFORM_GUIDE.md                  # claude.ai vs Desktop vs Claude Code — what to run where
│
├── skills/
│   │
│   ├── 00-startup-skills-guide/       # Orientation and initialization
│   │   └── SKILL.md
│   │
│   ├── 01-founder-intake/             # Context and personalization
│   │   └── SKILL.md
│   │
│   ├── 02-one-liner-workshop/         # Continuous clarity check
│   │   └── SKILL.md
│   │
│   ├── 03-idea-surface/               # Organic + research-backed ideation
│   │   └── SKILL.md
│   │
│   ├── 04-market-scout/               # Independent internet research sprint
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── search-playbook.md     # Specific search strategies by problem type
│   │       └── source-quality.md     # Which sources to trust for what
│   │
│   ├── 05-idea-pressure-test/         # Evaluation + tar pit + competitive
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── scoring-rubric.md     # Dalton's rubric, PG's 10 questions
│   │
│   ├── 06-problem-focus/              # Sharpening + ICP + hypothesis formation
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── hypothesis-templates.md
│   │
│   ├── 07-discovery-coach/            # Customer interview prep + debrief
│   │   ├── SKILL.md
│   │   └── references/
│   │       ├── mom-test-principles.md
│   │       ├── question-library.md    # Good/bad questions by scenario
│   │       └── debrief-protocol.md
│   │
│   ├── 08-signal-audit/               # PMF running score + false signal detection
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── evidence-classification.md
│   │
│   ├── 09-rapid-validate/             # Smoke tests, fake doors, landing pages
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── validation-techniques.md  # Full menu of validation options
│   │
│   ├── 10-mvp-architect/              # Scoping + superpowers handoff
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── mvp-examples.md        # Airbnb, Twitch, Stripe early versions
│   │
│   ├── 11-outreach-engine/            # First customers + sales funnel
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── email-templates.md
│   │
│   ├── 12-checkpoint-review/          # Pivot or persevere
│   │   ├── SKILL.md
│   │   └── references/
│   │       └── pivot-scoring.md
│   │
│   └── 13-artifact-builder/           # Pitch decks, landing pages, guides, resources
│       ├── SKILL.md
│       └── references/
│           ├── pitch-deck-structure.md
│           └── resource-library.md    # Books, communities, YouTube, podcasts
│
├── templates/
│   ├── startup-state-document.md      # The living state doc — copy for each user
│   ├── customer-interview-guide.md    # Ready-to-use before first interviews
│   ├── hypothesis-template.md
│   ├── mvp-spec-template.md
│   ├── pmf-evidence-log.md
│   └── outreach-email-sequences.md
│
├── docs/
│   ├── bias-sentinel-reference.md     # Full cognitive bias guide for all skills
│   ├── human-claude-division.md       # Who does what, when
│   ├── pmf-scoring-guide.md           # How to score evidence quality
│   └── superpowers-integration.md     # Exact handoff protocol to superpowers
│
└── examples/
    ├── walkthroughs/
    │   ├── no-idea-to-mvp.md          # Full A-to-Z example session
    │   ├── domain-expert-entry.md     # Starting from a specific problem
    │   ├── stuck-founder-recovery.md  # Entering at checkpoint-review
    │   └── b2b-saas-discovery.md      # B2B-specific nuances
    └── artifacts/
        ├── sample-startup-state.md    # Filled-in example
        ├── sample-pitch-deck.md       # Annotated example
        └── sample-interview-guide.md  # Ready-to-use example
```

---

## FINAL THOUGHT: THE QUESTION THE SYSTEM MUST ALWAYS BE ASKING

Every skill, at every moment, should be oriented around one question:

> **"What would it take to change your mind about this?"**

If the founder can't answer that — if there is no evidence that would cause them to stop — then they're not doing science. They're doing religion. The startup skills exist to make founders into scientists: people who form hypotheses, test them honestly, update their beliefs based on evidence, and move faster toward the truth than any competitor.

The skills don't tell founders what to build. They help founders find out what's true, faster than they could alone.
