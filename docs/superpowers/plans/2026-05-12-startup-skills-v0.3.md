# Startup Skills v0.3 Implementation Plan

**Goal:** Ship v0.3 — adds the `startup-skills-execution` plugin (4 skills) and 6 references per spec §7.4 and §12.

**Architecture:** Same pattern as v0.1 / v0.2. Adds one new plugin alongside existing ones.

## File Structure (additions)

```
plugins/startup-skills-execution/
├── .claude-plugin/plugin.json
└── skills/
    ├── rapid-experiments/SKILL.md
    ├── mvp-architect/SKILL.md
    ├── pricing-model/SKILL.md
    └── outreach-engine/SKILL.md

references/
├── validation-techniques.md
├── landing-page-patterns.md
├── mvp-examples.md
├── pricing-frameworks.md
├── sales-funnel-math.md
└── tool-recommendations.md
```

Plus updates: `.claude-plugin/marketplace.json` (add execution plugin, bump to 0.3.0), `CHANGELOG.md` (v0.3.0 entry).

## Tasks

1. **Plugin scaffolding + marketplace update.** Create directory tree, plugin.json, register in marketplace.json, bump marketplace version to 0.3.0.
2. **References (6):**
   - `validation-techniques.md` — menu of methods (Fake Door, Wizard of Oz, Concierge, pre-orders, etc.) per spec §8 ~500 words.
   - `landing-page-patterns.md` — Fake Door / signup page patterns per spec §8 ~300 words.
   - `mvp-examples.md` — canonical MVPs (Airbnb, Twitch, Stripe, DoorDash, Dropbox, Buffer) per spec §8 ~600 words.
   - `pricing-frameworks.md` — charge from day one, free trial vs money-back, freemium pitfalls per spec §8 ~400 words.
   - `sales-funnel-math.md` — funnel math, conversion rates per spec §8 ~300 words.
   - `tool-recommendations.md` — outreach/CRM/survey/landing/email/analytics/payment/CMS tools per spec §8 ~500 words.
3. **Skills (4):**
   - `rapid-experiments` per §7.4 Skill 10 — Fake Door / Wizard of Oz / Concierge by archetype; refuses B2B-enterprise Fake Door; falsification pre-commitments.
   - `mvp-architect` per §7.4 Skill 11 — gate-check on `rapid-experiments`; ruthless feature cuts; 2–6 week hard deadline; hair-on-fire early adopter; Reference Class Forecasting.
   - `pricing-model` per §7.4 Skill 12 — charge from day one; refuse B2B freemium; refuse free trials when money-back works.
   - `outreach-engine` per §7.4 Skill 13 — prospect list construction; YC email framework; funnel math backwards from goal; Continuous Launch; refuses paid acquisition pre-PMF.
4. **CHANGELOG update.**
5. **Smoke tests** — 5 JSON manifests, 13 SKILL.md paths, 20 references.

## Self-review

- All 4 v0.3 skills mapped.
- All 6 v0.3 references mapped.
- Marketplace gets the new plugin.
- Forward references to `pmf-scoring.md`, `pitch-deck-structure.md`, `one-pager-structure.md` from v0.3 skills are acceptable (those files ship in v0.4).
