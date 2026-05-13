[![Support on Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/quinnhall07)

> Startup Skills is free and always will be. If it saves you a bad pivot or six months of building the wrong thing, consider buying me a coffee.

# Startup Skills

A Claude Code plugin that turns Claude into an Aggressive Epistemic Auditor for founders. Idea to PMF, with Y Combinator methodology, the Mom Test, the Lean Startup, and behavioral economics applied as structural overrides.

**Status:** v0.4 — full coded scope complete. 16 skills, 23 references.

---

## What this is

Startup Skills compresses the time between "I have an idea (or no idea)" and "I know whether this is real." It keeps compressing it through customer discovery, MVP design, first customers, and product-market fit measurement. The system is distributed as a GitHub repository structured as a Claude Code plugin; users install with two commands and get a thinking partner who actively scours Reddit, G2, Crunchbase, and job postings while they're talking.

The tone is direct and willing to wound. The system will flatly tell a founder their idea is a tar pit, refuse to weight polite-customer signal, and halt building until behavioral demand is validated. It does this because diplomatic dishonesty causes six-month detours, and most founders fail not from bad execution but from cognitive delusion under pressure. Awareness of bias does not cure bias. The system installs the structural overrides — evidence weighting, pre-mortems, falsification pre-commitments — that bias-awareness alone cannot.

16 skills total, plus a shared reference library of canonical methodology. Each skill is small, opinionated, and oriented toward a specific failure mode that destroys early-stage startups.

## The thesis

> The most expensive mistake in startups is building something nobody wants. The second most expensive is discovering this after six months instead of six days. Startup Skills compresses that distance — combining the founder's domain intuition and judgment with Claude's ability to research at scale, identify cognitive bias in real time, build validation artifacts in minutes, and pattern-match across thousands of startup stories. The human does what only humans can: have lived expertise, build relationships, make sales calls, commit. Claude does what only Claude can: read the entire internet, never tire of pushing back, structurally enforce evidence over opinion. The system is not a coach in the soft sense. It is an Aggressive Epistemic Auditor whose job is to keep the founder from lying to themselves long enough to find out what's true.

## Who's it for

Six personas, all served by the same system; only the entry point differs.

- **The first-time founder with no idea.** Has motivation, no clear domain. Enters via `idea-genesis`.
- **The domain expert with an idea.** Industry professional who has observed pain. Enters via `idea-pressure-test`.
- **The technical builder with capacity but no problem.** Engineer or PM who can build but has no validated pain to solve. Enters via `market-intel` → `idea-genesis`.
- **The stuck founder.** 3–6 months in, no traction. Enters via `signal-audit` → `pivot-decision`.
- **The side-project builder.** Working a day job, limited time. Uses `rapid-experiments` for fast validation.
- **The post-launch founder seeking PMF.** Has users, wants to know if they have product-market fit. Enters via `pmf-audit`.

Built for U.S.-style technology startups (the YC archetype: tech-enabled, venture-fundable, scaling through software). Less applicable to traditional small businesses, services-only firms, and businesses for which Sean Ellis-style PMF is not a meaningful metric.

## What's included

### The 16 skills

- **`orientation`** — Entry point. Initializes `STARTUP-STATE.md`, explains the system, routes to the next skill.
- **`founder-context`** — Captures domain expertise, technical ability, time horizon, archetype, resources, risk tolerance. Runs parallel domain research while interviewing.
- **`idea-genesis`** — For founders with no idea. Organic interview track + parallel research track. Surfaces 5–7 candidate idea spaces. Refuses SISP framings.
- **`market-intel`** — Independent web research structured as a brief (pain expressed, customer vocabulary, who's building, what's missing, why-now, tar-pit check). Refuses TAM-as-validation.
- **`idea-pressure-test`** — Steel-mans the idea first, then scores it on Dalton's 4-criteria rubric and the YC 10-question framework. Detects tar pits, schlep blindness, SISP framings. Willing to say "kill it."
- **`cofounder-fit`** — Diagnoses team gaps. Applies YC's non-negotiable rules. Produces a 4-week trial protocol on request. Refuses pre-PMF sales hires.
- **`problem-focus`** — Recursive specificity drill: turns "companies need better X" into a sharp, testable ICP hypothesis. Refuses to proceed if the ICP can't be found online.
- **`discovery-coach`** — The most important skill. PREPARE mode (Mom-Test-aligned scripts, role-play) and DEBRIEF mode (classifies every customer statement, applies 7 false-signal patterns, refines hypothesis).
- **`signal-audit`** — The PMF running score. Refuses to bless build/scale/hire/raise decisions unsupported by behavioral evidence.
- **`rapid-experiments`** — Designs Fake Door / Wizard of Oz / Concierge MVP tests matched to archetype. Enforces falsification pre-commitments.
- **`mvp-architect`** — Ruthless feature-cutting. Hard 2–6 week deadline. Refuses to scope a build until behavioral signal exists.
- **`pricing-model`** — Charge from day one. Refuses B2B freemium pre-PMF. Commits a single price into the state document.
- **`outreach-engine`** — Prospect lists, YC-style cold emails, funnel math, Continuous Launch. Refuses paid acquisition pre-PMF.
- **`pmf-audit`** — Full Sean Ellis 40% Rule + Vohra Superhuman blueprint. Freezes scaling below 40%.
- **`pivot-decision`** — Dalton's opportunity cost + Klein pre-mortem. Aggressively counters sunk cost. Generates 3–5 scored pivot candidates rooted in what the founder already learned.
- **`artifact-builder`** — Pitch decks, landing pages, one-pagers, investor emails, demo day scripts. Pulled from the state document. Refuses pre-signal pitch decks.

### Reference library (23 documents)

`tone-and-stance`, `state-document-template`, `state-document-protocol`, `bias-sentinel`, `research-playbook`, `mom-test-principles`, `evidence-weighting-matrix`, `false-signal-detection`, `scoring-rubrics`, `tar-pit-detection`, `pmf-scoring`, `sales-funnel-math`, `validation-techniques`, `landing-page-patterns`, `mvp-examples`, `case-studies`, `email-templates`, `pricing-frameworks`, `cofounder-frameworks`, `tool-recommendations`, `external-resources`, `pitch-deck-structure`, `one-pager-structure`.

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

### Installing on claude.ai (alternative)

1. Clone or download this repo.
2. Create a new Claude.ai Project.
3. Upload the `references/` folder and the `SKILL.md` files to the project's knowledge.
4. In the project's custom instructions, paste the contents of `references/state-document-protocol.md` and a one-paragraph orientation pointing Claude to the SKILL.md files.
5. Start a conversation. Claude will surface skills based on the descriptions in the SKILL.md frontmatter.

## Methodology and sources

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

Full annotated list in `references/external-resources.md`.

## Status and roadmap

- **v0.4 (current)** — Full coded scope. 16 skills, 23 references.
- **v1.0 (next)** — Per-skill benchmark harness; dogfooded with real founders; walkthrough examples in `examples/`; description triggering accuracy optimization.

See [`CHANGELOG.md`](./CHANGELOG.md) for the full v0.1 → v0.4 progression.

## License

PolyForm Noncommercial License 1.0.0. See [`LICENSE`](./LICENSE).

Noncommercial use is free. Commercial use requires a license from the maintainer.

## Contributing

Issues welcome — bugs, mis-attributions, methodology gaps, false-positive bias-sentinel firings. PRs for new skills and references are reviewed against `startup-skills-spec-v0.2.md`. Keep skills under 250 lines, keep references high-density, cite sources.

## Acknowledgments

The system synthesizes work from the Y Combinator partners (Graham, Seibel, Caldwell, Alstromer, Friedman, Manalac, Bhat), Rob Fitzpatrick, Eric Ries, Steve Blank, Sean Ellis, Rahul Vohra, Daniel Kahneman, Amos Tversky, Dan Lovallo, Gary Klein, Lenny Rachitsky, and Marc Andreessen. Errors are the maintainer's; the canon is theirs.