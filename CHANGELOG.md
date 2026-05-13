# Changelog

All notable changes to Startup Skills are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.4.0] — 2026-05-12

### Added
- `startup-skills-pmf-and-pivot` plugin (2 skills): `pmf-audit` (Sean Ellis 40% Rule + Vohra Superhuman blueprint), `pivot-decision` (Dalton opportunity cost + Klein pre-mortem + scored candidates).
- `startup-skills-artifacts` plugin (1 skill): `artifact-builder` (pitch decks, landing pages, one-pagers, investor emails, demo day scripts; refuses pre-signal pitch decks).
- Reference library additions: `pmf-scoring` (full Sean Ellis + Superhuman implementation), `pitch-deck-structure` (10–12 slide YC format), `one-pager-structure` (async one-page format).
- `.claude-plugin/marketplace.json` updated to register both new plugins; version bumped to 0.4.0.

### Spec completion
- This release completes the coded scope of `startup-skills-spec-v0.2.md` §7 (all 16 skills) and §8 (all 23 references). The v1.0 milestone in §12 is non-code work (evaluation harness, dogfooding, walkthrough examples).
- All forward references from earlier versions now resolve.

### Behavior changes
- `pmf-audit` refuses to authorize scaling or paid acquisition below the Sean Ellis 40% threshold.
- `pivot-decision` aggressively names sunk cost when evidence supports a pivot; also refuses to validate chronic pivoting (3+ pivots in 6 months) as productive work.
- `artifact-builder` refuses pre-signal pitch decks; produces deck with thin-section warnings otherwise.

## [0.3.0] — 2026-05-12

### Added
- `startup-skills-execution` plugin (4 skills): `rapid-experiments`, `mvp-architect`, `pricing-model`, `outreach-engine`.
- Reference library additions: `validation-techniques`, `landing-page-patterns`, `mvp-examples`, `pricing-frameworks`, `sales-funnel-math`, `tool-recommendations`.
- `.claude-plugin/marketplace.json` updated to register the new plugin; version bumped to 0.3.0.

### Behavior changes
- `rapid-experiments` refuses to design Fake Door tests for B2B-enterprise archetypes (trust damage).
- `mvp-architect` gates feature scoping behind a `rapid-experiments` behavioral signal — or requires explicit risk acknowledgment.
- `pricing-model` refuses B2B freemium pre-PMF and refuses to defer the pricing decision.
- `outreach-engine` refuses paid acquisition pre-PMF, sales hire pre-PMF, and press/PR-as-acquisition.

### Known limitations of v0.3
- PMF, pivot, and artifact plugins still pending — see roadmap in README. Forward-references to `pmf-scoring.md`, `pitch-deck-structure.md`, and `one-pager-structure.md` from current skills will resolve in v0.4.

## [0.2.0] — 2026-05-12

### Added
- `startup-skills-validation` plugin (3 skills): `problem-focus`, `discovery-coach` (PREPARE + DEBRIEF modes), `signal-audit`.
- Reference library additions: `mom-test-principles`, `evidence-weighting-matrix`, `false-signal-detection`, `email-templates`.
- `.claude-plugin/marketplace.json` updated to register the new plugin; version bumped to 0.2.0.

### Resolved
- v0.1 forward-references to `evidence-weighting-matrix.md`, `mom-test-principles.md`, and `false-signal-detection.md` now resolve to actual files. SKILL.md files in `startup-skills-core` and `startup-skills-discovery` that cited these references (notably via `bias-sentinel.md` and `state-document-template.md`) now have full backing.

### Known limitations of v0.2
- Execution, PMF, pivot, and artifact plugins still pending — see roadmap in README. Skills that forward-reference `pmf-scoring.md`, `validation-techniques.md`, `landing-page-patterns.md`, `mvp-examples.md`, `pricing-frameworks.md`, `sales-funnel-math.md`, `tool-recommendations.md`, `pitch-deck-structure.md`, and `one-pager-structure.md` will resolve when v0.3 and v0.4 ship.

## [0.1.0] — 2026-05-12

### Added
- Initial release.
- `startup-skills-core` plugin (2 skills): `orientation`, `founder-context`.
- `startup-skills-discovery` plugin (4 skills): `idea-genesis`, `market-intel`, `idea-pressure-test`, `cofounder-fit`.
- Reference library v1 (10 documents): `tone-and-stance`, `state-document-template`, `state-document-protocol`, `bias-sentinel`, `research-playbook`, `scoring-rubrics`, `tar-pit-detection`, `cofounder-frameworks`, `case-studies`, `external-resources`.
- Marketplace manifest (`.claude-plugin/marketplace.json`) and per-plugin manifests.
- `README.md` covering install paths, the thesis, the six personas, methodology, and roadmap.
- `LICENSE` (PolyForm Noncommercial 1.0.0).

### Known limitations of v0.1
- Validation, execution, PMF, pivot, and artifact plugins not yet shipped — see roadmap in README.
- Several v0.1 skills forward-reference references that arrive in v0.2 (`mom-test-principles`, `evidence-weighting-matrix`, `false-signal-detection`). Forward references are intentional and documented; the cited skills (`discovery-coach`, `signal-audit`, etc.) ship in v0.2.
