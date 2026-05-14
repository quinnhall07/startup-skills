# Changelog

All notable changes to Startup Skills are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.5.0] — 2026-05-13

### Added — 5 new skills

- `continuous-discovery` — Teresa Torres's weekly Opportunity Solution Tree cadence post-validation. Refuses to let founders stop interviewing after launch.
- `ai-mvp-stack-selection` — Lovable / Bolt / Cursor / Claude Code / Replit Agent decision matrix. Enforces vibe-vs-craft gate; bans vibe-coding for regulated / payments / auth / PII surfaces.
- `positioning-narrative` — April Dunford 10-step positioning + Andy Raskin 5-act strategic narrative. Refuses pre-signal positioning ("theatre").
- `cofounder-decision` — distinct from `cofounder-fit`: handles active cofounder conflict, breakup, mid-flight equity disputes. Refuses to help one founder convince the other without both present.
- `founder-resilience` — decision-quality-under-stress circuit-breaker. Annie Duke's 24-hour rule; cofounder-alignment one-liner; "you are not your company" reframe.

### Added — 10 new references

- `retention-metrics.md` — cohort retention by archetype, Casey Winters flattening rule, Andrew Chen power user curve, PMF Treadmill (Reforge), token-cost-aware retention, Magic case study.
- `growth-loops.md` — Brian Balfour Four Fits, viral coefficient, NRR, CAC payback, David Skok unit economics, Bessemer benchmarks.
- `continuous-discovery-patterns.md` — Torres Opportunity Solution Tree, story-based interviewing, Product Trio, 5 assumption categories, I-Corps 100-interview standard.
- `distribution-by-archetype.md` — devtools / B2B SMB / B2B enterprise / consumer / marketplace / hardware / AI agent product / community-led GTM motions.
- `founder-resilience-protocols.md` — sustainable-pace check, decision fatigue protocol, cofounder alignment one-liner, loneliness diagnostic.
- `ai-era-anti-patterns.md` — 8 AI-era founder traps (wrapper without distribution, token-cost denial, model-market-fit vs PMF, vibe-coding regulated surfaces, cold-email blasting post-Feb 2024, synthetic-user validation, etc.).
- `positioning-frameworks.md` — April Dunford 10-step + Andy Raskin 5-act, anchor examples (Superhuman, Drift, Stripe, Linear).
- `jtbd-protocols.md` — two schools of JTBD (Ulwick ODI / Klement progress), Bob Moesta's 47-min Switch Interview, Four Forces of Progress.
- `decision-journal-template.md` — Annie Duke kill criteria + monkeys-vs-pedestals, Klein pre-mortem, Kahneman MAP + Independence rule, IDF Tenth Man rule, Tetlock calibration, sycophancy circuit-breaker.
- `aggressive-consultation-archetype.md` — 12 calibrated behaviors, cost-of-decision gate, institutional devil's advocacy patterns, AI-sycophancy countermeasures.

### Upgraded — 9 existing references

- `bias-sentinel.md` — Annie Duke (kill criteria, monkeys-vs-pedestals, resulting), Tetlock calibration + Bayesian updating, Kahneman MAP + Independence rule, Tenth Man rule, forbidden-phrases table, steelman-first ritual, **sycophancy circuit-breaker** (every 5 turns).
- `tone-and-stance.md` — 12 calibrated behaviors, cost-of-decision gate, founder-state modulates delivery never substance.
- `pmf-scoring.md` — Brian Balfour Four Fits, Casey Winters retention-curve rule, Andrew Chen power user curve, PMF Treadmill, Andreessen observables operationalized, anti-PMF signals table, AI-product token-cost-aware tests, First Round Levels of PMF.
- `pricing-frameworks.md` — Ramanujam Monetizing Innovation + Minivation trap, Van Westendorp PSM, AI pricing primitives (per-seat erosion, hybrid, outcome-based), B2B freemium gates, anti-discount rule, tier ratios.
- `external-resources.md` — ~30 new canonical sources (Torres, Moesta, Dunford, Raskin, Duke, Tetlock, Balfour, Chen, Winters, Ramanujam, NFX, Skok, Bessemer, Garry Tan, Founder Mode, Lightcone).
- `tool-recommendations.md` — 2026 pricing, AI build stack section (Lovable/Bolt/Cursor/Claude Code/Replit Agent), cold email infra post-Feb 2024, LinkedIn outbound, signal-based outbound.
- `sales-funnel-math.md` — archetype-segmented funnels (B2B SMB / enterprise / B2C / marketplace / AI), deliverability collapse, LinkedIn comment-first math.
- `validation-techniques.md` — source-quality + deposit-size weight modifiers, vibe-coded MVP + AI-WoZ techniques, vibe-vs-craft column.
- `state-document-template.md` — **schema v2** with AI Economics, Retention Cohorts, Positioning, Opportunity Solution Tree, Decision Journal, Kill Criteria Registry, Sycophancy Check, Research Cache. v1 forward-compatible.

### Skill engineering — all 21 skills

- **TRIGGER/SKIP block descriptions** on every skill (mirroring Anthropic's `claude-api` skill format) for materially better trigger reliability.
- **HARD-GATE blocks** on the 6 decision-gate skills (signal-audit, mvp-architect, outreach-engine, pmf-audit, pricing-model, pivot-decision) — refuses ungrounded decisions, lists specific evidence needed.
- **Red-flag tables** on every discipline skill — preempts specific founder rationalizations.
- **Stripped forward-reference debt** — no more `v0.X / until then / if available` caveats. Everything ships.

### Behavior changes

- `signal-audit` — now the load-bearing freeze gate; refuses scaling/hiring/raising/paid-acquisition unless evidence supports.
- `pricing-model` — Ramanujam WTP-before-build reframing; explicit AI outcome-based pricing path.
- `outreach-engine` — modern deliverability stack (SPF/DKIM/DMARC + secondary domains + warmup) mandatory before sending; LinkedIn comment-first; signal-based outbound; AI Overviews SEO awareness.
- `mvp-architect` — formal HARD-GATE; explicit pre-validation risk-accept log format.
- `pmf-audit` — retention curve + L7/L28 check mandatory alongside Sean Ellis; AI-PMF specifics including model-market-fit failure mode.
- `pivot-decision` — explicit pivot-candidate generation formula; Annie Duke "would you start today?" + monkeys-vs-pedestals.
- `bias-sentinel` (across all skills) — sycophancy circuit-breaker enforced every 5 turns.

### Methodology additions

Beyond v0.4's canon (PG, YC, Fitzpatrick, Ries, Blank, Ellis, Vohra, Kahneman, Klein, Andreessen, Rachitsky), v0.5 adds:

- **Customer discovery**: Teresa Torres (Continuous Discovery Habits), Bob Moesta (Demand-Side Sales 101 / Switch Interview), Indi Young (Listening Deeply), Alan Klement (When Coffee and Kale Compete), Tony Ulwick (Jobs to Be Done / ODI).
- **PMF + growth**: Brian Balfour (Four Fits), Casey Winters (retention), Andrew Chen (Cold Start Problem / Power User Curve), Reforge (PMF Collapse), First Round (Levels of PMF).
- **Pricing**: Madhavan Ramanujam (Monetizing Innovation), Patrick Campbell (Van Westendorp PSM), Sierra (outcome-based AI), Bessemer (Cloud benchmarks).
- **Positioning**: April Dunford (Obviously Awesome), Andy Raskin (strategic narrative), Sequoia business plan template.
- **Decision quality**: Annie Duke (Thinking in Bets / Quit), Phil Tetlock (Superforecasting), Kahneman/Sibony/Sunstein (Noise), Shane Parrish (Farnam Street decision journal).
- **YC modern**: Garry Tan (earnestness / first-principles thinkers), Founder Mode (PG 2024), Dalton & Michael 2024-2025 podcast, Lightcone Podcast, Tom Blomfield (B2B metrics), Diana Hu (agent infrastructure), Pete Koomen (enterprise sales).
- **AI-era**: Andrew Chen (Revenge of GPT Wrappers), Sequoia AI in 2026, Karpathy on vibe coding, Stack Overflow + MIT Sloan on AI tech debt, Proofpoint on Feb 2024 bulk-sender rules.
- **Aggressive consultation**: Kim Scott (Radical Candor), Crucial Conversations, Marshall Rosenberg (NVC), Gottman (criticism vs. contempt), Catholic / IDF Tenth Man / CIA Tradecraft Primer institutional devil's advocacy.

### Spec docs

- `docs/plans/2026-05-13-startup-skills-v2-improvement-plan.md` — full v2 improvement plan (~14k words) covering audit findings, methodology refresh, new skills, architectural changes, eval harness, and 14-week phased roadmap.

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
