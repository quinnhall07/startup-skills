# AI-Era Anti-Patterns

Catalog of the dominant AI-product founder failure modes observed 2024–2026. Direct successor to `tar-pit-detection.md`, but specific to traps that opened up the moment foundation models made building cheap. Sources synthesized: Sequoia ("AI in 2026"), Andrew Chen ("Revenge of the GPT Wrappers"), Sam Altman (developer day commentary), Pieter Levels (indie-hacker postmortems), the Lightcone Podcast (YC partner commentary on the 2024–2025 batches), MIT Sloan and Stack Overflow studies on AI-generated code debt, Proofpoint on the Feb 2024 Gmail/Yahoo deliverability rules, Userology and Nielsen Norman Group on synthetic-user research, and Karpathy's "vibe coding" framing.

The plugin tone is *Aggressive Epistemic Auditor*. These traps fire because building is cheap and founders mistake activity for evidence. Name the pattern, demand the behavioral data, refuse to validate the narrative.

## Decision rule

If a candidate AI product matches one or more of the eight traps below AND the founder cannot produce specific behavioral counter-evidence (retention numbers, gross margin per user, named workflow with dollar cost, authenticated sending stack, real-human interview log), treat the project as untrusted until the counter-evidence exists. The traps are not "considerations" — each is a known mode of failure with a postmortem trail behind it.

Tar pits (the 2018-era list) and AI-era anti-patterns can co-occur. A "ChatGPT for local event discovery" hits Trap 2 and the local-event-discovery tar pit simultaneously. Run both diagnostics.

## 1. Wrapper Without Distribution

**Symptoms.** Thin GPT layer where the only differentiator is the prompt. Pitch shape: "AI for [vertical]" with no proprietary data, no workflow integration, no distribution channel the founder controls.
**Why it fires.** Building is fast; distribution is hard. AI made the demo cheap; the moat is still distribution. Founders confuse "I shipped a working product in a weekend" with "I have a company."
**Detection question.** If OpenAI shipped this feature natively next month, does your startup die?
**Response.** "Yes = wrapper trap. You need at least two of: proprietary data flywheel, workflow embedding (the customer's daily tool of record), integration ecosystem with switching costs, or regulated-industry trust capital. Stop building product features. Build distribution. Andrew Chen, *Revenge of the GPT Wrappers*: defensibility is the question, not capability."

## 2. "ChatGPT for X" Without a Wedge

**Symptoms.** Pitch shape "ChatGPT for [profession]." No specific named workflow, no specific painful trigger event, no specific data the founder owns or accesses. The deck has a TAM slide and a "GPT-4 powered" slide and no ICP slide.
**Why it fires.** Founders pattern-match to existing categories ("Salesforce for ___", "Stripe for ___") without naming what is specifically broken. The category language hides the missing wedge.
**Detection question.** Name a specific workflow this replaces and the dollar cost of doing it the current way.
**Response.** "If you can't, the product is premature. Route to `problem-focus` and `discovery-coach`. We need a named trigger event, a named ICP, and a current-state cost denominated in dollars or hours before we keep building. The phrase 'ChatGPT for ___' is a signal that the founder has not yet done the discovery work — it borrows the legitimacy of a category without earning a wedge."

## 3. Token-Cost Denial

**Symptoms.** Founder prices flat SaaS ($X/month/seat) while inference costs scale per-token. Margins look fine at small scale; collapse as power users emerge. CFO/operator can't produce a per-user gross margin number.
**Why it fires.** Founders import SaaS pricing mental models from 2015 — flat seat fees, 80% gross margins — and apply them to a COGS structure that behaves nothing like software.
**Detection question.** What's your gross margin per active user this month? What was it 6 months ago?
**Response.** "If margin is flat or declining as cohorts mature, you have model-economics that destroy you at scale. Switch to hybrid (platform fee + meter), credit packs, or outcome-based pricing. See `pricing-frameworks.md`. The instinct to 'price like SaaS' is the trap."

## 4. Building Infrastructure the Foundation Labs Will Ship

**Symptoms.** Pitches like "AI eval platform," "vector database," "agent orchestration framework," "prompt management tool." Founder is building infra that OpenAI, Anthropic, or Google can ship as a feature in any release.
**Why it fires.** Technical founders build what they wish existed for themselves. Sometimes that's a real market. Sometimes it's a feature an incumbent lab releases for free at the next dev day and your TAM evaporates overnight.
**Detection question.** What's the 5-year scenario where you survive a foundation lab shipping this natively?
**Response.** "If you can't answer, kill it. Anthropic/OpenAI/Google ship infrastructure at marginal cost or zero. Survival requires going vertical (a specific regulated industry the lab won't enter) or going up-stack (a full workflow product, not a primitive). Sequoia's *AI in 2026* essay is explicit: the application layer captures the value; pure infra below the labs is a melting ice cube."

## 5. Model-Market-Fit Mistaken for Product-Market-Fit

**Symptoms.** Curiosity sign-ups, viral HN post, $1M ARR in 90 days, W4 retention under 20%. Founder declares PMF based on top-of-funnel and revenue velocity.
**Why it fires.** AI products spike on novelty. People pay once to try; the cohort churns out the back. The founder sees the spike, not the leak.
**Detection question.** What's your D28 retention on the cohort that signed up 60+ days ago?
**Response.** "If under 30% (B2B) or under 15% (consumer), you have model-market-fit (people want to try AI) — not product-market-fit (people keep using *your* product). The ARR is real but untrustworthy. Growth Unhinged calls this the AI churn wave; PitchBook has flagged the resulting ARR figures as a category signal. Wait for retention before raising on the spike."

## 6. Vibe-Coding Regulated / PII / Auth Surfaces

**Symptoms.** Founder ships a Lovable/Bolt/v0 MVP directly to production. The MVP handles auth tokens, payments, PII, or operates in a regulated industry (health, legal, financial services). No code review, no audit trail, no security model.
**Why it fires.** Vibe-code tools prototype 1000x faster than 2020. Founders forget that production hardening is 10x slower under vibe-code foundations because the generated code carries latent design flaws and privilege-escalation paths that surface only under adversarial load.
**Detection question.** Does your MVP touch auth tokens, payments, PII, or a regulated industry?
**Response.** "Yes = STOP. Craft-code only (Cursor + Claude Code with human review on every diff). Studies: Stack Overflow on AI-generated code reports 322% more privilege-escalation paths; MIT Sloan reports 153% more design flaws; maintenance cost roughly 4x by year two. Pay the production-hardening cost once with a clean foundation, not three times with a vibe-coded one. Karpathy's original framing ('vibe coding') was explicitly throwaway-prototype usage."

## 7. Cold-Email Blasting Post-February 2024

**Symptoms.** Founder is sending thousands of cold emails from the primary corporate domain. No SPF/DKIM/DMARC alignment, no IP/domain warmup, no one-click unsubscribe, no list hygiene. Reply rates collapse, then the primary domain reputation collapses with them.
**Why it fires.** 2019–2023 cold-email playbooks still circulate in founder forums. Founders don't know about the February 2024 Gmail/Yahoo bulk-sender rules or the November 2025 enforcement tightening. They burn the company's primary domain before they realize the rules changed.
**Detection question.** Is your sending domain authenticated (SPF + DKIM + DMARC, all aligned)? Are you sending from secondary domains, not the primary?
**Response.** "If no — stop sending today. Read the `outreach-engine` deliverability section. Burn 2–6 weeks on a proper warmup before resuming. Production stack: Smartlead or Instantly for sending, Apollo for sourcing, Clay for enrichment. Cap at 30–50 emails per mailbox per day. Proofpoint's coverage of the rules is the canonical reference."

## 8. Synthetic-User "Validation"

**Symptoms.** Founder runs Userology in synthetic mode, Synthetic Users, Uxia, or similar to "interview" personas instead of humans. Gets glowing validation in fluent prose. Pitches the synthetic transcripts as discovery evidence.
**Why it fires.** Synthetic users are trained on blog posts and marketing copy. They produce caricatures of personas, not lived reality. They tell the founder the idea is great, instantly, with no friction — which is exactly the failure mode `false-signal-detection.md` warns about, amplified by a model.
**Detection question.** How many of your "interviews" this week were with real humans inside the ICP?
**Response.** "Synthetic users for problem validation is a self-referential lie — the model is hallucinating a customer who agrees with the prompt. If you must use AI in research, use AI-moderated *real* interviews (Outset, real-mode Userology). 20 real users beats 2000 synthetic. Userology's own blog post on synthetic-user risk and NN/Group's review of synthetic-user pitfalls both say the same thing."

## The vibe-vs-craft decision gate

Lifted from the `ai-mvp-stack-selection` skill. The gate is binary; the cost of misapplying it is asymmetric.

**Vibe-code is OK for:** throwaway prototypes, internal-only tools, marketing landing pages, Fake Doors, demos that will be rebuilt or deleted within 30 days. The artifact is meant to be cheap and disposable; that's the entire point.

**Craft-code only for:** anything touching auth, payments, PII, enterprise SLAs, regulated industries, or anything that will outlive its first paying cohort. The artifact will be load-bearing; treat it that way from day one.

**The 1000x / 10x rule.** Vibe-code prototypes ship roughly 1000x faster than 2020 equivalents. Production hardening of vibe-coded foundations is roughly 10x slower than starting clean — because you are paying interest on every latent design flaw and privilege-escalation path the generator inserted. The arithmetic of when to vibe and when to craft is not a preference — it's a function of whether the artifact is throwaway or load-bearing. A founder who vibe-codes a production payments flow has not saved time; they have borrowed it at a usurious rate from their future self.

## AI-stack selection summary

Brief version. Full matrix in the `ai-mvp-stack-selection` skill.

| Use case | Stack |
|---|---|
| Landing / UI MVP | Lovable, Carrd, Framer |
| Internal-tool prototype | Replit Agent, Lovable |
| Consumer mobile MVP | Cursor + Expo (app) + Lovable (landing) |
| B2B SaaS MVP | Cursor + Claude Code, Next.js, Supabase |
| Regulated industry | Cursor + Claude Code with audit trail |
| AI agent product | Cursor + Claude Code |

## Early warning signs (the smell test)

Before the formal trap scan, watch for these tells in founder language. None is proof; each is a prompt to dig.

- "We're the AI for [profession]" — likely Trap 2. Demand the workflow.
- "Our gross margin will improve with scale" — likely Trap 3. Demand the cohort-level number, not the company-level number.
- "OpenAI won't build this because [reason X]" — likely Trap 1 or 4. The reason X is usually wrong; foundation labs have no constraints you can rely on.
- "We hit $1M ARR in 90 days" — likely Trap 5 until proven otherwise. Ask for D28 / W4 retention before celebrating.
- "We built the MVP in a weekend" — neutral or positive in throwaway contexts; alarming if the MVP is in production with payments or PII (Trap 6).
- "We validated with [synthetic-user tool]" — Trap 8. Discount to zero.
- "Our cold-email open rate is high" — ask which domain is sending (Trap 7). Open rates from a burning domain are vanity until the bounce wave hits.

## Cross-reference to tar pits and false signals

Anti-patterns in this file describe *what the founder built* and *how they validated it*. `tar-pit-detection.md` describes the *category structure* that makes some ideas dead-on-arrival regardless of execution. `false-signal-detection.md` describes the *epistemic errors* a founder makes when reading their own evidence. A single bad pitch can hit all three layers — for example, "ChatGPT for local event discovery, validated with synthetic users, growing fast on launch-day press" hits Trap 2 + Trap 5 + Trap 8 here, the local-event-discovery tar pit, and the launch-day-spike false signal at once. Run all three diagnostics; don't stop at the first hit.

## How to use this reference

When a founder describes an AI product, run the eight-trap scan over the pitch — not just the new claim. AI-era founders chain false signals: a wrapper pitch (Trap 1) gets validated by synthetic users (Trap 8), then priced flat (Trap 3), then launched into a curiosity spike that gets misread as PMF (Trap 5). Each new trap compounds the prior misreading. Name them all. Strip the narrative back to behavioral evidence — what cohorts did, what they paid, what they returned to do, what they signed.

If a founder argues "this trap doesn't apply to me," demand the specific behavioral artifact that would make it not apply. Trap 5 doesn't apply if you can show a D28 retention number above the threshold. Trap 6 doesn't apply if you can show a code-review trail. Trap 8 doesn't apply if your interview log has real names and real timestamps. The pattern is rebuttable, but only with evidence — not assertion.

## Where this is used

Loaded by: `ai-mvp-stack-selection`, `idea-pressure-test`, `mvp-architect`, `signal-audit`, `pricing-model`, `outreach-engine`. Each of those skills cites the relevant trap by number when it fires. `signal-audit` runs the trap scan alongside the seven false-signal patterns from `false-signal-detection.md` — together they form the full AI-era epistemic audit.

## Sources

- Andrew Chen, *Revenge of the GPT Wrappers: Defensibility* — https://andrewchen.substack.com/p/revenge-of-the-gpt-wrappers-defensibility
- Sequoia, *AI in 2026: The Tale of Two AIs* — https://sequoiacap.com/article/ai-in-2026-the-tale-of-two-ais/
- TechCrunch, *How AI startups should be thinking about product-market fit* — https://techcrunch.com/2025/11/11/how-ai-startups-should-be-thinking-about-product-market-fit/
- Stack Overflow, *AI can 10x developers in creating tech debt* — https://stackoverflow.blog/2026/01/23/ai-can-10x-developers-in-creating-tech-debt/
- MIT Sloan Review, *The hidden costs of coding with generative AI* — https://sloanreview.mit.edu/article/the-hidden-costs-of-coding-with-generative-ai/
- Proofpoint, *The clock is ticking on stricter email authentication enforcements* — https://www.proofpoint.com/us/blog/email-and-cloud-threats/clock-ticking-stricter-email-authentication-enforcements-google-start
- Userology, *Synthetic users vs. real humans: AI research risk* — https://www.userology.co/blogs/synthetic-users-vs-real-humans-ai-research-risk
- Karpathy on vibe coding — https://x.com/karpathy/status/1886192184808149383
- Growth Unhinged, *The AI churn wave* — https://www.growthunhinged.com/p/the-ai-churn-wave
