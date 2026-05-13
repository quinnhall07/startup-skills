# Startup Skills

A Claude Code plugin marketplace that turns Claude into an Aggressive Epistemic Auditor for founders. Idea to PMF, with Y Combinator methodology, the Mom Test, the Lean Startup, and behavioral economics applied as structural overrides.

**Status:** v0.1 — Discovery foundation (six skills, ten references). v0.2–v1.0 roadmap below.

---

## What this is

Startup Skills compresses the time between "I have an idea (or no idea)" and "I know whether this is real." It keeps compressing it through customer discovery, MVP design, first customers, and product-market fit measurement. The system is distributed as a GitHub repository structured as a Claude Code plugin marketplace; users install with one command and get a thinking partner who actively scours Reddit, G2, Crunchbase, and job postings while they're talking.

The tone is direct and willing to wound. The system will flatly tell a founder their idea is a tar pit, refuse to weight polite-customer signal, and halt building until behavioral demand is validated. It does this because diplomatic dishonesty causes six-month detours, and most founders fail not from bad execution but from cognitive delusion under pressure. Awareness of bias does not cure bias. The system installs the structural overrides — evidence weighting, pre-mortems, falsification pre-commitments — that bias-awareness alone cannot.

Sixteen skills total across five plugins (when complete), plus a shared reference library of canonical methodology. v0.1 ships the first two plugins — `startup-skills-core` and `startup-skills-discovery` — covering orientation, founder context, idea generation, market intelligence, idea pressure-testing, and cofounder fit. Each skill is small, opinionated, and oriented toward a specific failure mode that destroys early-stage startups.

## The thesis

> The most expensive mistake in startups is building something nobody wants. The second most expensive is discovering this after six months instead of six days. Startup Skills compresses that distance — combining the founder's domain intuition and judgment with Claude's ability to research at scale, identify cognitive bias in real time, build validation artifacts in minutes, and pattern-match across thousands of startup stories. The human does what only humans can: have lived expertise, build relationships, make sales calls, commit. Claude does what only Claude can: read the entire internet, never tire of pushing back, structurally enforce evidence over opinion. The system is not a coach in the soft sense. It is an Aggressive Epistemic Auditor whose job is to keep the founder from lying to themselves long enough to find out what's true.

## Who's it for

Six personas, all served by the same system; only the entry point differs.

- **The first-time founder with no idea.** Has motivation, no clear domain. Enters via `idea-genesis`.
- **The domain expert with an idea.** Industry professional who has observed pain. Enters via `idea-pressure-test`.
- **The technical builder with capacity but no problem.** Engineer or PM who can build but has no validated pain to solve. Enters via `market-intel` → `idea-genesis`.
- **The stuck founder.** 3–6 months in, no traction. Enters via `signal-audit` → `pivot-decision` (v0.2+).
- **The side-project builder.** Working a day job, has limited time. Uses `rapid-experiments` for fast validation (v0.3).
- **The post-launch founder seeking PMF.** Has users, wants to know if they have product-market fit. Enters via `pmf-audit` (v0.4).

Built for U.S.-style technology startups (the YC archetype: tech-enabled, venture-fundable, scaling through software). Less applicable to traditional small businesses, services-only firms with no product ambition, and businesses for which Sean Ellis-style PMF is not a meaningful metric.

## What's included in v0.1

### Plugin: startup-skills-core (2 skills)

- **`orientation`** — Entry point. Initializes `STARTUP-STATE.md`, briefly explains the system, asks one question to identify where the founder is, routes to the next skill.
- **`founder-context`** — Captures domain expertise, technical ability, time horizon, archetype, resources, risk tolerance, starting point. Runs parallel domain research while interviewing.

### Plugin: startup-skills-discovery (4 skills)

- **`idea-genesis`** — For founders with no idea. Runs an organic interview track AND a parallel research track on the founder's domain. Surfaces 5–7 candidate idea spaces, each with a named potential customer. Refuses Solution-In-Search-of-a-Problem framings.
- **`market-intel`** — Independent web research, structured as a brief (pain expressed, customer vocabulary, who's building, what's missing, why-now, tar-pit check). Refuses TAM-as-validation. Called by other skills as a subroutine, or invoked directly.
- **`idea-pressure-test`** — Steel-mans the idea first, then scores it on Dalton's 4-criteria rubric (market size, founder-market fit, ease of starting, early market feedback) and the YC 10-question framework. Calls `market-intel`. Detects tar pits, schlep blindness, SISP framings. Willing to recommend "kill it."
- **`cofounder-fit`** — Diagnoses team gaps. Applies YC's non-negotiable rules (work together first, near-equal equity, vesting). Produces a 4-week trial protocol on request. Refuses to validate pre-PMF sales hires or contractor v1 builds.

### Reference library (10 documents)

Shared canon loaded by skills on demand: `tone-and-stance`, `state-document-template`, `state-document-protocol`, `bias-sentinel`, `research-playbook`, `scoring-rubrics`, `tar-pit-detection`, `cofounder-frameworks`, `case-studies`, `external-resources`.

## Install — Claude Code (recommended)

```text
/plugin marketplace add quinnhall07/startup-skills
/plugin install startup-skills-core@startup-skills
/plugin install startup-skills-discovery@startup-skills
```

After install, start a Claude Code session in your project directory and type:

```text
/skill orientation
```

…or just describe what you want: "I have an idea, can we pressure-test it?" The system handles routing.

## Install — claude.ai (supported alternative)

1. Clone or download this repo.
2. Create a new Claude.ai Project.
3. Upload the `references/` folder and the SKILL.md files (or the full repo zip) to the project's knowledge.
4. In the project's custom instructions, paste the contents of `references/state-document-protocol.md` and a one-paragraph orientation pointing Claude to the SKILL.md files.
5. Start a conversation. Claude will surface skills based on the descriptions in the SKILL.md frontmatter.

If your claude.ai project knowledge is hitting limits, start with just `startup-skills-core`. The modular plugin structure makes this easy.

## Quick start

In a Claude Code session inside the project you want to work on:

```text
/skill orientation
```

The system creates `.claude/startup-state.md` (your shared anchor across sessions) and routes you to the right next skill. To override the state path: set `STARTUP_STATE_PATH=/absolute/path/to/file.md`.

## Methodology and sources

Every claim, framework, scoring rubric, and bias antidote in Startup Skills comes from a named, attributable source. The system does not invent methodology — it synthesizes existing rigorous methodology into a form Claude can apply consistently.

- **Y Combinator Startup School** — Paul Graham (*How to Get Startup Ideas*, *Do Things That Don't Scale*, *Schlep Blindness*), Michael Seibel (*How to Build an MVP*, *Product Development Cycle Fundamentals*), Dalton Caldwell (*All About Pivoting*, *How to Get and Evaluate Startup Ideas*, *Where Do Great Startup Ideas Come From*), Gustav Alstromer (*How to Get Your First Customers*), Jared Friedman (*How to Talk to User*), Divya Bhat (*Setting KPIs and Goals*), Kat Manalac (*The Best Way to Launch Your Startup*).
- **Rob Fitzpatrick, *The Mom Test*** — customer discovery methodology. Behavioral over attitudinal.
- **Eric Ries, *The Lean Startup*** — Build-Measure-Learn. MVP as scientific experiment.
- **Steve Blank, *The Four Steps to the Epiphany*** — Customer Development methodology.
- **Sean Ellis, the 40% Rule** — the leading-indicator PMF survey.
- **Rahul Vohra, Superhuman PMF blueprint** — HXC segmentation, polarity analysis, fence-sitter conversion.
- **Daniel Kahneman, Amos Tversky, Dan Lovallo** — inside view vs outside view, Reference Class Forecasting, planning fallacy, overconfidence.
- **Gary Klein** — the Pre-Mortem.
- **Lenny Rachitsky** — go-to-market motions by company type; first-customer data.
- **Marc Andreessen** — qualitative PMF indicators.
- **First Round Capital research, CB Insights post-mortems, the Dinnr post-mortem** — recurring failure-mode patterns.

Full annotated list in `references/external-resources.md`.

## Status and roadmap

- **v0.1 — Discovery Foundation (current).** `startup-skills-core` + `startup-skills-discovery`. 6 skills, 10 references.
- **v0.2 — Validation Layer.** Adds `startup-skills-validation` (3 skills: `problem-focus`, `discovery-coach`, `signal-audit`) + references for Mom Test, evidence weighting, false-signal detection.
- **v0.3 — Execution Layer.** Adds `startup-skills-execution` (4 skills: `rapid-experiments`, `mvp-architect`, `pricing-model`, `outreach-engine`).
- **v0.4 — PMF + Pivot + Artifacts.** Adds `startup-skills-pmf-and-pivot` (`pmf-audit`, `pivot-decision`) and `startup-skills-artifacts` (`artifact-builder`).
- **v1.0 — Polish + Evaluation.** Benchmark harness, dogfooded with real founders, walkthrough examples.

See [`CHANGELOG.md`](./CHANGELOG.md) for release notes.

## License

PolyForm Noncommercial License 1.0.0. See [`LICENSE`](./LICENSE).

In short: anyone can use, modify, and redistribute Startup Skills for **noncommercial** purposes. Commercial use (anything primarily intended for commercial advantage or monetary compensation) is reserved to the licensor. This keeps the project open for founders, students, and researchers while preserving commercial rights for the maintainer.

## Contributing

Issues welcome — bugs, mis-attributions, methodology gaps, false-positive bias-sentinel firings. Pull requests for new skills, references, or improvements are reviewed against the spec at `startup-skills-spec-v0.2.md`. Keep skills under 250 lines, keep references high-density, and cite sources.

## Acknowledgments

The system synthesizes work from the Y Combinator partners (Graham, Seibel, Caldwell, Alstromer, Friedman, Manalac, Bhat), Rob Fitzpatrick, Eric Ries, Steve Blank, Sean Ellis, Rahul Vohra, Daniel Kahneman, Amos Tversky, Dan Lovallo, Gary Klein, Lenny Rachitsky, and Marc Andreessen. Errors are the maintainer's; the canon is theirs.
