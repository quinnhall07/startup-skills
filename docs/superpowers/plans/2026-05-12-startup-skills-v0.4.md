# Startup Skills v0.4 Implementation Plan

**Goal:** Finish the spec's coded scope. Adds 2 new plugins: `startup-skills-pmf-and-pivot` (2 skills) and `startup-skills-artifacts` (1 skill). Plus 3 references.

**Architecture:** Two new plugins. Final manifest update bumps marketplace to 0.4.0.

## File Structure (additions)

```
plugins/startup-skills-pmf-and-pivot/
├── .claude-plugin/plugin.json
└── skills/
    ├── pmf-audit/SKILL.md
    └── pivot-decision/SKILL.md

plugins/startup-skills-artifacts/
├── .claude-plugin/plugin.json
└── skills/
    └── artifact-builder/SKILL.md

references/
├── pmf-scoring.md
├── pitch-deck-structure.md
└── one-pager-structure.md
```

Plus updates: `.claude-plugin/marketplace.json` (add 2 plugins, bump to 0.4.0), `CHANGELOG.md` (v0.4.0 entry), README.md (status section update to reflect complete spec coverage).

## Tasks

1. **Plugin scaffolding + marketplace update** — 2 plugin dirs, 2 plugin.json, marketplace.json update.
2. **References (3):**
   - `pmf-scoring.md` (~500 words) — Sean Ellis 40% Rule full implementation; Superhuman blueprint (HXC, polarity, fence-sitter, 50/50); Andreessen qualitative complement.
   - `pitch-deck-structure.md` (~400 words) — YC 10–12 slide format; what never to include.
   - `one-pager-structure.md` (~250 words) — async one-page format.
3. **Skills (3):**
   - `pmf-audit` per §7.5 Skill 14 — Sean Ellis 40% Rule; HXC segmentation; refuses scaling pre-40%; Andreessen complement.
   - `pivot-decision` per §7.5 Skill 15 — Dalton's opportunity cost; Klein pre-mortem; aggressive sunk-cost antidotes; 3–5 candidate pivots if recommended.
   - `artifact-builder` per §7.6 Skill 16 — pitch deck (REFUSES if pre-signal); landing page; one-pager; investor email; demo day script.
4. **CHANGELOG + README update + smoke tests + commit.**
