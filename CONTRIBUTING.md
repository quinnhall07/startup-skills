# Contributing

Thanks for considering a contribution. The system is small, opinionated, and load-bearing for founders — keep that bar in mind.

## Reporting issues

Open a GitHub issue. Include:
- The skill name (e.g. `discovery-coach`) or reference name (e.g. `bias-sentinel.md`)
- What you said to Claude
- What the system did vs. what you expected
- Your install path (Claude Code / claude.ai / other)

For bias-sentinel false positives, paste the user message that fired the bias and the bias name.

## Pull requests

**Hard requirements:**
- Skills stay under 250 lines.
- References cite named sources inline (Mom Test, YC partner, Lenny's Newsletter, etc.) — no unsupported claims.
- YAML frontmatter on every SKILL.md uses the `TRIGGER when:` / `SKIP:` block format (see existing skills for examples).
- Decision-gate skills carry a `## HARD-GATE` block near the top.
- No forward-reference debt (`if available`, `until then`, `ships in vN`) — everything must resolve at PR time.

**Validation:**
- Run `claude plugin validate plugins/startup-skills` locally before submitting.
- Verify every `${CLAUDE_PLUGIN_ROOT}/references/<file>.md` you cite actually exists.

**Bump:**
- `plugins/startup-skills/.claude-plugin/plugin.json` version.
- `CHANGELOG.md` entry with the version + changes.

**Tone:**
- Aggressive Epistemic Auditor voice (see `references/tone-and-stance.md` + `references/aggressive-consultation-archetype.md`). Direct, willing to wound, never cruel.
- No marketing words ("leverage," "transform," "unleash"). Direct verbs.
- Refusal logic must be crisp, with explicit rationale and the evidence that would change the answer.

## What we will reject

- Pre-PMF skills that validate bias-amplifying behaviors (e.g., a skill that helps founders justify staying with a tar-pit idea).
- Methodology without named attribution.
- Skills that produce artifacts without thin-section warnings when state is sparse.
- Sycophantic phrasing.
- Forward-reference debt.

## Design rationale

Before proposing a new skill or reference, read:
- [`docs/specs/2026-05-12-v0.4-design-spec.md`](./docs/specs/2026-05-12-v0.4-design-spec.md) — original v0.4 design (historical).
- [`docs/plans/2026-05-13-startup-skills-v2-improvement-plan.md`](./docs/plans/2026-05-13-startup-skills-v2-improvement-plan.md) — v0.5 design rationale (current).

Open an issue for discussion before opening a non-trivial PR.

## License

By contributing, you agree your contribution is licensed under PolyForm Noncommercial 1.0.0 (matching the project license). Commercial sub-licensing rights remain with the maintainer.
