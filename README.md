![Version](https://img.shields.io/badge/version-0.5.0-blue)
[![License](https://img.shields.io/badge/license-PolyForm_Noncommercial-orange)](./LICENSE)
![Skills](https://img.shields.io/badge/skills-21-green)
![References](https://img.shields.io/badge/references-33-green)
[![Ko-fi](https://img.shields.io/badge/support-Ko--fi-ff5f5f)](https://ko-fi.com/quinnhall07)
![Claude Code](https://img.shields.io/badge/Claude_Code-plugin-blueviolet)
[![GitHub Issues](https://img.shields.io/github/issues/quinnhall07/startup-skills)](https://github.com/quinnhall07/startup-skills/issues)
[![GitHub Stars](https://img.shields.io/github/stars/quinnhall07/startup-skills)](https://github.com/quinnhall07/startup-skills/stargazers)

> Startup Skills is free for noncommercial use and always will be. If it saves you a bad pivot or six months of building the wrong thing, consider [buying me a coffee](https://ko-fi.com/quinnhall07).

*Want commercial use? [Contact me](mailto:quinn.hall.scho@gmail.com).*

# Startup Skills

A Claude Code plugin that turns Claude into an Aggressive Epistemic Auditor for founders. Idea to PMF, with Y Combinator methodology, the Mom Test, the Lean Startup, and behavioral economics applied as structural overrides.

**Status:** v0.5 — 21 skills, 33 references. Methodology refreshed to 2026 canon (Torres / Moesta / Dunford / Duke / Tetlock / Balfour / Ramanujam / Andrew Chen). AI-era playbook integrated. Every skill carries TRIGGER/SKIP routing blocks; decision-gate skills carry HARD-GATE refusal blocks.

---

## What Is This?

Startup Skills compresses the time between "I have an idea (or no idea)" and "I know whether this is real." It keeps compressing it through customer discovery, MVP design, first customers, and product-market fit measurement. The system is distributed as a GitHub repository structured as a Claude Code plugin; users install with two commands and get a thinking partner who actively scours Reddit, G2, Crunchbase, and job postings while they're talking.

The tone is direct and willing to wound. The system will flatly tell a founder their idea is a tar pit, refuse to weight polite-customer signal, and halt building until behavioral demand is validated. It does this because diplomatic dishonesty causes six-month detours, and most founders fail not from bad execution but from cognitive delusion under pressure. Awareness of bias does not cure bias. The system installs the structural overrides — evidence weighting, pre-mortems, falsification pre-commitments — that bias-awareness alone cannot.

21 skills total, plus a shared reference library of 33 documents. Each skill is small, opinionated, and oriented toward a specific failure mode that destroys early-stage startups.

## The Thesis

> The most expensive mistake in startups is building something nobody wants. The second most expensive is discovering this after six months instead of six days. Startup Skills compresses that distance — combining the founder's domain intuition and judgment with Claude's ability to research at scale, identify cognitive bias in real time, build validation artifacts in minutes, and pattern-match across thousands of startup stories. The human does what only humans can: have lived expertise, build relationships, make sales calls, commit. Claude does what only Claude can: read the entire internet, never tire of pushing back, structurally enforce evidence over opinion. The system is not a coach in the soft sense. It is an Aggressive Epistemic Auditor whose job is to keep the founder from lying to themselves long enough to find out what's true.

## Who Is This For?

Six personas, all served by the same system; only the entry point differs.

- **The first-time founder with no idea.** Has motivation, no clear domain. Enters via `idea-genesis`.
- **The domain expert with an idea.** Industry professional who has observed pain. Enters via `idea-pressure-test`.
- **The technical builder with capacity but no problem.** Engineer or PM who can build but has no validated pain to solve. Enters via `market-intel` → `idea-genesis`.
- **The stuck founder.** 3–6 months in, no traction. Enters via `signal-audit` → `pivot-decision`.
- **The side-project builder.** Working a day job, limited time. Uses `rapid-experiments` for fast validation.
- **The post-launch founder seeking PMF.** Has users, wants to know if they have product-market fit. Enters via `pmf-audit`.

Built for U.S.-style technology startups (the YC archetype: tech-enabled, venture-fundable, scaling through software). Less applicable to traditional small businesses, services-only firms, and businesses for which Sean Ellis-style PMF is not a meaningful metric.

## What Is Included?

### The 21 Skills

**Entry + context (2)**

- **`orientation`** — Entry point. Initializes `STARTUP-STATE.md`, explains the system, routes to the next skill.
- **`founder-context`** — Captures domain expertise, technical ability, time horizon, archetype, resources, risk tolerance. Runs parallel domain research while interviewing.

**Discovery (4)**

- **`idea-genesis`** — For founders with no idea. Organic interview track + parallel research track. Surfaces 5–7 candidate idea spaces. Refuses SISP framings.
- **`market-intel`** — Independent web research structured as a brief (pain expressed, customer vocabulary, who's building, what's missing, why-now, tar-pit check). Refuses TAM-as-validation.
- **`idea-pressure-test`** — Steel-mans the idea first, then scores it on Dalton's 4-criteria rubric and the YC 10-question framework. Detects tar pits, schlep blindness, SISP framings. Willing to say "kill it."
- **`cofounder-fit`** — Diagnoses team gaps. Applies YC's non-negotiable rules. Produces a 4-week trial protocol on request. Refuses pre-PMF sales hires.

**Validation (3)**

- **`problem-focus`** — Recursive specificity drill: turns "companies need better X" into a sharp, testable ICP hypothesis. Refuses to proceed if the ICP can't be found online.
- **`discovery-coach`** — The most important skill. PREPARE mode (Mom-Test-aligned scripts, role-play) and DEBRIEF mode (classifies every customer statement, applies 7 false-signal patterns, refines hypothesis).
- **`signal-audit`** — The PMF running score. HARD-GATE refusal of build/scale/hire/raise decisions unsupported by behavioral evidence.

**Execution (4)**

- **`rapid-experiments`** — Designs Fake Door / Wizard of Oz / Concierge MVP tests matched to archetype. Enforces falsification pre-commitments.
- **`ai-mvp-stack-selection`** *(v0.5)* — Match MVP to the right AI-build stack (Lovable / Bolt / Cursor / Claude Code / Replit Agent). Enforces vibe-vs-craft gate; bans vibe-coding for regulated / payments / auth / PII surfaces.
- **`mvp-architect`** — Ruthless feature-cutting. Hard 2–6 week deadline. HARD-GATE refusal of pre-validation builds without explicit risk acknowledgment.
- **`pricing-model`** — Force-commit a single price. Ramanujam WTP-before-build. AI-aware: outcome-based pricing, per-seat erosion, token-cost economics. Refuses B2B freemium pre-PMF.

**Distribution + PMF (3)**

- **`outreach-engine`** — Prospect lists, YC-style cold emails, funnel math, Continuous Launch. Modernized for 2026: SPF/DKIM/DMARC + secondary-domain deliverability stack, LinkedIn comment-first, signal-based outbound. Refuses paid acquisition pre-PMF.
- **`pmf-audit`** — Full Sean Ellis 40% Rule + Vohra Superhuman blueprint. Adds Casey Winters retention-curve check + Andrew Chen L7/L28 + Balfour Four Fits + AI-product specifics. HARD-GATE freeze of scaling below 40%.
- **`continuous-discovery`** *(v0.5)* — Teresa Torres's weekly Opportunity Solution Tree cadence post-validation. Refuses to let founders stop interviewing after launch.

**Decision gates (3)**

- **`pivot-decision`** — Dalton's opportunity cost + Klein pre-mortem + Annie Duke's "would you start today?" + monkeys-vs-pedestals. Generates 3–5 scored pivot candidates rooted in what the founder already learned.
- **`cofounder-decision`** *(v0.5)* — Cofounder conflict, breakup, mid-flight equity disputes. Refuses to help one founder convince the other without both present. Three outcomes: continue with role realignment / clean exit / pivot.
- **`founder-resilience`** *(v0.5)* — Decision-quality circuit-breaker. Annie Duke's 24-hour rule; cofounder-alignment one-liner; loneliness diagnostic. Defers irreversible decisions under acute stress.

**Positioning + artifacts (2)**

- **`positioning-narrative`** *(v0.5)* — April Dunford 10-step positioning + Andy Raskin 5-act strategic narrative. Refuses pre-signal positioning. Feeds `artifact-builder` and `outreach-engine`.
- **`artifact-builder`** — Pitch decks, landing pages, one-pagers, investor emails, demo day scripts. Pulled from the state document. Refuses pre-signal pitch decks. Marks thin sections explicitly.

### Reference Library (33 documents)

**Foundational protocols** — `tone-and-stance`, `state-document-template` (schema v2), `state-document-protocol`, `bias-sentinel`, `aggressive-consultation-archetype` *(v0.5)*, `research-playbook`.

**Customer discovery** — `mom-test-principles`, `evidence-weighting-matrix`, `false-signal-detection`, `continuous-discovery-patterns` *(v0.5)*, `jtbd-protocols` *(v0.5)*.

**Idea evaluation** — `scoring-rubrics`, `tar-pit-detection`, `case-studies`, `ai-era-anti-patterns` *(v0.5)*.

**MVP + experiments** — `validation-techniques`, `landing-page-patterns`, `mvp-examples`.

**PMF + retention** — `pmf-scoring`, `retention-metrics` *(v0.5)*, `growth-loops` *(v0.5)*.

**Pricing + distribution** — `pricing-frameworks`, `sales-funnel-math`, `distribution-by-archetype` *(v0.5)*, `email-templates`, `tool-recommendations`.

**Decision quality** — `decision-journal-template` *(v0.5)*, `founder-resilience-protocols` *(v0.5)*, `cofounder-frameworks`.

**Positioning + artifacts** — `positioning-frameworks` *(v0.5)*, `pitch-deck-structure`, `one-pager-structure`.

**External canon** — `external-resources`.

#### Reference Path

It's worth noting that the reference path in the SKILL.md files is tailored for use with Claude Code, not Claude.ai. They all use `${CLAUDE_PLUGIN_ROOT}/references/...` as the path. Claude.ai does not support plugin file paths. However, it will likely be able to recognize an alternative as long as you supply the references in the knowledge base. 

## Install

Two commands. That's it.

```text
/plugin marketplace add quinnhall07/startup-skills
/plugin install startup-skills@startup-skills
```

Then start a Claude Code session in your project directory and type:

```text
/skill orientation
```

Or just describe what you want — "I have an idea, can we pressure-test it?" — and the system handles routing.

The state document lives at `.claude/startup-state.md` in your project directory. It persists across sessions so you never have to re-introduce yourself. To override the path: set `STARTUP_STATE_PATH=/absolute/path/to/file.md`.

### Installing on Claude.ai (alternative, not preferred)

1. Clone or download this repo.
2. Create a new Claude.ai Project.
3. Upload the `references/` folder and the `SKILL.md` files to the project's knowledge.
4. In the project's custom instructions, paste the contents of `references/state-document-protocol.md` and a one-paragraph orientation pointing Claude to the SKILL.md files.
5. Start a conversation. Claude will surface skills based on the descriptions in the SKILL.md frontmatter.

## Methodology and Sources

Every framework, scoring rubric, and bias antidote in Startup Skills comes from a named, attributable source.

- **Y Combinator Startup School** — Paul Graham, Michael Seibel, Dalton Caldwell, Gustav Alstromer, Jared Friedman, Kat Manalac, Divya Bhat.
- **Rob Fitzpatrick, *The Mom Test*** — customer discovery methodology.
- **Eric Ries, *The Lean Startup*** — Build-Measure-Learn, MVP as scientific experiment.
- **Steve Blank, *The Four Steps to the Epiphany*** — Customer Development methodology.
- **Sean Ellis, the 40% Rule** — the leading-indicator PMF survey.
- **Rahul Vohra, Superhuman PMF blueprint** — HXC segmentation, polarity analysis, fence-sitter conversion.
- **Daniel Kahneman, Amos Tversky, Dan Lovallo** — inside view vs outside view, Reference Class Forecasting, planning fallacy.
- **Gary Klein** — the Pre-Mortem.
- **Lenny Rachitsky** — go-to-market motions by company type; first-customer data.
- **Marc Andreessen** — qualitative PMF indicators.
- **Teresa Torres** *(v0.5)* — Continuous Discovery Habits, Opportunity Solution Trees, story-based interviewing.
- **Bob Moesta / Alan Klement / Tony Ulwick** *(v0.5)* — Jobs-to-be-Done (Switch Interview, Four Forces of Progress, Outcome-Driven Innovation).
- **April Dunford** *(v0.5)* — 10-step positioning, competitive alternatives.
- **Andy Raskin** *(v0.5)* — strategic narrative, 5-act deck spine.
- **Brian Balfour** *(v0.5)* — Four Fits framework (Market-Product / Product-Channel / Channel-Model / Model-Market).
- **Casey Winters** *(v0.5)* — retention curves, growth loops.
- **Andrew Chen** *(v0.5)* — Cold Start Problem, Power User Curve, AI-era moats.
- **Annie Duke** *(v0.5)* — Thinking in Bets / Quit, kill criteria, monkeys-vs-pedestals, "resulting."
- **Phil Tetlock** *(v0.5)* — Superforecasting, calibration, Bayesian updating.
- **Kahneman / Sibony / Sunstein** *(v0.5)* — Noise, Mediating Assessments Protocol.
- **Madhavan Ramanujam** *(v0.5)* — Monetizing Innovation, WTP-before-build, Minivation trap.
- **Garry Tan + Founder Mode (PG 2024) + Lightcone Podcast** *(v0.5)* — modern YC canon.

Full annotated list in `references/external-resources.md`.

## Status and Roadmap

- **v0.5 (current)** — 21 skills, 33 references. 2026 canon refresh. AI-era playbook integrated. TRIGGER/SKIP + HARD-GATE patterns on every skill.
- **v1.0 (next)** — Per-skill `evals.json` benchmark harness; dogfooded with real founders; walkthrough examples in `examples/`; description triggering accuracy optimization via skill-creator pattern.

See [`CHANGELOG.md`](./CHANGELOG.md) for the full v0.1 → v0.5 progression, and [`docs/plans/2026-05-13-startup-skills-v2-improvement-plan.md`](./docs/plans/2026-05-13-startup-skills-v2-improvement-plan.md) for the v0.5 design rationale.

## License

PolyForm Noncommercial License 1.0.0. See [`LICENSE`](./LICENSE).

Noncommercial use is free. Commercial use requires a license from the maintainer.

## Contributing

Issues welcome — bugs, mis-attributions, methodology gaps, false-positive bias-sentinel firings. PRs for new skills and references are reviewed against `startup-skills-spec-v0.2.md`. Keep skills under 250 lines, keep references high-density, cite sources.

## Acknowledgments

The system synthesizes work from the Y Combinator partners (Graham, Seibel, Caldwell, Alstromer, Friedman, Manalac, Bhat, Tan, Blomfield, Hu, Koomen, Epstein, Taggar, Flora), Rob Fitzpatrick, Eric Ries, Steve Blank, Sean Ellis, Rahul Vohra, Teresa Torres, Bob Moesta, Alan Klement, Tony Ulwick, Indi Young, April Dunford, Andy Raskin, Brian Balfour, Casey Winters, Andrew Chen, Madhavan Ramanujam, Patrick Campbell, Daniel Kahneman, Amos Tversky, Dan Lovallo, Gary Klein, Annie Duke, Phil Tetlock, Lenny Rachitsky, Marc Andreessen, Kim Scott, Ben Horowitz. Errors are the maintainer's; the canon is theirs.