# State Document Template — STARTUP-STATE.md

`STARTUP-STATE.md` is the single source of truth for the founder's startup journey. Every skill reads it at activation and writes back at completion. It persists across sessions, across skills, and across pivots. The default location is project-local `.claude/startup-state.md`; override with the `STARTUP_STATE_PATH` environment variable. Skills must never maintain private state — context mush is the silent killer of long sessions, and this document is the antidote.

When `orientation` initializes the file, it copies the template below and populates whatever the user has already said. Subsequent skills update only the sections they own, bump the `_Last updated_` header, and append one line to the Session Log.

## Template (copy verbatim, then populate)

```markdown
# Startup State — [Name or "Unnamed"] — [Date initialized]
_Last updated: [ISO date] by [skill name]_
_Schema version: 2.0_

## Founder Profile
- Name (optional):
- Domain expertise:
- Technical ability: [can build self / needs developer / has team]
- Time horizon to MVP: [weeks]
- Resource reality: [solo nights+weekends / full-time savings runway / team + seed money]
- Startup archetype: [B2B SaaS / consumer / marketplace / devtools / hardware / services-to-product / content/media]
- Starting point: [no idea / problem observed / product built / customers + stalled]
- Risk tolerance (worst-case acceptable):

## One-Liner (versioned)
- v1 (date): ...
- v2 (date): ...
- Current: ...

## Current Hypothesis
"We believe [customer type] experiences [problem] when [situation] and will [behavior change] because [insight]."
- Riskiest assumption:
- Pre-committed kill threshold: [the falsifiable metric below which we stop]
- Pre-committed success criterion: [metric / by date]

## Target Customer (ICP)
- Role/type:
- Company/context:
- Current workaround:
- Signs of urgency observed:
- Where to find them (specific):
- Buyer vs. user distinction (if B2B):

## Evidence Log
| # | Date | Source | Quote/Observation | Type | Weight | Notes |
|---|------|--------|-------------------|------|--------|-------|

(Weight is from the Evidence Weighting Matrix in `references/evidence-weighting-matrix.md` — ships in v0.2 — running 0.0 attitudinal weak → 1.0 behavioral absolute. Until that reference exists, log `Weight` as a plain number and update once available.)

## PMF Running Score
- Sample size: [N targeted conversations]
- Behavioral evidence quality: [mean weight across log]
- Commitment signals: [count of 0.8+ entries]
- False-signal flags raised:
- Sean Ellis survey result (if applicable): X% Very Disappointed (N respondents)
- Current stage: [pre-signal / early signal / converging / clear / Sean Ellis confirmed]
- Gap to next stage:

## What We Know vs. What We've Assumed
| Item | Status | Source |
|------|--------|--------|

## Competitive Landscape
- Existing alternatives (with strengths/weaknesses from reviews):
- Why insufficient:
- Our specific insight (the why-now):
- Tar-pit checks performed: [Y/N + summary]

## Pricing
- Model: [subscription / usage / one-time / marketplace / services-to-product / freemium]
- Price point committed:
- First-paid-customer hypothesis: [who pays first, why, what they get]

## MVP / Experiment Plan
- Experiment type: [Fake Door / Wizard of Oz / Concierge / MVP build]
- What it tests:
- Success criterion:
- Kill criterion:
- Timeline: [weeks]
- Status:

## Team
- Solo / cofounder / team of N
- Specific gaps:
- Plan to fill:

## Active Experiments
- (any running tests with deploy date, success and kill criteria)

## Current Decision Point
[ ] Discovering idea
[ ] Pressure-testing idea
[ ] Sharpening problem
[ ] Talking to customers
[ ] Designing experiment
[ ] Running experiment
[ ] Building MVP
[ ] Acquiring first customers
[ ] Auditing PMF
[ ] Pivot evaluation

## Next Action — Human (48 hours)
-

## Next Action — Claude (parallel)
-

## Positioning (post-validation, schema v2)
- Competitive alternatives:
- Unique attributes:
- Best-fit customer (sharper than ICP):
- Market category:
- Strategic narrative (Raskin: BIG shift / winners-losers / promised land / obstacles / magic gifts):

## AI Economics (if AI-product, schema v2)
- Token cost per active user (last 30d): $
- LTV / inference-cost ratio: X (target ≥3)
- Margin per active user trend: improving / flat / declining
- Model dependency risk: low / medium / high (foundation lab could ship this natively)
- Vibe-vs-craft decision logged: vibe / craft / hybrid, date: YYYY-MM-DD

## Retention Cohorts (post-launch, schema v2)
- D1 retention: X%
- D7 retention: X%
- D28 retention: X%
- D90 retention: X%
- L7/L28 curve shape: smile / frown / flat
- Cohort retention by signup month (table)

## Opportunity Solution Tree (post-validation, schema v2)
- Outcome (single, measurable):
- Opportunities (children, in customer language):
  - [opportunity 1]
    - Solutions:
      - [solution]
        - Assumption tests: [test] (status: queued/running/done)
  - [opportunity 2]
  - ...

## Decision Journal (schema v2)
| # | Date | Decision | State | Confidence% | Alternatives | Key assumptions | Review date | Outcome |
|---|------|----------|-------|-------------|--------------|-----------------|-------------|---------|

## Kill Criteria Registry (schema v2)
| # | Criterion | Deadline | Status | Outcome |
|---|-----------|----------|--------|---------|

## Sycophancy Check (auto-logged every 5 turns, schema v2)
- Last contrarian pass: [date / turn]
- Recent disagreements logged:
- Recent unquantified praise count:

## Research Cache (deduplication, schema v2)
| Topic | Last researched | Source skill | Brief location |
|-------|-----------------|--------------|----------------|

## Session Log
- [date] [skill] — [one-sentence summary, decisions made, evidence added]
```

## Usage notes

- **Storage.** In Claude Code: project-local at `.claude/startup-state.md`. Override via `STARTUP_STATE_PATH`. In claude.ai: paste the contents into a Markdown artifact and copy-forward at the start of each new conversation.
- **Versioning.** Bump `_Schema version_` only when the schema (sections, columns) changes. Bump `_Last updated_` on every write.
- **One-Liner.** Versioned because the founder's positioning will mutate — preserve the history.
- **Evidence Log.** Append-only. Never edit prior entries. If a quote turns out to be misclassified, add a new row with the corrected weight and a Notes pointer to the original.
- **Session Log.** One line per skill invocation. Date, skill name, one-sentence summary. Keeps the audit trail without bloating the doc.
- **Forward references.** Some sections cite references that ship in later versions of Startup Skills. Skills shipping in v0.1 must not block on those — log what they can, leave fields blank until the relevant reference and skill exist.
- **Schema v2 (2026-05-13)**: added AI Economics, Retention Cohorts, Positioning, Opportunity Solution Tree, Decision Journal, Kill Criteria Registry, Sycophancy Check, Research Cache. Migration: existing v1 state docs are forward-compatible; new sections are populated by new skills as they fire. No data loss.

## Migration from v1.0 to v2.0

If your existing `STARTUP-STATE.md` is schema v1, it's forward-compatible — new sections populate when relevant skills fire. To manually migrate:

1. Update `_Schema version: 1.0_` to `_Schema version: 2.0_`.
2. Append the new sections from the template above (Positioning, AI Economics, Retention Cohorts, Opportunity Solution Tree, Decision Journal, Kill Criteria Registry, Sycophancy Check, Research Cache).
3. Leave fields empty until the relevant skill fires.

Schema v2 is the canonical version as of May 2026. All skills shipped in v2.0 of startup-skills assume schema v2 fields.
