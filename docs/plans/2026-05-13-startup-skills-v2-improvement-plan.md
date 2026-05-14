# Startup Skills v2.0 — Comprehensive Improvement Plan

**Date:** 2026-05-13
**Author:** Synthesis from internal audit + 10 parallel external-research agents
**Target:** Take a strong v0.4 system (median skill score 27/30, exemplary reference library, mean reference score 4.82/5) and turn it into the best-in-class founder-advisor system on Claude Code.

**Scope:** Skill-engineering upgrades, methodology refresh for 2026, six new skills, ten new references, architectural improvements (state schema v2, subagent forking, hooks), eval harness, and a launch plan.

---

## Executive Summary

The audit verdict is clear: **`startup-skills` is already a strong system.** The skills are well-scoped, references are dense and well-attributed, and the system genuinely does what it claims. This is a sharpening plan, not a rewrite.

The four meaningful gaps to close:

1. **Skill engineering** — descriptions don't yet exploit Anthropic's TRIGGER/SKIP block convention, body text mixes content with workflow, hand-offs are advisory rather than directive, and there is no eval harness. Fix: rewrite every description in the `claude-api` skill style, add HARD-GATE blocks and red-flag tables (superpowers patterns), ship `evals.json` per skill.
2. **2026 methodology** — the canon is mostly 2010-2020 (Mom Test, YC pre-Tan, Sean Ellis, Vohra). Missing: Teresa Torres (continuous discovery), Bob Moesta (Switch interview / Four Forces), April Dunford (positioning), Brian Balfour (Four Fits), Annie Duke (kill criteria + monkeys/pedestals), Madhavan Ramanujam (WTP-before-build), AI-era cohort dynamics (Lovable/Cursor stack, AI Overviews SEO, deliverability collapse, model-market-fit failure mode).
3. **Coverage gaps** — no continuous-discovery skill (post-validation cadence), no cofounder-conflict skill, no positioning/narrative skill, no AI-stack-selection skill, no founder-resilience reference, no retention-metrics reference. The system stops too cleanly at PMF.
4. **Architectural** — `STARTUP-STATE.md` schema lacks AI-economics fields, retention cohort fields, decision-journal fields, and noise/calibration fields. Forward-reference language (`v0.2/v0.4 if available`) is stale (everything ships). Skills should fork-to-subagent on heavy research to preserve main-context budget.

Headline numbers:

| Dimension | Today | After v2 |
|---|---|---|
| Skills | 16 | 22 |
| References | 23 | 33 |
| Skills with TRIGGER/SKIP blocks | 0 | 22 |
| Skills with HARD-GATE | 0 | ~10 (decision-gate skills) |
| Skills with `evals.json` | 0 | 22 |
| Decision-handoff specificity | Advisory ("recommend X") | Directive ("invoke EXACTLY X; forbidden: Y, Z") |
| AI-era currency | Pre-AI-stack era | 2026 canon throughout |
| State schema fields | ~25 | ~40 (AI economics + retention cohorts + decision journal) |

---

## Part 1 — Audit Findings (Per-Skill, Per-Reference)

### 1.1 Per-skill scores

| Skill | Trigger | Struct | Hand-off | Prompt | Refusal | Refs | /30 | Priority |
|-------|---------|--------|----------|--------|---------|------|-----|----------|
| orientation | 5 | 5 | 5 | 4 | 3 | 4 | 26 | M (refusal gate, route preview) |
| founder-context | 4 | 4 | 5 | 5 | 4 | 4 | 26 | M (trigger tighten, mandatory case-study match) |
| idea-genesis | 5 | 5 | 4 | 5 | 5 | 5 | 29 | L (paralysis branch, template) |
| idea-pressure-test | 4 | 5 | 5 | 5 | 5 | 5 | 29 | L (rubric weights, mandatory analogue) |
| market-intel | 4 | 5 | 4 | 5 | 5 | 5 | 28 | M (gate on direct invocation, quantify "concentrated") |
| cofounder-fit | 4 | 5 | 4 | 5 | 5 | 4 | 27 | M (shipping definition, return-route specificity) |
| problem-focus | 4 | 5 | 5 | 5 | 4 | 5 | 28 | M (bad/good ICP examples, quantify "concentrated") |
| discovery-coach | 5 | 5 | 4 | 5 | 5 | 5 | 29 | L (mode gate, script structure) |
| signal-audit | 4 | 4 | 3 | 4 | 5 | 3 | 23 | H (handoff specificity, refusal sharpness, kill criterion) |
| rapid-experiments | 5 | 4 | 4 | 4 | 5 | 4 | 26 | M (3 separate bias checkpoints, B2B-enterprise explanation) |
| mvp-architect | 4 | 5 | 5 | 5 | 4 | 4 | 27 | M (risk-acceptance log format, MVP inline examples) |
| pricing-model | 5 | 4 | 4 | 5 | 5 | 4 | 27 | M (market-intel fallback, freemium-as-cowardice direct call) |
| outreach-engine | 4 | 4 | 5 | 4 | 5 | 5 | 27 | M (deliverability infra, Step 9 split-out, modern stack) |
| pmf-audit | 4 | 5 | 4 | 5 | 5 | 5 | 28 | L (survey template, HXC scoring concrete) |
| pivot-decision | 5 | 5 | 5 | 5 | 5 | 5 | 30 | L (pivot generation formula explicit) |
| artifact-builder | 5 | 4 | 4 | 5 | 5 | 4 | 27 | M (routing table, thin-section summary, refusal rationale) |

**Median: 27/30. No skill is broken. The lowest score (signal-audit, 23) is the single highest-priority skill to sharpen — it is the load-bearing decision gate for the whole system.**

### 1.2 Per-reference scores

Mean: **4.82/5**. No dead weight; no reference loaded too eagerly; no broken attributions.

**Reference findings:**

- **Stale:** `tool-recommendations.md` pricing is 2023-2024 (Carrd $19/yr is now tiered, HubSpot CRM free tier increasingly throttled, Tally under-maintained by Jotform).
- **Under-segmented:** `validation-techniques.md` Fake Door weight is flat 0.4 — needs source-quality + deposit-size modifiers.
- **Under-segmented:** `sales-funnel-math.md` assumes B2B SaaS defaults — needs archetype rows for B2C, marketplace, enterprise.
- **Attribution gap:** `case-studies.md` cites "YC alumni interviews" without specific founder names in places; should link to specific source where possible.

### 1.3 Cross-cutting anti-patterns to fix everywhere

1. **Over-broad triggers without negative phrasing.** `outreach-engine` fires on "marketing" (which spans SEO/brand/PR — none of which the skill handles). `signal-audit` fires on "is this working" (almost every skill could fire on this). Fix: add `SKIP:` blocks to every description.
2. **Vague hand-offs.** "Recommend next skill" without naming forbidden alternatives. Superpowers shows the cure: "invoke EXACTLY `X`. Do NOT invoke `Y`, `Z`."
3. **Forward-reference debt.** "Ships in v0.2/v0.4" language is now stale — everything ships. Strip all `v0.X if available` phrasing.
4. **Missing state-document guards.** Several skills say "read STARTUP-STATE.md" without checking existence; if a skill fires before `orientation`, it crashes. Add live state injection (` !`cat STARTUP-STATE.md` `) to every skill body.
5. **Artifact-offer optionality.** Many skills offer artifacts "on request" but don't suggest them. The artifact IS often the right next ask.
6. **`market-intel` re-run logic missing.** Multiple skills call `market-intel`; no skill checks whether it ran recently on the same topic. State doc needs `last_market_intel_date` per topic.
7. **Bias-sentinel pass inconsistency.** Every skill names `bias-sentinel.md` in "Required Reading," but `orientation`, `cofounder-fit`, and `artifact-builder` don't actually run a pass. Add minimal bias-sentinel hook to every skill.
8. **Soft refusals.** "I accept the risk and we'll continue" without explicit log format. `mvp-architect` allows pre-validation builds with risk acknowledgment but doesn't enforce log format. Make the log entry mandatory and structured.

---

## Part 2 — Skill Engineering Upgrades

The single highest-leverage change in this plan. Eight concrete patterns to copy from Anthropic's official skills and `obra/superpowers`.

### 2.1 Rewrite every description in TRIGGER/SKIP block format

Current `discovery-coach` description (114 chars after "The most important skill"):

> "The most important skill. Use before AND after every customer conversation. Fires on 'I'm going to interview users,' 'I just got off a call,' 'I need an interview script,' or 'what should I learn from these conversations.' PREPARE mode generates Mom-Test-aligned scripts. DEBRIEF mode classifies every statement by evidence weight, surfaces false signals, and refines the hypothesis."

Proposed rewrite, mirroring Anthropic's `claude-api` skill format:

```yaml
description: |
  Customer-interview prep (script generation) and debrief (evidence classification + false-signal detection). PREPARE before every interview; DEBRIEF after every one. Mom-Test-aligned; refuses to count compliments as data.

  TRIGGER when: user says "interview", "talk to users", "just got off a call", "I talked to N people", "need an interview script", "what should I learn from these conversations"; user is about to schedule customer conversations; user reports a finished customer call; `STARTUP-STATE.md` Evidence Log has new entries since last `discovery-coach` run.

  SKIP: user has no hypothesis yet (route to `problem-focus`); user wants to fundraise (route to `pmf-audit`); user is asking how to phrase a single question rather than running PREPARE/DEBRIEF.
```

Why this works: (1) the `TRIGGER when:` and `SKIP:` blocks are inside the YAML description, so Claude reads them when routing; (2) trigger phrases are explicit; (3) state-document signals are included as triggers; (4) skip conditions name the routing alternatives. This format matches what `obra/superpowers` and `anthropics/skills` use and produces materially better trigger reliability per the skill-engineering research.

**Action: rewrite all 22 skill descriptions in this format. Estimated effort: 1-2 hours.**

### 2.2 Add HARD-GATE blocks to decision-gate skills

`obra/superpowers` opens decision-gate skills with literal HARD-GATE language. Adopt for: `signal-audit` (the freeze gate), `mvp-architect` (the build gate), `outreach-engine` (the paid-acquisition gate), `pmf-audit` (the scaling gate), `pricing-model` (the commit gate), `pivot-decision` (the continue/pivot gate).

Example for `signal-audit`:

```markdown
## HARD-GATE — do not proceed past this if:

- [ ] User is asking about scaling, hiring, paid acquisition, or fundraising, AND
- [ ] PMF Running Score in `STARTUP-STATE.md` is below "converging" (≥5 entries at 0.8+, mean weight ≥0.5), AND
- [ ] No Sean Ellis survey has been run, OR survey is below 40% Very Disappointed

If all three are true: REFUSE the action. State explicitly: "Evidence does not support this. To unlock this decision, you need [specific evidence]. Fastest path: [specific skill]. Logging this refusal to Session Log."

Do NOT soften. Do NOT offer "but if you really want to..." caveats. The gate is the load-bearing feature of this skill.
```

Why this works: superpowers data shows HARD-GATE blocks are why the system can "work autonomously for hours without deviating." For our system, the gates are the *whole point* — `signal-audit` exists to refuse decisions the evidence doesn't support.

### 2.3 Red-flag tables on every discipline skill

Pattern from `superpowers:dispatching-parallel-agents`:

| Founder thought | Reality |
|---|---|
| "But they were so enthusiastic" | Enthusiasm without behavioral commitment is weight 0.0 |
| "We're different from those failed startups" | Inside view. Force outside view first. |
| "Let me just ship and see" | Pre-validation build = bet you guessed the hypothesis right on first try. Data says you can't. |
| "I'll figure out pricing later" | Pricing changes MVP shape and funnel math. Refuse to defer. |

Apply per skill: `signal-audit` red-flags around false signals, `mvp-architect` red-flags around feature creep, `pivot-decision` red-flags around sunk cost reasoning, `pricing-model` red-flags around freemium-as-cowardice, `discovery-coach` red-flags around politeness-as-data.

### 2.4 Live state injection via dynamic context

Skills currently say "read `STARTUP-STATE.md` at activation," trusting Claude to do it. Better: inject the state at the top of every skill body via Anthropic's `` !`command` `` block:

````markdown
## Current state (live)
```!
cat .claude/startup-state.md 2>/dev/null || echo "(no STARTUP-STATE.md — route to orientation first)"
```
````

Anthropic's skill spec runs the `!` block before Claude sees the skill body, replacing the placeholder with the command output. This guarantees the skill sees current state — no reliance on Claude remembering to Read it.

**Bonus effect:** the skill self-routes. If the cat returns the no-state echo, Claude sees that and immediately hands off to `orientation`.

### 2.5 `paths` frontmatter for stage-locked skills

Several skills only make sense at certain points in the project. Use Anthropic's `paths` glob to gate them:

```yaml
paths:
  - ".claude/startup-state.md"
  - "validation/**"
  - "experiments/**"
```

A skill with these paths won't appear in the skill listing when the user is working in `src/` or `node_modules/`. Eliminates over-firing. The cost of a skill never appearing is much lower than the cost of a skill firing wrong.

### 2.6 Eval harness per skill

Ship `evals.json` alongside each `SKILL.md`:

```json
{
  "skill_name": "idea-pressure-test",
  "trigger_evals": [
    {"query": "I want to build a Notion clone for therapists", "should_trigger": true},
    {"query": "score my idea", "should_trigger": true},
    {"query": "is selling shoelaces a good business", "should_trigger": true},
    {"query": "what's the difference between SaaS and PaaS", "should_trigger": false},
    {"query": "I have no idea what to build", "should_trigger": false, "should_route_to": "idea-genesis"},
    {"query": "I already have customers but they're churning", "should_trigger": false, "should_route_to": "signal-audit"}
  ],
  "process_evals": [
    {
      "query": "I want to build a CRM for dog walkers",
      "must_include": ["steel-man", "FMF", "Dalton", "tar pit check"],
      "must_not_include": ["This is a great idea", "I think this could work"]
    }
  ],
  "refusal_evals": [
    {
      "query": "I want to use AI to do something cool, any ideas?",
      "must_refuse": true,
      "must_include": ["solution looking for a problem", "SISP"]
    }
  ]
}
```

Then a script (`scripts/run_evals.py`) runs each query against Claude with the plugin installed, scores trigger / process / refusal, and prints a per-skill report. Run before every release. Pattern from `anthropics/skills/skill-creator`.

**This is the v1.0 commitment in the spec:** "Add a benchmark/evaluation harness: ~30 test prompts per skill, run through Claude with the skill loaded, scored against a rubric. Run before each release."

### 2.7 Numbered process steps with verification gates

Current skills use bullet sub-steps inside numbered top-level steps. Convert to flat numbered steps, each with a verification command after. Pattern from `superpowers:writing-plans`:

```markdown
## Process

1. Read `.claude/startup-state.md`. Verify: state file exists and has a Founder Profile.
2. If the founder mentions "AI" + "what should I build" → refuse with SISP redirect. Verify: refusal message is in conversation; do NOT continue to step 3.
3. Ask Q1 ("What's your job right now?"). Wait for answer. Verify: user has responded with a sentence, not a one-word answer.
...
```

The verification line after each step is what produces "work autonomously without deviating." It's also what makes the skill auditable — a reviewer can read the conversation and check each verification.

### 2.8 Specific terminal hand-offs (named-skill, named-forbidden)

Superpowers pattern: "Invoke EXACTLY `writing-plans`. Do NOT invoke `frontend-design`, `mcp-builder`, or any other implementation skill."

Apply to every skill end:

```markdown
## Next step

If the founder's evidence is converging:
- Invoke EXACTLY: `mvp-architect`
- Do NOT invoke: `outreach-engine` (premature without scoped MVP), `artifact-builder` (artifacts before MVP are speculative)

If evidence is mixed:
- Invoke EXACTLY: `rapid-experiments`
- Do NOT invoke: `mvp-architect`, `outreach-engine`

If evidence is pre-signal and the founder has been at this for 3+ months:
- Invoke EXACTLY: `pivot-decision`
- Do NOT invoke: `mvp-architect`, `outreach-engine`, `pmf-audit`
```

### 2.9 Subagent forking for heavy research

`market-intel` runs 5-10 parallel searches + 2-3 WebFetches. Each WebFetch returns substantial text. This blows out the main session's context window over a 5-skill journey. Fix: run `market-intel` in a forked subagent.

Frontmatter addition:

```yaml
context: fork
agent: Explore
allowed-tools: WebSearch WebFetch Read Glob Grep
```

The forked subagent does the heavy lifting in isolated context, returns a structured brief (the Pain/Vocabulary/Who's-Building/etc. fields), and the main conversation only sees the summary. Same pattern for `founder-context` parallel research and `pmf-audit` survey design.

### 2.10 Anti-sycophancy circuit-breaker (built into `bias-sentinel.md`)

Stanford 2026 research: LLMs endorse user positions ~49% more often than humans do. RLHF rewards agreement. The system's whole thesis is "structural override of bias" — sycophancy is the bias most likely to undo it.

Add to `bias-sentinel.md`:

```markdown
## Sycophancy circuit-breaker (run every N=5 turns)

After every 5 user turns, run this check silently:
- Have I disagreed with the founder substantively in the last 5 turns?
- Have I pushed back on at least one claim with a specific counter?
- If I praised the founder, was the praise quantified (with evidence) or just affirming?

If all answers are "no, no, just affirming" → force a contrarian pass on the most recent decision. State: "Pausing for a contrarian pass — I've been agreeing too much. Here's the strongest case against what we just decided: ..."

This is not optional. The system's value is friction. Sycophancy is its failure mode.
```

---

## Part 3 — Methodology Updates (the 2026 canon refresh)

### 3.1 YC canon: Tan-era, Founder Mode, Lightcone, new partners

Add to `external-resources.md` and (where applicable) to specific skill bodies:

- **Paul Graham, "Founder Mode" (Sept 2024)** [link](https://paulgraham.com/foundermode.html). Foundational essay on staying in details at scale. Cite in `cofounder-fit`, `mvp-architect`, any future scaling skill. Note: contested (Wasserman, Maan critiques) — cite as influential, not universal.
- **Garry Tan's "earnestness" + "first-principles thinkers"** — Knowledge Project Ep. 226. Add to `founder-context` evaluation framing.
- **Jared Friedman, "How to Get and Evaluate Startup Ideas" (Startup School 2024)** — the de facto 2024 successor to PG's 2012 essay. Cite in `idea-genesis` alongside the older essay.
- **Dalton & Michael 2024-2025 podcast** — "Tar Pit Ideas" framing (Lenny's, 2024), "Stop Innovating on the Wrong Things", "Co-founder mistakes". Cite in `idea-pressure-test`, `cofounder-fit`, `pivot-decision`.
- **Lightcone Podcast (Tan/Hu/Friedman/Taggar, 2024+)** — episodes on contrarian bets, AI startup ideas, enterprise AI failure rates. Add as a recurring source.
- **New partner names to surface where they own RFS topics:** Tom Blomfield (B2B metrics), Diana Hu (agent infrastructure), Aaron Epstein (business models), Pete Koomen (enterprise sales).
- **Michael Seibel's March 2025 B2B framing** — "drive significant impact" [tweet](https://x.com/mwseibel/status/1905435084318257476). Update `signal-audit` and `pmf-audit` to cite.
- **Current RFS (live)** — `https://www.ycombinator.com/rfs`. `market-intel` and `idea-genesis` should fetch the live RFS rather than relying on snapshot.
- **Update Seibel attribution** — he is now Partner Emeritus (stepped back 2024). Dalton Caldwell is Managing Director. Cite Seibel as still authoritative on YC-era 2016-2024 frameworks but note newer content is post-Seibel.
- **Update growth benchmarks** — Tan publicly cites 10-20% weekly for current AI YC cos vs. older 5-7% benchmark.
- **Update geography** — Tan's current stance is "be in SF." Reframe any `outreach-engine` remote-friendliness messaging.
- **Update moat framing** — "Speed is the only pre-PMF moat; moats are results, not starting points." (Sam Altman + Lightcone consensus.)

### 3.2 Customer discovery: Torres, Moesta, Indi Young, JTBD

Add to `discovery-coach`, `problem-focus`, and a new `continuous-discovery` skill.

- **Teresa Torres — Continuous Discovery Habits.** The biggest missing piece. Add:
  - **Opportunity Solution Tree (OST)** as a canonical output of `discovery-coach`.
  - **Weekly cadence rule:** discovery is continuous, not episodic.
  - **Product Trio:** PM + designer + engineer interview together.
  - **Story-based interviewing:** "Tell me about the last time you [did the behavior]."
  - **Interview snapshots:** one-page artifact per interview.
- **Bob Moesta — Switch interview (~47 min, 10-phase protocol).** Add to `discovery-coach` as a second mode alongside Mom Test, selected by user state:
  - **Pre-purchase / problem discovery:** Mom Test.
  - **Post-purchase / switching behavior:** Switch interview.
  - **Four Forces of Progress** (Push + Pull > Anxiety + Habit) as post-interview synthesis prompt.
- **Indi Young — Listening Deeply.** Phase-0 mode for founders with no hypothesis yet. Germinal question: "What was going through your mind as you were doing that thing you do?" Add to `idea-genesis` as the deepest form of organic-track interviewing.
- **JTBD: two schools, named.** `mvp-architect` and `idea-pressure-test` should explicitly distinguish Ulwick (Outcome-Driven Innovation, B2B-strong) from Christensen/Moesta/Klement (Jobs-as-Progress, consumer/switching-strong). Recommend which fits which archetype.
- **I-Corps 100-interview standard.** Cite as the rigorous benchmark in `signal-audit`. Mom Test's 20-conversation threshold is a floor; 100 is the bar that NSF-funded teams hit.

### 3.3 PMF measurement: Balfour Four Fits, retention curves, AI PMF collapse

Add to `pmf-audit` and `signal-audit`:

- **Brian Balfour Four Fits (Market-Product, Product-Channel, Channel-Model, Model-Market)** — PMF alone insufficient for $100M scale; when growth stalls despite "good product," misfit is almost always one of the latter three.
- **Casey Winters retention curve flattening rule** — PMF = flattened retention curve on key action at appropriate frequency + MoM growth in new-user cohorts. Add to `pmf-audit` as a leading indicator alongside Sean Ellis.
- **Andrew Chen Power User Curve (L7/L28 smile vs. frown)** — distinguishes real PMF (smile-shaped histogram) from broken PMF (frown).
- **PMF Treadmill / Collapse (Winters + Mosavat + Balfour)** — PMF is not static; expectations rise. Add an AI-substitution check: "is your core JTBD now achievable in ChatGPT/Claude in <30s? If yes, you're on the treadmill."
- **Token-cost-aware PMF (AI products)** — LTV/inference-cost ratio ≥ 3x, margin-per-active-user trend, cost-per-retained-user (not cost-per-signup).
- **Anti-PMF signals table** — narrative-as-explanation, busy-as-churn-reason, champion-dependency, lengthening cycles, intensifying pricing pushback. Add to `signal-audit`.
- **Andreessen observables operationalized** — sales-cycle-length-delta (shrinks 20-40% in 90 days), "from a friend/colleague" referral share ≥30% (50-70% strong PMF), CS perpetually behind hiring.
- **First Round Levels of PMF** [link](https://www.firstround.com/levels) — staging diagnoses with ARR/churn/NRR thresholds.

### 3.4 Pricing: Ramanujam, outcome-based AI pricing

Update `pricing-frameworks.md` and `pricing-model`:

- **Madhavan Ramanujam — Monetizing Innovation.** "WTP before you build." Reframe "charge from day one" as a corollary of "measure WTP before you build." Add the four failure modes: Feature Shocks, **Minivations** (right product, priced too low — dominant pre-PMF founder mistake), Hidden Gems, Undeads.
- **Patrick Campbell — Van Westendorp PSM (4-question)** + Conjoint Analysis. The recommended pre-build research method. N≥40 per persona for directional, N≥150 for stable.
- **AI pricing primitives:**
  - **Per-seat erosion** — 40% lower gross margins + 2.3× higher churn vs. usage/outcome (Bain).
  - **Hybrid pricing** (platform fee + meter) as the default new launch model.
  - **Outcome-based pricing:** Intercom Fin $0.99/resolution, Sierra per-outcome, Zendesk AI. Charge 10-30% of human-replaced cost.
  - **Token COGS** = 30-60% of revenue for AI products (vs. <10% traditional SaaS). The 80% gross margin rule is broken for AI.
- **Charge-from-day-one boundary conditions:**
  - **Right** for B2B with bounded users + measurable value; enterprise/mid-market; anything with non-trivial unit COGS.
  - **Wrong** for consumer (TikTok-scale funnel needed); marketplaces (liquidity precedes monetization); strong viral-coefficient products (Slack, Figma early days).
- **B2B freemium gates:** require k > 0.4 viral coefficient AND ACV < $5K AND COGS < $0.50/free-user/mo before allowing freemium in B2B.
- **Anti-discount rule:** discount scope or term length, never list price. (Each 20% discount requires 25% more volume to break even.)
- **Tier ratio rule of thumb:** 1 : 2.5 : 6 (Starter : Pro : Enterprise) approximates median B2B SaaS.

### 3.5 AI-era playbook (the biggest single update)

This deserves its own new reference (`ai-era-anti-patterns.md`) AND updates across multiple skills.

**Concrete shifts:**

- **MVP construction:**
  - Lovable for landing/UI MVPs (best polish, no SQL).
  - Bolt.new for fastest prompt-to-deploy (degrades sharply past 3-5 components).
  - Replit Agent for autonomous long-running prototypes (pricing unpredictable).
  - Cursor / Claude Code for anything shipping to paying users.
  - v0 has fallen behind.
- **Vibe-code vs. craft-code gate:** Karpathy's framing survived; ban from production for regulated (healthcare/legal/fin), B2B with SLAs, anything touching auth/payments/PII. Studies show LLM-generated code introduced 322% more privilege-escalation paths and 153% more design flaws.
- **The 1000x/10x tradeoff:** prototypes 1000x faster, production hardening 10x slower (hidden tech debt). Cite Stack Overflow + MIT Sloan studies.
- **Distribution shifts:**
  - **Cold email deliverability collapse** (Feb 2024 Gmail/Yahoo + Nov 2025 enforcement). Mandatory SPF/DKIM/DMARC, ≤0.3% spam rate, one-click unsubscribe. Custom domain + Outlook = 5.9% reply, custom domain + Gmail = 3.5%, webmail = 1.2-2.1%. Modern stack: secondary sending domains, 2-6 week warmup, Smartlead/Instantly + Apollo + Clay.
  - **LinkedIn algorithm shift (late 2025):** comment-first strategies. 30-80 word comments signal "deep engagement." Personal profiles 8× engagement vs. company pages. Connection-request-with-note is primary; InMail reserved for high-priority follow-ups. Volume Tax penalty on bulk DM senders (~100/wk hard cap).
  - **SEO under AI Overviews:** organic CTR drop 61% on queries with AIO. Comparison tables (+25.7% citations), FAQ schema, "AI-resistant" content types (original research, named POV, YouTube, Reddit presence). Reddit is #1 cited domain in ChatGPT/Gemini/Perplexity/Google AI Overviews; citation share +73% Oct 2025 → Jan 2026.
  - **Signal-based outbound** (Common Room, Clay, Apollo): hiring signals, funding signals, job-change signals, tech-stack signals. Pre-PMF: use free signals (BuiltWith, Crunchbase, LinkedIn jobs) + Clay/Apollo workflow; skip full 6sense ($50k+).
- **Defensibility re-classification:**
  - **Wrapper trap:** "If OpenAI shut down your API key and your startup also dies, you didn't build a product."
  - **Winning wrappers** stack ≥2 of: proprietary data flywheel, workflow embedding, integration ecosystem, regulated-industry trust capital.
  - **Vertical AI > horizontal AI** by ROI (Lyzr: 500% vs. 171%), retention (Sierra: 30-50% higher), accuracy (Harvey legal: 94.8%).
- **Tiny team math:**
  - Solo-founded startups: 23.7% (2019) → 36.3% (mid-2025).
  - Sequoia: leading AI startups earn >$1M revenue per employee.
  - Dario Amodei: 70-80% probability a one-person $1B company emerges in 2026.
- **AI-mediated customer discovery:** AI-moderated **real** interviews fine (Outset, Userology, Maze AI); synthetic users **never for problem validation** ("If you ask AI to act like a frustrated CFO, it gives you a caricature based on blog posts").
- **AI-era investor lens:** seed-stage median post-money $24M (Q4 2025); "completed work" decks; revenue-per-employee KPI; token-cost-per-user / gross margin questions arrive at seed.
- **8 AI-era founder mistakes to encode as a checklist:** wrapper-without-distribution, "ChatGPT for X" without wedge, token-cost denial, infrastructure when foundation labs already ship it, confusing model-market-fit with PMF, vibe-coding regulated surfaces, cold-email blasting post-Feb 2024, synthetic-user validation.

### 3.6 Behavioral economics deepening (the `bias-sentinel.md` upgrade)

Add to `bias-sentinel.md`:

- **Annie Duke — Thinking in Bets, Quit:**
  - **Kill criteria** as state + date format: "If [measurable state] is not true by [specific date], we quit."
  - **Monkeys vs. Pedestals:** test the monkey (hard problem) first; ban pedestal work until monkey is partially trained.
  - **Resulting:** judging decisions by outcomes destroys learning. Score *decision process* separately from *outcome*.
- **Phil Tetlock — Superforecasting:**
  - **Calibrated probability estimation.** Forbid "definitely," "obviously," "no doubt." Force probability ranges on every founder claim.
  - **Brier score self-tracking.**
  - **Bayesian updating:** "Prior: X%, posterior: Y%, evidence: Z" format.
- **Noise (Kahneman/Sibony/Sunstein, 2021):**
  - **Mediating Assessments Protocol (MAP):** decompose any major decision into 5-7 independent dimensions, score before discussing holistically.
  - **Independence rule:** advisors give written assessments before hearing each other.
- **Decision Journal (Shane Parrish / Farnam Street):**
  - Date, decision, expected outcome, confidence %, alternatives considered, key assumptions, review date.
  - Add to STARTUP-STATE.md schema (see Part 6).
- **Forbidden phrases (linguistic interventions):**
  - "Obviously" / "definitely" / "no question" → must replace with explicit probability.
  - "Everyone wants this" → must cite N and methodology.
  - "Just need to ship faster" → must specify falsifiable metric.
  - "Trust me" → ban entirely.
  - "We're different" → trigger forced reference-class identification.
- **Steelman-first ritual:** before any decision, proposer must give strongest version of opposite decision.

### 3.7 Aggressive consultation calibration (the `tone-and-stance.md` upgrade)

Add to `tone-and-stance.md`:

- **Critique the artifact, never the founder.** Pitch buries the ask, not "you bury the ask." (Gottman: criticism vs. contempt.)
- **Lead with observation, not evaluation.** "Your churn is 8% monthly" before "your retention is bad." (NVC.)
- **Name the load-bearing claim.** One sentence: "The thing that decides whether this works is X." (Andreessen "only thing that matters.")
- **State regime before recommendation.** "If you're pre-PMF, do A. If scaling, do B. You're pre-PMF." (Horowitz wartime/peacetime.)
- **Assign probabilities to predictions.** "I'd give this ~20% of working" beats "this won't work." (Tetlock.)
- **Front-load the negative.** "You'll probably fail; here's why you might not." (Altman.)
- **Force articulation of the non-consensus belief.** "What do you believe that your competitors don't?" (Thiel.)
- **Refuse "our case is special."** Name it when it shows up. (Rabois.)
- **Modulate delivery on emotional state; never soften the claim.** State the founder's apparent state, then deliver the truth. (Crucial Conversations.)
- **Show care via specificity, not warmth performance.** Specificity *is* the care signal for an AI advisor.
- **Don't critique on aesthetic/personal choices.** Save capital for high-cost decisions.

**Cost-of-decision gate** for `bias-sentinel.md`:

| Decision class | Audit pressure |
|---|---|
| Build / raise / quit / fire cofounder | Hardest. Refuse fuzz. |
| Market choice, pricing, GTM motion | Hard. Specifics, Thiel-style "what would have to be true?" |
| Tactics (copy, feature priority, hire #7) | Moderate. State better option, drop it. |
| Aesthetic / personal style | Soft or decline. |

### 3.8 Trusted source canon — concrete additions to `external-resources.md`

(Detailed agent report has full list with URLs. Highlights:)

**Tier 1 books to canonize:**
- April Dunford — *Obviously Awesome* (positioning)
- Andy Raskin — "Greatest Sales Deck I've Ever Seen" (strategic narrative)
- Madhavan Ramanujam — *Monetizing Innovation* (WTP-before-build)
- Annie Duke — *Thinking in Bets*, *Quit* (decision quality, kill criteria)
- Phil Tetlock — *Superforecasting* (calibration)
- Kahneman/Sibony/Sunstein — *Noise* (decision hygiene)
- Brian Balfour — Four Fits essays (post-PMF growth)
- Andrew Chen — *Cold Start Problem* (atomic networks, marketplaces)
- Casey Winters — Casey Accidental (retention, growth loops)
- Bob Moesta — *Demand-Side Sales 101* (Four Forces, Switch interview)
- Alan Klement — *When Coffee and Kale Compete* (JTBD-as-progress)
- Tony Ulwick — *Jobs to Be Done* (ODI, outcome scoring)
- Teresa Torres — *Continuous Discovery Habits* (OST)

**Tier 2 canon (post-PMF, boundary-case):**
- Reid Hoffman — *Blitzscaling* (post-PMF only; cite as boundary marker)
- Geoffrey Moore — *Crossing the Chasm* (already cited; mark post-PMF)
- Sangeet Choudary et al. — *Platform Revolution* (marketplaces)
- David Skok — For Entrepreneurs (SaaS unit economics)
- Bessemer State of the Cloud (annual benchmarks)
- NFX Network Effects Bible / Manual (marketplace/network products)
- Ben Thompson — Aggregation Theory (Stratechery 2015)

**Reject / deprioritize:** *Good to Great*, *Built to Last*, *Innovator's Dilemma* (post-PMF), *The Startup Way* (enterprise), *Shoe Dog* (memoir not framework), early-2010s startup canon (superseded).

---

## Part 4 — New Skills

Six new skills bring the system from 16 to 22.

### 4.1 `continuous-discovery` (Teresa Torres methodology)

**Purpose:** Maintain customer signal *after* validation. Currently the system goes hypothesis → interviews → MVP → PMF → done. Real product work requires Torres-style weekly discovery forever.

**Triggers:** post-MVP launch; PMF stage = early-signal or higher; user says "what next features should I build", "what should be on the roadmap", "weekly customer cadence", "should we keep doing customer interviews"; calendar trigger (every 2 weeks).

**Process:**
1. Read state; confirm post-validation (MVP shipped OR PMF stage ≥ early-signal).
2. Build/update the **Opportunity Solution Tree** (outcome at top, opportunities mid, solutions + assumption tests at leaves).
3. Schedule weekly touchpoint: 1 interview per week with HXC-cohort customer.
4. Per interview, surface 1-3 new opportunities. Branch them onto the OST.
5. **Assumption mapping** on new solutions: desirability, viability, feasibility, usability, ethical.
6. Generate 1-2 cheap assumption tests per week (≤1-day experiment cost).
7. Update STARTUP-STATE.md OST section.

**Hand-off:** `rapid-experiments` for the cheapest assumption test; `mvp-architect` if a new opportunity is large enough to be a v2.

### 4.2 `ai-mvp-stack-selection`

**Purpose:** Match the founder's MVP to the right AI-stack choice. Most founders choose Lovable when they should choose Cursor, or Bolt when they should choose Replit Agent.

**Triggers:** user is starting an MVP; says "should I use Lovable / Bolt / Cursor / Replit / v0"; technical ability < "can build" + non-trivial product; vibe-coding question.

**Process:**
1. Read state; pull archetype, hypothesis, technical ability, regulated-industry flag.
2. **Decision matrix:**

| Build target | Recommended stack | Vibe-code OK? |
|---|---|---|
| Landing page / Fake Door | Carrd, Framer, Lovable | Yes |
| Internal-tool prototype (non-shipping) | Replit Agent, Lovable | Yes |
| Consumer mobile MVP | Cursor + Expo, Lovable for landing | Partial — review every shipped path |
| B2B SaaS MVP (PII, auth, payments) | Cursor + Claude Code, Next.js, Supabase | No — craft-code only |
| Regulated (health, legal, fin) | Cursor + Claude Code, audit trail mandatory | NO. Period. |
| AI agent product | Cursor + Claude Code; pure AI stack ≥ AI Engineer infra | No |

3. **Vibe-vs-craft gate.** Decision rule: regulated OR payments OR auth OR PII OR enterprise SLA = craft-code. Otherwise vibe is acceptable for prototype phase only.
4. Cite the 1000x/10x tradeoff: prototypes 1000x faster, production hardening 10x slower under vibe-code.
5. Surface specific token-cost / pricing predictability warnings (Replit Agent burns $600+ unpredictably).

**Hand-off:** `mvp-architect` once stack is chosen; `outreach-engine` in parallel to recruit hair-on-fire customers.

### 4.3 `distribution-2026` (replacing the dated outreach assumptions)

This could be an upgrade to `outreach-engine` rather than a new skill. **Recommendation: keep `outreach-engine` but split out a new `distribution-2026` reference + retitle Step 9 (Continuous Launch) into its own section.**

Adds:
- Cold-email-deliverability-2025 module: SPF/DKIM/DMARC, secondary domains, 2-6 week warmup, modern stack (Smartlead/Instantly/Apollo/Clay).
- AI-Overviews SEO module: comparison tables, FAQ schema, first-hand experience, named POV.
- LinkedIn comment-first module: 30-80 word comments, 0-3 hashtags, doc carousel format.
- Reddit/YouTube as primary AI-citation distribution channels.
- Signal-based outbound (Common Room / Clay + free signals stack).

### 4.4 `positioning-narrative` (April Dunford + Andy Raskin)

**Purpose:** Fix the canonical pre-fundraising gap. Founders go from problem-focus → MVP → outreach without ever doing positioning, and then build pitch decks that fail.

**Triggers:** user is about to write a pitch deck / website / cold email; user says "how do I describe what we do", "what's our positioning", "elevator pitch", "messaging", "narrative"; PMF stage ≥ early-signal AND no committed positioning in state.

**Process:**
1. Read state; pull ICP, hypothesis, competitive landscape, PMF score.
2. **Dunford 10-step positioning:**
   1. Understand competitive alternatives (not just direct competitors).
   2. Isolate unique attributes — what only you have.
   3. Map attributes to value.
   4. Identify best-fit customers.
   5. Choose market category that makes you obvious.
   6. Layer on trends (only when honest).
   7. Test positioning vs. alternatives.
3. **Raskin strategic narrative:**
   - Old game (why the world is changing).
   - New game (what now wins).
   - Promised land (what your customer becomes).
   - Obstacles (what's in the way).
   - Magic gifts (your unique advantages).
4. Commit positioning to STARTUP-STATE.md Positioning section (new).
5. Produce on request: positioning brief, deck narrative, website hero copy.

**Hand-off:** `artifact-builder` for the deck / website. `outreach-engine` if cold email copy is needed.

### 4.5 `cofounder-decision` (cofounder conflict)

**Purpose:** Currently `cofounder-fit` is for diagnosing gaps and onboarding cofounders. There is no skill for the much harder situation: cofounders disagreeing on direction, one wanting to quit, equity disputes mid-flight, breakup decisions.

**Triggers:** user says "cofounder disagrees", "cofounder wants to quit", "cofounder fight", "should I fire my cofounder", "vesting cliff", "cofounder breakup"; user is solo asking how to convince the other person of something.

**Process:**
1. Read state; pull Team section, recent Session Log for context.
2. **Separate value-function check.** Each founder's real constraint (financial runway, equity, lived expertise, exit value). Surface mismatches.
3. **Factcheck the disagreement.** Is this about data or preference? If data — point at evidence in state. If preference — name it as preference and ask what would change minds.
4. **Per-founder opportunity-cost recalc.** What does each founder give up by continuing/quitting?
5. **Mediation toward three choices:**
   - Continue together with explicit role realignment.
   - One founder exits cleanly (vesting + buyback per founder agreement).
   - Pivot both agree on (route to `pivot-decision`).
6. **Refuse to help one founder convince the other without both present.** Strict refusal.
7. Update Team section.

**Hand-off:** `pivot-decision` if the disagreement is about direction; `signal-audit` if it's about whether evidence supports continuing.

### 4.6 `founder-resilience` (decision quality under stress)

**Purpose:** Founders make worse decisions when depleted. Most startup go/no-go decisions happen when the founder is exhausted. This skill is a pre-decision hygiene check.

**Triggers:** user is about to make a major decision (build / raise / quit / hire / fire / pivot) AND signals of stress in conversation; user says "I'm exhausted", "burnt out", "haven't slept", "this is killing me"; PMF stage = pre-signal for 3+ months.

**Process:**
1. Read state; pull recent Session Log for cadence + stress signals.
2. **Three hygiene questions:**
   - Are you making this decision under physiological stress? (Sleep, illness, family, financial.) If yes — recommend deferring by 24 hours.
   - Is this decision reversible in 30 days? If no — escalate audit pressure (route to `pivot-decision` if pivot, `signal-audit` if build/scale).
   - Is your cofounder seeing the same data the same way? If no — route to `cofounder-decision`.
3. **Sustainable-pace check.** Can you maintain current burn (mental + financial) for 18 months? If no, name the constraint.
4. **Loneliness audit.** By month 6-12, you're the only person who knows what's at stake. Who else are you actually talking to (not your team, not your family)?
5. **You are not your company.** Brief reminder framing.

**Hand-off:** the deferred decision usually returns to the originating skill (`mvp-architect`, `pivot-decision`, `pmf-audit`, etc.). This skill is a circuit-breaker, not a replacement.

---

## Part 5 — New References (10 additions)

### 5.1 `retention-metrics.md` (CRITICAL gap)

**Content:**
- D1 / D7 / D14 / D28 retention benchmarks by archetype (SaaS, consumer, devtools, marketplace, B2C subscription).
- Cohort retention curves: flat curve = PMF; decay = no PMF.
- Activation analysis: of users who came back on day 7, what did they do on day 1 that churned users didn't?
- L7/L28 smile-vs-frown curve (Andrew Chen).
- Anti-PMF retention signals (champion-dependency, novelty curl, polite-churn explanations).
- Case study: Magic (launch spike + day-4 retention <5% killed the company).

**Loaded by:** `pmf-audit`, `signal-audit`, `pivot-decision`, new `continuous-discovery`.

### 5.2 `growth-loops.md`

**Content:**
- Viral coefficient (k) — k > 0.4 enables freemium, k > 1 enables exponential.
- NRR (net revenue retention) — >100% = expansion revenue.
- CAC payback period — <12 months sustainable, >24 months money pit.
- Growth vs. efficiency — high growth + high CAC = burning to show growth, not building a company.
- Bessemer benchmarks (Rule of X, Efficiency Score, NRR bands 100/110/120).
- David Skok unit economics (LTV:CAC ≥ 3, Magic Number > 0.75).
- The Four Fits (Balfour).

**Loaded by:** `outreach-engine`, `pmf-audit`, `pricing-model`.

### 5.3 `continuous-discovery-patterns.md`

**Content:**
- Torres weekly cadence — 1 interview/week forever.
- Opportunity Solution Tree visual structure.
- Assumption mapping (5 categories: desirability, viability, feasibility, usability, ethical).
- Feedback triage: independence check ("have you heard this from 20+ ICP users independently or just this one?").
- AARRR pirate metrics — which apply pre-PMF vs. post.
- Build-measure-learn velocity (2-3 experiments/week pre-PMF target).

**Loaded by:** new `continuous-discovery`, `discovery-coach`, `rapid-experiments`, `pmf-audit`.

### 5.4 `distribution-by-archetype.md`

**Content:**
- Developer tools: free tier + self-serve + word-of-mouth (with exceptions: Stripe/Twilio = founder sales for 12-18mo first).
- B2B SMB SaaS: founder-led sales for first 100; no SDR pre-PMF.
- Consumer: virality (internal incentive) or paid acquisition at scale; Airbnb-style manual seeding for marketplaces.
- Hardware/deep-tech: pre-orders + founder-led B2B.
- Marketplace: solve one side at a time (DoorDash restaurants first, Airbnb hosts first); aim for 50 suppliers / 500 customers on one side before attempting the other.
- Each section includes a what-failed example.

**Loaded by:** `outreach-engine`, `pricing-model`, `signal-audit`, `idea-pressure-test`.

### 5.5 `founder-resilience-protocols.md`

**Content:**
- Sustainable-pace check.
- Decision quality under fatigue.
- Cofounder-alignment one-line check ("My cofounder and I both believe our biggest risk is X and our biggest advantage is Y").
- "You are not your company" reframe.
- Loneliness diagnostic.
- Citations: Horowitz, Andreessen, Paul Graham ("relentlessly resourceful").

**Loaded by:** new `founder-resilience`, `pivot-decision`, `cofounder-fit`.

### 5.6 `ai-era-anti-patterns.md`

**Content:**
- The 8 AI-era founder traps (wrapper-without-distribution, "ChatGPT for X" without wedge, token-cost denial, etc.).
- AI-stack selection matrix.
- Vibe-code vs. craft-code gate.
- Synthetic-user ban for validation.
- Model-market-fit failure mode.
- Token COGS instrumentation requirement.
- Case studies: Chegg ($14B lost to AI Overviews), Magic, AI wrapper graveyard.

**Loaded by:** new `ai-mvp-stack-selection`, `idea-pressure-test`, `mvp-architect`, `signal-audit`, `pricing-model`.

### 5.7 `positioning-frameworks.md`

**Content:**
- April Dunford 10-step positioning.
- Andy Raskin strategic narrative.
- "Old game / new game / promised land" structure.
- Competitive alternatives mapping (NOT just direct competitors).
- Category-creation vs. category-fit decision.

**Loaded by:** new `positioning-narrative`, `artifact-builder`, `outreach-engine`.

### 5.8 `jtbd-protocols.md`

**Content:**
- Christensen/Moesta/Klement vs. Ulwick (two schools, when to use which).
- Bob Moesta Switch Interview (47-min, 10-phase protocol).
- Four Forces of Progress (Push + Pull > Anxiety + Habit).
- Outcome statements (Ulwick: "minimize time to X, maximize Y").
- Opportunity scoring formula: Importance + max(Importance − Satisfaction, 0).
- When JTBD beats Mom Test, when it doesn't.

**Loaded by:** `discovery-coach`, `problem-focus`, `idea-pressure-test`.

### 5.9 `decision-journal-template.md`

**Content:**
- Farnam Street decision journal template.
- Annie Duke kill-criteria format (state + date).
- Brier score self-tracking framework.
- Pre-mortem facilitation protocol (Klein, 5-step).
- Mediating Assessments Protocol (Kahneman).
- The Tenth Man rule (Ifcha Mistabra).
- Sycophancy circuit-breaker check.

**Loaded by:** `bias-sentinel.md` (as enforcement override), `pivot-decision`, `pmf-audit`, `mvp-architect`, `signal-audit`.

### 5.10 `aggressive-consultation-archetype.md`

**Content:**
- Twelve behaviors for `tone-and-stance.md` (criticize the artifact not the founder, lead with observation, name the load-bearing claim, etc.).
- Cost-of-decision gate (push hardest on irreversible decisions).
- Twelve patterns for `bias-sentinel.md` (sycophancy detector, Tenth Man trigger, key assumptions check, etc.).
- Citations: Radical Candor (Kim Scott), Crucial Conversations, Gottman (criticism vs. contempt), institutional devil's advocacy, Tetlock open-mindedness.

**Loaded by:** `bias-sentinel.md` (always), `tone-and-stance.md` (always).

---

## Part 6 — Architectural Improvements

### 6.1 `STARTUP-STATE.md` schema v2.0

Current schema has ~25 fields. v2.0 adds ~15. Schema version bumps to 2.0; v1 → v2 migration is documented in `state-document-protocol.md`.

**New sections:**

```markdown
## AI Economics (if AI-product)
- Token cost per active user (last 30d): $
- LTV / inference-cost ratio: X (target ≥3)
- Margin per active user trend: improving / flat / declining
- Model dependency risk: low / medium / high (foundation lab could ship this natively)

## Retention Cohorts (post-launch)
- D1 retention: X%
- D7 retention: X%
- D28 retention: X%
- L7/L28 curve shape: smile / frown / flat
- Cohort retention by signup month (table)

## Positioning (post-validation)
- Competitive alternatives:
- Unique attributes:
- Best-fit customer (sharper than ICP):
- Market category we sit in:
- Strategic narrative (Raskin format):

## Decision Journal
| # | Date | Decision | Confidence% | Alternatives | Key assumptions | Review date | Outcome |
|---|------|----------|-------------|--------------|-----------------|-------------|---------|

## Kill Criteria Registry (Annie Duke format)
| # | Criterion | Deadline | Status | Outcome |
|---|-----------|----------|--------|---------|

## Sycophancy Check (auto-logged every 5 turns)
- Last contrarian pass: [date / turn]
- Recent disagreements:
- Recent unquantified praise: count

## Research Cache (deduplication)
| Topic | Last researched | Source skill | Brief location |
|-------|-----------------|--------------|----------------|

## Opportunity Solution Tree (post-validation)
- Outcome:
- Opportunities (children):
- Solutions (grandchildren):
- Assumption tests (leaves):
```

### 6.2 Strip forward-reference debt

Every "ships in v0.2/v0.4 — until then…" line should be removed. Everything ships. Stale references include:
- `signal-audit` line 25 ("pmf-audit (also v0.4)")
- `rapid-experiments` line 16 (auto-fire from skills not yet shipped)
- `pivot-decision` line 15
- Multiple "if available" caveats across `pricing-model`, `outreach-engine`, etc.

### 6.3 Hooks (Claude Code native)

Two `SessionStart` hooks worth adding (per the skill-engineering research):

1. **State-injection hook.** Reads `.claude/startup-state.md` at session start, injects: "User is at stage `<X>`; preferred next skill: `<Y>`; PMF stage: `<Z>`." This makes the right skill more likely to fire without explicit invocation.

2. **Stale-research alert hook.** Checks state for `last_market_intel_date` per topic; if >30 days ago and topic is still active, prompts: "Market research on `<topic>` is 45 days old. Consider re-running `market-intel` before next decision."

Hooks live in the plugin's `hooks.json`. They're per-Claude-Code, optional.

### 6.4 Subagent forking on heavy skills

Add to frontmatter for `market-intel`, `founder-context` (parallel domain research), `pmf-audit` (when designing survey + processing N=100 responses):

```yaml
context: fork
agent: Explore
allowed-tools: WebSearch WebFetch Read Glob Grep
```

Heavy work runs in isolated subagent context. Main conversation receives only the structured brief.

### 6.5 `evals/` directory + script

Top-level `evals/` directory with:
- `run_evals.py` — runs all `evals.json` against Claude with the plugin installed.
- `rubric.json` — per-skill scoring rubric (trigger correctness, process adherence, refusal appropriateness, hand-off accuracy).
- `golden_transcripts/` — known-good conversations to regression-test against.

Run via: `npm test` (alias) or `python evals/run_evals.py`. Required pass before any version bump.

---

## Part 7 — Distribution & Marketplace Strategy

### 7.1 Anthropic official marketplace path

The competitive-landscape research is clear: `obra/superpowers` is shipped via `anthropics/claude-plugins-official`. Getting `startup-skills` there is the single highest-leverage distribution decision.

**Action plan:**
1. Verify license compatibility with marketplace guidelines (PolyForm-NC is source-available, not OSI-open-source — may need an MIT or Apache-licensed mirror for official inclusion; verify with Anthropic).
2. Submit a PR to `anthropics/claude-plugins-official` when v1.0 ships.
3. Mirror at `claudemarketplaces.com`, `awesome-claude-skills` (travisvn), `tonsofskills.com`.

### 7.2 Launch narrative

Most AI-tool launches lead with capability ("I built a startup advisor"). Lead instead with the wedge: **adversarial structural honesty.**

**Suggested launch artifacts:**
- HN post + IH post + X thread: **"Claude told me to kill my startup. Here's the skill that did it."** Lead with one specific founder story (real or composite-with-permission) where the system refused to validate a tar-pit idea.
- Demo video: 90 seconds of `idea-pressure-test` saying "kill it" with the founder reluctantly agreeing.
- Quote-bait sentence for X: "Most AI founder tools are sycophants. This one isn't."

**Influencer amplifier targets:** Garry Tan, Jesse Vincent (obra/superpowers), Sahil Lavingia, Lenny Rachitsky, Dalton Caldwell. A single quote-RT from any = 1000-install spike.

**Communities to launch in:** Indie Hackers Discord + forum (~115k), r/SideProject, r/EntrepreneurRideAlong, HN (Show HN), YC SS forum, Maven cohorts.

### 7.3 Pricing / commercial license

PolyForm-NC is correct for adoption (free for hobby, personal, research, charity — every actual target user).

**Commercial license path:** accelerators (YC, Techstars), agencies, fractional-CTO firms, VC platform teams want to embed for paid programs. Suggested model: $X/seat/month commercial license. Same path EPPlus uses post-LGPL→PolyForm switch.

---

## Part 8 — Quality, Evaluation, and Pilot Program

### 8.1 Eval harness (per Part 2.6)

Per skill, ship `evals.json` with ~30 prompts:
- 10 should clearly trigger
- 10 adjacent (sometimes trigger)
- 10 should not trigger

Score: trigger accuracy, process adherence, refusal appropriateness, hand-off correctness. Run before every version bump.

### 8.2 Calibration self-tracking

Add Brier-score logging to `bias-sentinel.md`: every probabilistic claim ("I'd give this ~20% of working") gets logged with date + claim. When the outcome is known (next decision gate), record actual outcome. Compute calibration. Make this visible to the founder ("When I say 80%, I've been right X% of the time on past predictions in your project.").

### 8.3 Founder pilot program

The v1.0 spec calls for "dogfooded with 5 real founders." Expand:
- Recruit 10 pre-PMF founders, half pre-idea, half mid-validation.
- 4-week engagement, weekly check-in.
- Document outcomes: decisions sped up (Yes/No + days saved), pivot/persevere clarity, customer interviews completed, founder NPS.
- Publish results (with permission) in a launch post.

### 8.4 Telemetry (privacy-first)

Spec says "no telemetry in v0.1." For v2.0, add an **opt-in** feedback hook:
- After a session that ends in a decision (continue/pivot/build/raise), prompt: "If this session was useful, would you mind sharing a 1-line outcome to help us improve?"
- Anonymized; opt-in only; stored in a GitHub Discussions thread.
- Never sent automatically. Never includes state-document content.

### 8.5 GitHub Star benchmarks

v1.0 spec target: 1,000 stars in 6 months. v2.0 with the launch plan and marketplace inclusion: **realistic stretch target 5,000 stars in 6 months.** (For context: superpowers crossed 5k in its first months. Same audience overlap, more specific founder focus.)

---

## Part 9 — Phased Roadmap

### Phase 1 — Critical fixes (Weeks 1-2)

- [ ] Rewrite all 16 skill descriptions in TRIGGER/SKIP format
- [ ] Add HARD-GATE blocks to 6 decision-gate skills (signal-audit, mvp-architect, outreach-engine, pmf-audit, pricing-model, pivot-decision)
- [ ] Strip all forward-reference "v0.X if available" debt
- [ ] Add live state injection (` !`cat` ` block) to every skill body
- [ ] Update `tool-recommendations.md` with 2026 pricing
- [ ] Add archetype rows to `sales-funnel-math.md`
- [ ] Add source-quality + deposit-size modifiers to `validation-techniques.md` weights

**Deliverable:** v1.0 with the lowest-effort, highest-leverage fixes.

### Phase 2 — Methodology refresh (Weeks 3-6)

- [ ] Add Torres/Moesta/Indi Young to `discovery-coach` + new `continuous-discovery-patterns.md`
- [ ] Add Balfour Four Fits + Casey Winters retention + Andrew Chen power-user-curve + AI PMF Treadmill to `pmf-audit` + new `retention-metrics.md`
- [ ] Add Ramanujam Minivation + AI outcome-based pricing to `pricing-model` + update `pricing-frameworks.md`
- [ ] Update `tone-and-stance.md` with 12 calibrated behaviors
- [ ] Upgrade `bias-sentinel.md` with Annie Duke, Tetlock, Noise, decision-journal template, sycophancy circuit-breaker, Tenth Man rule, forbidden-phrase linter
- [ ] Update YC canon citations (Tan, Lightcone, Founder Mode, Tom Blomfield, Diana Hu, current RFS)
- [ ] Add 10 new references (Part 5)

**Deliverable:** v1.5 — 2026-current canon, no methodology lag.

### Phase 3 — New skills + AI-era playbook (Weeks 7-10)

- [ ] Build `continuous-discovery`
- [ ] Build `ai-mvp-stack-selection` + `ai-era-anti-patterns.md`
- [ ] Build `positioning-narrative` + `positioning-frameworks.md`
- [ ] Build `cofounder-decision`
- [ ] Build `founder-resilience` + `founder-resilience-protocols.md`
- [ ] Split `outreach-engine` Step 9 into Continuous Launch section + add 2026 deliverability + LinkedIn comment-first + AI Overviews SEO + signal-based outbound modules
- [ ] Add `jtbd-protocols.md`

**Deliverable:** v1.8 — six new skills, AI-era playbook complete.

### Phase 4 — Architecture + eval harness + launch (Weeks 11-14)

- [ ] Migrate `STARTUP-STATE.md` to schema v2 (AI economics, retention cohorts, decision journal, positioning, OST, kill-criteria registry, research cache)
- [ ] Add SessionStart hooks (state injection, stale-research alert)
- [ ] Add `context: fork` to heavy skills
- [ ] Ship `evals.json` for all 22 skills
- [ ] Build `evals/run_evals.py` + rubric
- [ ] Run pilot with 10 founders, document 3+ concrete outcomes
- [ ] Submit to `anthropics/claude-plugins-official`
- [ ] Launch posts (HN, IH, X) with the "Claude told me to kill my startup" narrative

**Deliverable:** v2.0 GA — best-in-class founder-advisor system on Claude Code.

### Beyond v2.0 (post-launch)

- Post-PMF expansion: `scaling-playbook`, `fundraising-execution`, `first-hires`, `hiring-debt`.
- Archetype-specialized variants: marketplace deep-dive, consumer deep-dive, hardware deep-dive, AI-infra deep-dive.
- Commercial license tier (accelerators, agencies, fractional-CTO firms).
- Internationalization (English-only for v2.0; localize for major markets post-1.0).

---

## Part 10 — Concrete Before/After Examples

### 10.1 `orientation` skill — before/after

**Current frontmatter:**
```yaml
description: >
  (startup-skills) Entry point for the Startup Skills system. Use at the start of any new startup session or when the user says "help me with my startup," "I have an idea," "where do I begin," or "what should I do next." Initializes STARTUP-STATE.md and routes to the right next skill based on where the founder actually is.
```

**Proposed frontmatter:**
```yaml
description: |
  Entry point for Startup Skills. Initializes `STARTUP-STATE.md` and routes the founder to the correct next skill based on where they actually are (vs. where they wish they were). Establishes the Aggressive Epistemic Auditor stance from message one.

  TRIGGER when: first session in a project (no `.claude/startup-state.md` exists); user says "help me with my startup", "I have an idea", "where do I begin", "I want to start a company", "what should I do next", "I'm stuck"; user mentions starting a startup without prior context.

  SKIP: `.claude/startup-state.md` exists AND was updated <7 days ago (read state, continue from there instead — invoke the skill named in the most recent Session Log entry); user is mid-flow in another skill (e.g., debriefing an interview = `discovery-coach`); user is asking a tactical question (pricing, deck, etc.) — route directly to the relevant skill.

paths:
  - ".claude/startup-state.md"
```

**Current body opening:**
> "The entry point. Establishes the Aggressive Epistemic Auditor stance from message one..."

**Proposed body opening:**

````markdown
# Orientation

The entry point. Establishes the Aggressive Epistemic Auditor stance, initializes `STARTUP-STATE.md`, routes to the next skill.

## HARD-GATE — do not proceed past this without:
- [ ] Reading existing `.claude/startup-state.md` (live, below)
- [ ] Either initializing it OR confirming with user that they want to reorient
- [ ] One orientation question with five options answered

## Current state (live)
```!
cat .claude/startup-state.md 2>/dev/null || echo "(no state file — initializing fresh)"
```

## Red flags

| Founder behavior | Response |
|---|---|
| Wants to start with a deck or landing page | Refuse. Route through validation first. |
| Has "an idea about AI/blockchain/LLMs for something" | SISP framing. Route to `idea-genesis` with refusal note. |
| "I just need to start building" without validation | Name the bias (action bias). Route to `problem-focus` or `rapid-experiments`. |
| State doc exists and is <7 days old | This skill is the wrong one. Ask: "Continue from `<last_skill>`, or reorient?" |

[... rest of body ...]
````

### 10.2 New reference example — `retention-metrics.md` sample

````markdown
# Retention Metrics

Diagnose and fix cohort retention. Currently the gap between "PMF Survey says we're at 35%" and "we still don't grow" is unexplained — retention mechanics are the missing diagnostic.

## Cohort retention benchmarks by archetype

| Archetype | D7 | D28 | D90 | Notes |
|---|---|---|---|---|
| Consumer mobile | 20-35% | 8-15% | 4-8% | Flat by D60 = PMF |
| Consumer web | 25-40% | 12-20% | 6-12% | Same |
| B2B SaaS | 40-60% | 25-40% | 15-30% | NRR matters more post D90 |
| Devtools (PLG) | 35-50% | 20-35% | 12-25% | "Magic curve" |
| Marketplace (demand-side) | 15-25% | 5-10% | 2-5% | Frequency-dependent |
| Games | 20-35% | 5-10% | 1-3% | F2P benchmark |

Compute: cohort retention = % of day-1 cohort still active on day N. "Active" = performed core action ≥1x in window.

## Smile vs. frown vs. flat curve

(per Andrew Chen, a16z)

- **Smile curve.** Plot users by # of active days in 28-day window. Mass at 1 day (newbies) + mass at 27-28 days (power users). Healthy.
- **Frown curve.** Mass in the middle (5-15 days), no power-user tail. Anti-PMF.
- **Flat retention curve** (different metric — cohort over time): flat by month 3 = PMF. Decay continuing past month 3 = no PMF.

[... etc ...]
````

### 10.3 New skill example — `ai-mvp-stack-selection` sample

````markdown
---
name: ai-mvp-stack-selection
description: |
  Match the founder's MVP to the right AI-stack (Lovable, Bolt, Cursor, Claude Code, Replit Agent, v0). Enforces the vibe-vs-craft gate — bans vibe-coding for regulated/payments/auth/PII surfaces. Surfaces 1000x/10x prototype/production tradeoff explicitly.

  TRIGGER when: user is starting an MVP and asks about stack choice; user says "Lovable", "Bolt", "Cursor", "v0", "Replit Agent", "vibe code", "AI build"; technical ability < "can build" + non-trivial product; founder is regulated industry.

  SKIP: founder already has working MVP (route to `outreach-engine`); founder is at validation phase (route to `rapid-experiments`); founder is bare-metal infrastructure (this skill is for application-layer MVPs).
---

# AI-MVP Stack Selection

## HARD-GATE

If the MVP touches ANY of: auth (passwords, tokens, sessions), payments (Stripe, etc.), PII (HIPAA, GDPR, financial PII), enterprise SLAs, regulated industry (health, legal, fin) — vibe-coding is BANNED. Craft-code only (Cursor + Claude Code).

If the founder pushes back: cite the studies. 322% more privilege-escalation paths and 153% more design flaws in LLM-generated code (Stack Overflow, MIT Sloan). The 1000x faster prototype, 10x slower production tradeoff is real. They will pay the production-hardening cost regardless. Better to pay it once with a clean foundation than 10x with a vibe-code foundation.

[... process steps ...]
````

---

## Closing

The system this plan describes does one specific thing: it keeps founders from lying to themselves long enough to find out what's true. v0.4 already does this. v2.0 makes it the best-in-class instance of doing it on Claude Code in 2026.

Three sentences that summarize the whole plan:

1. **Skill engineering matters more than methodology** — the descriptions, HARD-GATEs, red-flag tables, and eval harness are higher leverage than any new methodology citation.
2. **The 2026 canon refresh is non-optional** — Torres, Moesta, Dunford, Annie Duke, Balfour, Ramanujam, the AI-era playbook, and the new YC canon are the difference between a 2020 system and a 2026 system.
3. **The wedge to lean into is adversarial structural honesty in the pre-PMF zone, native to Claude Code** — no competitor occupies this; sycophancy is the dominant failure mode in every adjacent product; the launch narrative writes itself.

Build it accordingly.
