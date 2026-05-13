# Startup Skills v0.2 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: superpowers:executing-plans. Steps use checkbox (`- [ ]`) syntax.

**Goal:** Ship v0.2 of Startup Skills — adds the `startup-skills-validation` plugin (3 skills) and 4 new references, per `startup-skills-spec-v0.2.md` §7.3 and §12.

**Architecture:** Adds one new plugin alongside the v0.1 plugins. References shipped here resolve the forward-references made by v0.1 SKILL.md files (especially `evidence-weighting-matrix.md`, cited from `bias-sentinel.md` and the state template).

**Tech Stack:** Same as v0.1 (markdown + JSON; no runtime).

**Spec sections referenced:**
- §7.3 Skill definitions (verbatim YAML + body content guidance for `problem-focus`, `discovery-coach`, `signal-audit`)
- §8 Reference library specs for `mom-test-principles.md`, `evidence-weighting-matrix.md`, `false-signal-detection.md`, `email-templates.md`
- §9 SKILL.md format conventions
- §10 marketplace.json (must be updated to add new plugin)

## File Structure (additions)

```
plugins/startup-skills-validation/
├── .claude-plugin/plugin.json
└── skills/
    ├── problem-focus/SKILL.md
    ├── discovery-coach/SKILL.md
    └── signal-audit/SKILL.md

references/
├── mom-test-principles.md
├── evidence-weighting-matrix.md
├── false-signal-detection.md
└── email-templates.md
```

Plus updates: `.claude-plugin/marketplace.json` (add validation plugin), `CHANGELOG.md` (v0.2.0 entry).

---

## Task 1: Validation plugin scaffolding + manifest update

- [ ] Create directory tree for `plugins/startup-skills-validation/`
- [ ] Write `plugins/startup-skills-validation/.claude-plugin/plugin.json`
- [ ] Add validation plugin entry to `.claude-plugin/marketplace.json` (preserving existing entries)
- [ ] Validate all 3 plugin.json files + marketplace.json parse

## Task 2: Reference — mom-test-principles.md

Per spec §8 (~400 words). The three Mom Test rules (ask about their life not your idea; ask about the past not the future; talk less, listen more). Bad question types (hypothetical, leading, feature-focused, yes/no). Good question types (past behavior, current workaround, time/money spent). The three bad data types (compliments, hypothetical fluff, wishlists). Attribute to Rob Fitzpatrick.

## Task 3: Reference — evidence-weighting-matrix.md

Per spec §8 (~300 words) and §6.4 / §7.3 Skill 8 examples. Full 0.0–1.0 matrix:
- 0.0: "Sounds cool, I'd use it" / "I'd pay $20/month" (hypothetical)
- 0.1: "You should add feature Y" (wishlist)
- 0.3–0.5: weaker behavioral (clicked, signed up)
- 0.6: "Last week I spent 4 hours on this in Excel" (behavioral, time-cost)
- 0.8: "Here, let me show you our internal workflow" (workflow displacement)
- 1.0: "Can I pay you $500 to do this for me manually?" (absolute behavioral)

Include the Dinnr counter-example (attitudinal validation → product failure). Attribute to Fitzpatrick (Mom Test).

## Task 4: Reference — false-signal-detection.md

Per spec §8 (~400 words). Seven patterns from §7.3 Skill 8: enthusiasm trap, small sample fallacy, launch day spike, network halo (talking to friends/colleagues), polite customer, feature request mirage, press/social attention. Each with symptoms, detection question, and response.

## Task 5: Reference — email-templates.md

Per spec §8 (~500 words). Three template patterns: warm intro, cold to specific role, cold to founder. Each ≤100 words. Constraints: 50–100 words; plain text; founder credibility (one line); specific value prop tied to their problem; single clear CTA (15–20 min call, not "let's connect"); no marketing language. Include explicit "what never to include" list.

## Task 6: Skill — problem-focus

Per spec §7.3 Skill 7. YAML frontmatter verbatim. SKILL.md body per §9.
Process highlights:
- Read state; pull idea + any prior ICP attempts.
- Recursive specificity questions (who specifically / situation / doing what / cost / current workaround).
- Map workflow in detail.
- Distinguish buyer vs user for B2B.
- Invoke `market-intel` to validate ICP exists online; refuse to proceed if can't.
- Extract customer language verbatim.
- Formulate hypothesis in standard Lean Startup format.
- Identify single riskiest assumption.
- Pre-commit success and kill criteria.
- Bias sentinel: false consensus, narrow-well failure.
- Surface PG's narrow-well metaphor.
- Recommend `discovery-coach` (PREPARE) or `rapid-experiments` (v0.3).

References loaded: state-document-protocol, bias-sentinel, research-playbook, case-studies, external-resources.

## Task 7: Skill — discovery-coach

Per spec §7.3 Skill 8. YAML frontmatter verbatim. PREPARE + DEBRIEF modes.

**PREPARE mode:**
- Generate custom 12–18 question script per `mom-test-principles.md`.
- NEVER include hypothetical/leading questions; ALWAYS open-ended past-behavior.
- Outreach approach (warm + cold) per `email-templates.md`.
- Role-play option.
- Identify 3 bad questions the founder is likely to ask.
- Refuse to include "pitch the idea" step.
- Set behavioral success criterion before the call.

**DEBRIEF mode:**
- Founder dumps everything; classify each statement via `evidence-weighting-matrix.md`.
- Apply `false-signal-detection.md` seven patterns.
- Test for Dinnr-style false-positive trap.
- Update Evidence Log + PMF running score.
- Refine hypothesis (persevere/pivot).
- Bias sentinel: confirmation bias, polite customer.
- Recommend next: more interviews if N<20; `signal-audit` if 5+ logged; `rapid-experiments` if signal mixed.

References loaded: state-document-protocol, bias-sentinel, mom-test-principles, evidence-weighting-matrix, false-signal-detection, email-templates, external-resources.

Artifacts on request: custom interview script; debrief synthesis memo; "lessons across N interviews" pattern doc.

## Task 8: Skill — signal-audit

Per spec §7.3 Skill 9. YAML frontmatter verbatim.

Process:
- Read Evidence Log + current PMF score.
- For each new evidence item: classify and weight via `evidence-weighting-matrix.md`.
- Run `false-signal-detection.md` on entire log.
- Compute PMF dimensions: sample size adequacy (20+ threshold), behavioral evidence quality, commitment density, workflow displacement evidence, Sean Ellis stage (note: full implementation in v0.4 `pmf-audit`; this skill notes when to escalate to it).
- Map to PMF stage (pre-signal / early signal / converging / Sean Ellis confirmed).
- If pre-signal and founder asks about building/scaling, refuse — state what evidence would change that.
- Surface the gap and fastest path to close it.
- Pre-mortem prompt at full audit ("assume this fails in 6 months — most likely cause?").
- Bias sentinel: uncanny valley, confirmation bias, sunk cost.
- Recommend next: `discovery-coach` for more interviews; `rapid-experiments` for behavioral test; `pmf-audit` (v0.4); `pivot-decision` (v0.4) if pre-signal for 3+ months.

References loaded: state-document-protocol, bias-sentinel, evidence-weighting-matrix, false-signal-detection, external-resources. (Note: `pmf-scoring.md` ships in v0.4 — forward reference acceptable per state-document-protocol convention.)

## Task 9: CHANGELOG.md v0.2.0 entry

Add a `[0.2.0]` section above `[0.1.0]`. Date 2026-05-12. List the 3 new skills, 4 new references, the new plugin, marketplace.json update, and note that the v0.1 forward references to `evidence-weighting-matrix.md`, `mom-test-principles.md`, `false-signal-detection.md` are now resolved.

## Task 10: Smoke test

- All 4 JSON manifests parse (now 3 plugin.json + 1 marketplace.json).
- Every skill path listed in marketplace.json exists.
- All 9 SKILL.md files under 250 lines.
- All 14 reference files exist (10 from v0.1 + 4 new).
- Every `references/<file>.md` cited in any SKILL.md resolves to an actual file.

## Self-review check

- [x] All 3 v0.2 skills from spec §7.3 mapped (Tasks 6–8).
- [x] All 4 v0.2 references from spec §12 mapped (Tasks 2–5).
- [x] Marketplace.json gets the new plugin entry.
- [x] CHANGELOG updated.
- [x] Smoke tests at end.
