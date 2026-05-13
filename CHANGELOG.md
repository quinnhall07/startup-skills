# Changelog

All notable changes to Startup Skills are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

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
