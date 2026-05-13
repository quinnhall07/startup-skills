# Startup Skills v0.1 Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Ship v0.1 of Startup Skills — a Claude Code plugin marketplace with two plugins (Core + Discovery), 6 skills, 10 reference documents, and full repo scaffolding per the spec at `startup-skills-spec-v0.2.md`.

**Architecture:** A GitHub repo structured as a Claude Code plugin marketplace. Six skills across two plugins call shared reference documents from a top-level `references/` directory. State persists in a project-local `.claude/startup-state.md` written by every skill. Content is markdown; configuration is JSON.

**Tech Stack:** Markdown (SKILL.md, references, README, CHANGELOG), JSON (marketplace.json, plugin.json), plain-text LICENSE. No runtime/build system.

**Decisions from clarifying questions:**
- Scope: v0.1 only (6 skills, 10 references, Core + Discovery plugins)
- Maintainer GitHub username: `quinnhall07`
- State doc default location: project-local `.claude/startup-state.md`

**Spec sections referenced:**
- §6.3 State document schema → `references/state-document-template.md`
- §6.4 Bias sentinel trigger table → `references/bias-sentinel.md`
- §7.1–§7.2 Skill definitions (verbatim YAML + body content guidance for 6 v0.1 skills)
- §8 Reference library specs (content guidance for the 10 v0.1 references)
- §9 SKILL.md format conventions
- §10 Repository structure, marketplace.json, plugin.json
- §11 Installation instructions for README
- §14 Build order

---

## File Structure

```
startup-skills/
├── README.md
├── LICENSE                                              # PolyForm Noncommercial 1.0.0
├── CHANGELOG.md
├── .claude-plugin/
│   └── marketplace.json
├── plugins/
│   ├── startup-skills-core/
│   │   ├── .claude-plugin/plugin.json
│   │   └── skills/
│   │       ├── orientation/SKILL.md
│   │       └── founder-context/SKILL.md
│   └── startup-skills-discovery/
│       ├── .claude-plugin/plugin.json
│       └── skills/
│           ├── idea-genesis/SKILL.md
│           ├── market-intel/SKILL.md
│           ├── idea-pressure-test/SKILL.md
│           └── cofounder-fit/SKILL.md
└── references/
    ├── tone-and-stance.md
    ├── state-document-template.md
    ├── state-document-protocol.md
    ├── bias-sentinel.md
    ├── research-playbook.md
    ├── scoring-rubrics.md
    ├── tar-pit-detection.md
    ├── cofounder-frameworks.md
    ├── case-studies.md
    └── external-resources.md
```

Existing repo contents (`Skills/`, `YC Startup School Resources/`, `startup-skills-spec-v0.2.md`) are left untouched.

---

## Conventions for every content task

When the plan says "Generate per spec §X," the implementer:
1. Reads the spec section.
2. Writes the file content as **original synthesis** of the named sources (no quotation, attribution preserved). High information density. Concise.
3. For SKILL.md files: uses YAML frontmatter from §7 **verbatim**, then expands the body to match the §9 SKILL.md format (sections: title, one-paragraph statement, "When to Activate", "Required Reading", "State Document Protocol", "Process", "Outputs", "Anti-Patterns Prevented", "Recommended Next Skills", "Tone"). Keep each SKILL.md under 250 lines.
4. For references: target the word count specified in §8 (±20%). Each must cite named sources inline.
5. Uses absolute paths in tool calls (Windows: `C:\Users\danie\Documents\GitHub\startupskills\...`).
6. Does NOT auto-commit; commits happen at the end of each task as a single git command.

---

## Task 1: Repository scaffolding (directories + LICENSE + CHANGELOG)

**Files:**
- Create: `LICENSE` (PolyForm Noncommercial 1.0.0)
- Create: `CHANGELOG.md`
- Create: directory tree per File Structure above

- [ ] **Step 1: Create directory tree**

Run (PowerShell):
```
New-Item -ItemType Directory -Force -Path .claude-plugin, plugins\startup-skills-core\.claude-plugin, plugins\startup-skills-core\skills\orientation, plugins\startup-skills-core\skills\founder-context, plugins\startup-skills-discovery\.claude-plugin, plugins\startup-skills-discovery\skills\idea-genesis, plugins\startup-skills-discovery\skills\market-intel, plugins\startup-skills-discovery\skills\idea-pressure-test, plugins\startup-skills-discovery\skills\cofounder-fit, references | Out-Null
```

- [ ] **Step 2: Write LICENSE**

Write the full text of PolyForm Noncommercial License 1.0.0 to `LICENSE`. Source: https://polyformproject.org/licenses/noncommercial/1.0.0/. Replace `<licensor>` with `Quinn Hall`. License text is canonical and must be verbatim from the official source — do not paraphrase.

- [ ] **Step 3: Write CHANGELOG.md**

Content:
```markdown
# Changelog

All notable changes to Startup Skills are documented here. Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versioning follows [SemVer](https://semver.org/).

## [0.1.0] — 2026-05-12

### Added
- Initial release.
- `startup-skills-core` plugin (2 skills): `orientation`, `founder-context`.
- `startup-skills-discovery` plugin (4 skills): `idea-genesis`, `market-intel`, `idea-pressure-test`, `cofounder-fit`.
- Reference library v1 (10 documents): tone-and-stance, state-document-template, state-document-protocol, bias-sentinel, research-playbook, scoring-rubrics, tar-pit-detection, cofounder-frameworks, case-studies, external-resources.
- Marketplace and plugin manifests.
- README, LICENSE (PolyForm Noncommercial 1.0.0).
```

- [ ] **Step 4: Commit**

```
git add LICENSE CHANGELOG.md .claude-plugin plugins references docs
git commit -m "scaffold: directories, LICENSE, CHANGELOG for v0.1"
```

---

## Task 2: Marketplace and plugin manifests

**Files:**
- Create: `.claude-plugin/marketplace.json`
- Create: `plugins/startup-skills-core/.claude-plugin/plugin.json`
- Create: `plugins/startup-skills-discovery/.claude-plugin/plugin.json`

- [ ] **Step 1: Write `.claude-plugin/marketplace.json`**

Use the JSON from spec §10.1 verbatim, but list ONLY the two v0.1 plugins (`startup-skills-core` and `startup-skills-discovery`). Replace `[maintainer GitHub username]` with `quinnhall07`. Version `0.1.0`. Homepage `https://github.com/quinnhall07/startup-skills`.

Content:
```json
{
  "name": "startup-skills",
  "displayName": "Startup Skills",
  "description": "An Aggressive Epistemic Auditor for founders. Idea to PMF, with Y Combinator methodology, the Mom Test, the Lean Startup, and behavioral economics applied as structural overrides.",
  "version": "0.1.0",
  "author": "quinnhall07",
  "homepage": "https://github.com/quinnhall07/startup-skills",
  "license": "PolyForm-Noncommercial-1.0.0",
  "plugins": [
    {
      "name": "startup-skills-core",
      "source": "./plugins/startup-skills-core",
      "description": "Essential. Orientation + founder context. Required.",
      "skills": [
        "./plugins/startup-skills-core/skills/orientation",
        "./plugins/startup-skills-core/skills/founder-context"
      ],
      "strict": false
    },
    {
      "name": "startup-skills-discovery",
      "source": "./plugins/startup-skills-discovery",
      "description": "Find or pressure-test an idea. Includes market intelligence and cofounder fit.",
      "skills": [
        "./plugins/startup-skills-discovery/skills/idea-genesis",
        "./plugins/startup-skills-discovery/skills/market-intel",
        "./plugins/startup-skills-discovery/skills/idea-pressure-test",
        "./plugins/startup-skills-discovery/skills/cofounder-fit"
      ],
      "strict": false
    }
  ]
}
```

- [ ] **Step 2: Write `plugins/startup-skills-core/.claude-plugin/plugin.json`**

Content:
```json
{
  "name": "startup-skills-core",
  "version": "0.1.0",
  "description": "Essential entry-point skills for the Startup Skills system. Required.",
  "author": "quinnhall07",
  "license": "PolyForm-Noncommercial-1.0.0"
}
```

- [ ] **Step 3: Write `plugins/startup-skills-discovery/.claude-plugin/plugin.json`**

Content:
```json
{
  "name": "startup-skills-discovery",
  "version": "0.1.0",
  "description": "Discovery skills: idea generation, market intelligence, idea pressure-testing, cofounder fit.",
  "author": "quinnhall07",
  "license": "PolyForm-Noncommercial-1.0.0"
}
```

- [ ] **Step 4: Validate JSON**

Run (PowerShell):
```
Get-Content .claude-plugin\marketplace.json | ConvertFrom-Json | Out-Null
Get-Content plugins\startup-skills-core\.claude-plugin\plugin.json | ConvertFrom-Json | Out-Null
Get-Content plugins\startup-skills-discovery\.claude-plugin\plugin.json | ConvertFrom-Json | Out-Null
```
Expected: no errors.

- [ ] **Step 5: Commit**

```
git add .claude-plugin plugins/startup-skills-core/.claude-plugin plugins/startup-skills-discovery/.claude-plugin
git commit -m "config: marketplace.json and v0.1 plugin manifests"
```

---

## Task 3: Reference — tone-and-stance.md

**Files:**
- Create: `references/tone-and-stance.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "tone-and-stance.md", ~300 words). The Aggressive Epistemic Auditor stance per §4.3. Voice: direct, witty, no padding. Lists what the system does (calls things what they are, names biases, refuses validation of ungrounded decisions) and doesn't do (cruel, sarcastic at the founder, lecturing). Include 3–4 sample exchanges showing tone in action — short founder turn, sharp Claude response.

- [ ] **Step 2: Commit**

```
git add references/tone-and-stance.md
git commit -m "ref: tone-and-stance — Aggressive Epistemic Auditor voice"
```

---

## Task 4: Reference — state-document-template.md

**Files:**
- Create: `references/state-document-template.md`

- [ ] **Step 1: Write the reference**

Generate per spec §6.3 (full STARTUP-STATE.md schema) and §8 (entry "state-document-template.md", ~500 words). Reproduce the full markdown template from §6.3 verbatim as a fenced code block. Above the template: 2–3 sentence preamble explaining purpose and that every skill reads it at activation and writes back at completion. Below the template: short usage notes — where it lives by default (`.claude/startup-state.md`), how to override path, that the Evidence Log uses the weighting matrix in `evidence-weighting-matrix.md` (forward-referenced — file will exist in v0.2 but skills can still cite).

- [ ] **Step 2: Commit**

```
git add references/state-document-template.md
git commit -m "ref: state-document-template — STARTUP-STATE.md schema"
```

---

## Task 5: Reference — state-document-protocol.md

**Files:**
- Create: `references/state-document-protocol.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "state-document-protocol.md", ~200 words) and §6.3 (read/write protocol section).

Required content:
- Read `STARTUP-STATE.md` at activation. If absent, hand off to `orientation`.
- Update relevant sections at completion. Update header timestamp + skill name.
- Append a one-line entry to the Session Log: `- [YYYY-MM-DD] <skill-name> — <one-sentence summary>`.
- Bump `_Last updated` field; do not bump `_Schema version_` unless schema actually changes.
- Default path `.claude/startup-state.md` (project-local). Override via `STARTUP_STATE_PATH` env var.

- [ ] **Step 2: Commit**

```
git add references/state-document-protocol.md
git commit -m "ref: state-document-protocol — read/write rules for every skill"
```

---

## Task 6: Reference — bias-sentinel.md

**Files:**
- Create: `references/bias-sentinel.md`

- [ ] **Step 1: Write the reference**

Generate per spec §6.4 + §8 (entry "bias-sentinel.md", ~600 words).

Required content:
1. Brief opening paragraph: this is the enforcement file loaded by every evidence-handling skill. Skim it. Apply briefly. Do not lecture.
2. Reproduce the full trigger table from §6.4 (10 biases × Trigger phrases × Response) verbatim.
3. One short paragraph per bias (~30–50 words) explaining the bias and attributing it (Kahneman/Tversky for inside view, optimism, anchoring; Lovallo for reference class; Klein for pre-mortem support; Fitzpatrick for polite-customer; Graham for schlep blindness / tar pit).
4. Section "Structural overrides" listing the four per §6.4: Evidence Weighting Matrix (forward-ref to evidence-weighting-matrix.md), Pre-Mortem (Klein), Reference Class Forecasting (Lovallo/Kahneman), Falsification Pre-commitments.
5. Sample exchange demonstrating "name the bias briefly, move on" pattern.

- [ ] **Step 2: Commit**

```
git add references/bias-sentinel.md
git commit -m "ref: bias-sentinel — bias trigger table and structural overrides"
```

---

## Task 7: Reference — research-playbook.md

**Files:**
- Create: `references/research-playbook.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "research-playbook.md", ~400 words). Cover:
- Six search categories from §7.2 market-intel (forum pain, review complaints, job posting analysis, failed-startup retrospectives, funding activity, community language mapping) plus adjacent/wedge entry points.
- Specific query templates with `{placeholder}` variables (e.g., `site:reddit.com {domain} frustration`, `{competitor} G2 reviews bad`, `hiring {role} site:linkedin.com`).
- Source trust ladder (G2/Capterra = signal; Reddit = unfiltered language; Crunchbase = structured data; press releases = noise; failed-startup post-mortems = high signal).
- Guidance on using `WebFetch` to extract substance from 2–3 most signal-rich pages, not just snippets.
- Note that TAM math is not a substitute for behavioral evidence.

- [ ] **Step 2: Commit**

```
git add references/research-playbook.md
git commit -m "ref: research-playbook — search categories, query templates, source trust"
```

---

## Task 8: Reference — scoring-rubrics.md

**Files:**
- Create: `references/scoring-rubrics.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "scoring-rubrics.md", ~500 words) and §7.2 idea-pressure-test scoring sections.

Required content:
- **Dalton's 4-criteria rubric**: Market size, Founder-market fit, Ease of getting started, Early market feedback. For each: 1–10 scale with anchor descriptions for 3, 5, 7, 10. Attribute to Dalton Caldwell.
- **YC 10-question framework**: full list from §7.2 (founder-market fit, market size now, market growth, acuteness, competition existence, right team, genuinely had this problem, was it your idea first, when did you have the idea, fertile idea space). Brief gloss per question.
- **Composite recommendation rules**:
  - FMF ≥ 7 AND ≥ 2 other dimensions ≥ 7 → "Worth pursuing. Single gap to close."
  - Tar pit detected → "Tar pit. Why. Move on."
  - FMF < 5 → "No founder-market fit. Find cofounder or change ideas."
  - Otherwise → "Mixed. 2–3 things to learn."

- [ ] **Step 2: Commit**

```
git add references/scoring-rubrics.md
git commit -m "ref: scoring-rubrics — Dalton 4-criteria + YC 10-question framework"
```

---

## Task 9: Reference — tar-pit-detection.md

**Files:**
- Create: `references/tar-pit-detection.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "tar-pit-detection.md", ~400 words) and §7.2 idea-pressure-test.

Required content:
- Definition: a tar pit is an idea that seems obvious and easy but consistently fails because the underlying market structure is hostile (acquisition costs, retention churn, monetization gaps, network effects working against you).
- The canonical tar pit list with one-paragraph "why it fails" per entry: meet-up-with-friends apps, local event discovery, unified communication inbox, social planning, generic "Uberize X" for fragmented services. Reference Dalton's tar pit video.
- The "no competition is a red flag" pattern.
- Schlep-blindness counterpart (per Paul Graham): boring B2B, regulated industries, hard-to-start ideas often look like tar pits but are not — the difficulty IS the moat.
- Decision rule: if a candidate matches a known tar pit AND no founder-specific insider edge exists, kill.

- [ ] **Step 2: Commit**

```
git add references/tar-pit-detection.md
git commit -m "ref: tar-pit-detection — canonical tar pits + schlep blindness counterpart"
```

---

## Task 10: Reference — cofounder-frameworks.md

**Files:**
- Create: `references/cofounder-frameworks.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "cofounder-frameworks.md", ~400 words) and §7.2 cofounder-fit content.

Required content:
- YC's rules: work together on a meaningful project for ≥ 4 weeks before committing; near-equal equity (50/50, not 90/10); 4-year vesting with 1-year cliff non-negotiable.
- Patterns to avoid: LinkedIn-stranger cofounders, family-members who can't be fired, lopsided equity splits between true cofounders, hiring contractors for the core build.
- The 4-week trial protocol from §7.2 (build small thing together, run interviews together, hard conversation).
- When you don't need a cofounder: domain expert who can learn enough to ship v1; technical founder with deep network in target domain.
- Sales hire pre-PMF: refuse to recommend. Founders do early sales themselves.
- YC Cofounder Matching platform pointer.

- [ ] **Step 2: Commit**

```
git add references/cofounder-frameworks.md
git commit -m "ref: cofounder-frameworks — YC rules, 4-week trial protocol, anti-patterns"
```

---

## Task 11: Reference — case-studies.md

**Files:**
- Create: `references/case-studies.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "case-studies.md", ~800 words). 10 companies × 100–150 words each:
- **Stripe** — founder-market fit (Collison brothers, payment pain at e-commerce startups); things that don't scale (manual nightly bank faxes); early customer narrowness (only YC startups).
- **Brex** — pivot from VR headset to corporate cards; FMF earned via deep dive into fintech regulation.
- **Airbnb** — narrow start at conferences with air mattresses; multiple launches (3); doing things that don't scale (photographing listings personally).
- **Segment** — pivot from classroom feedback tool to analytics infrastructure; the customer-data-platform wedge.
- **Slack** — pivot from Glitch (failed game) to internal-tools-as-product.
- **Superhuman** — Rahul Vohra's PMF engineering blueprint; from 22% → 58% Sean Ellis score.
- **PlanGrid** — Tracy Young, domain expert (construction) + technical cofounder; schlep-heavy regulated B2B.
- **DoorDash** — landing page + manual delivery; founders did the deliveries themselves to learn the workflow.
- **Twitch** — long Justin.tv journey, content iteration, gaming wedge.
- **Magic** — rapid SMS-based prototype, viral hit, the perils of attitudinal demand without retention.

Each entry must be runnable as a pattern-match anchor by skills: distinct lesson, attributable, concrete.

- [ ] **Step 2: Commit**

```
git add references/case-studies.md
git commit -m "ref: case-studies — 10 anchor companies for runtime pattern matching"
```

---

## Task 12: Reference — external-resources.md

**Files:**
- Create: `references/external-resources.md`

- [ ] **Step 1: Write the reference**

Generate per spec §8 (entry "external-resources.md", ~600 words). Organize by phase, not by source type.

Sections:
- **Discovery / idea-genesis**: Paul Graham *How to Get Startup Ideas* (essay); YC video *Where Do Great Startup Ideas Come From* (Dalton + Michael); YC video *How to Get and Evaluate Startup Ideas* (Dalton); PG *Schlep Blindness*.
- **Founder profile / cofounder**: PG *How to Pick a Cofounder*; YC video *How to Apply and Succeed at Y Combinator*; YC Cofounder Matching.
- **Customer discovery**: Rob Fitzpatrick *The Mom Test* (book); YC video *How to Talk to User* (Jared Friedman); Steve Blank *Four Steps to the Epiphany*.
- **MVP / experiments**: Eric Ries *The Lean Startup*; YC video *How to Build an MVP* (Michael Seibel); PG *Do Things That Don't Scale*; Dropbox video MVP.
- **First customers / sales**: YC video *How to Get Your First Customers* (Gustav); YC video *The Best Way to Launch Your Startup* (Kat Manalac); Lenny Rachitsky GTM articles.
- **PMF measurement**: Rahul Vohra First Round Review *How Superhuman Built an Engine to Find Product/Market Fit*; Sean Ellis 40% Rule posts; Marc Andreessen *The Only Thing That Matters*.
- **Pivoting**: YC video *All About Pivoting* (Dalton); Eric Ries pivot chapter.
- **General canon**: Hard Thing About Hard Things (Horowitz); Zero to One (Thiel); Crossing the Chasm (Moore).
- **Communities**: Indie Hackers; r/Entrepreneur; On Deck.
- **Podcasts**: Acquired; How I Built This; My First Million; Lenny's Podcast.

One line per item: title — author/host — one-sentence why-relevant.

- [ ] **Step 2: Commit**

```
git add references/external-resources.md
git commit -m "ref: external-resources — phase-organized canon (books, videos, essays)"
```

---

## Task 13: Skill — orientation

**Files:**
- Create: `plugins/startup-skills-core/skills/orientation/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use the YAML frontmatter from spec §7.1 Skill 1 verbatim. Body follows §9 format. Process steps come directly from §7.1 Skill 1 SKILL.md body content guidance:
1. Read state document (per `references/state-document-protocol.md`). If exists, ask user "Looks like we've talked before. Picking up from where we left off?"
2. 3-sentence intro: what Startup Skills is; the human-Claude division; the state document.
3. One orientation question with 5 options (per §7.1).
4. Initialize STARTUP-STATE.md from `references/state-document-template.md`. Populate placeholders from what the user has said.
5. Route per the option chosen (per §7.1).
6. Tell user explicitly: "Type `/skill <name>` to invoke the next one, or just describe what you want next."

Required Reading section: `references/tone-and-stance.md`, `references/state-document-template.md`, `references/state-document-protocol.md`.

Anti-Patterns Prevented: founders bouncing between concepts without an anchor; restarting context every session; vague advice that doesn't match where the founder is.

Tone section: short reminder pointing to `references/tone-and-stance.md`.

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-core/skills/orientation/SKILL.md
git commit -m "skill: orientation — entry point and router"
```

---

## Task 14: Skill — founder-context

**Files:**
- Create: `plugins/startup-skills-core/skills/founder-context/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use the YAML frontmatter from spec §7.1 Skill 2 verbatim. Body per §9 format. Process steps from §7.1 Skill 2 guidance:
1. Read STARTUP-STATE.md; confirm Founder Profile section is empty or stale.
2. Sequenced questions (one at a time, 7 questions per §7.1).
3. While asking, in parallel: invoke `market-intel` on stated domain using `references/research-playbook.md`. Surface 4-bullet domain context note alongside.
4. Pattern-match founder profile against `references/case-studies.md` and surface analogue if any.
5. Surface 2–3 questions only the founder could answer.
6. Apply bias sentinel from `references/bias-sentinel.md`. Especially founder-market fit gaps.
7. Update STARTUP-STATE.md Founder Profile section + Session Log line.
8. Recommend next skill based on Starting Point answer.

Required Reading: `references/state-document-protocol.md`, `references/bias-sentinel.md`, `references/research-playbook.md`, `references/case-studies.md`, `references/external-resources.md`.

External resources to surface: PG *How to Get Startup Ideas* (FMF section); YC *How to Get and Evaluate Startup Ideas* (Dalton); YC *Should You Start a Startup* + YC Cofounder Matching for non-technical founders.

Tone reminder pointing to `references/tone-and-stance.md`.

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-core/skills/founder-context/SKILL.md
git commit -m "skill: founder-context — capture profile, parallel domain research"
```

---

## Task 15: Skill — idea-genesis

**Files:**
- Create: `plugins/startup-skills-discovery/skills/idea-genesis/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use the YAML frontmatter from spec §7.2 Skill 3 verbatim. Body per §9 format. Process from §7.2 Skill 3:
- Read state document; confirm Founder Profile is rich enough.
- Open with PG framing: "The verb you want is not 'think up' but 'notice.'"
- Refuse SISP openings ("AI is cool, what could I apply it to") — flat redirect.
- Organic track: 7 questions, one at a time (from §7.2 Skill 3).
- Research track (parallel, automatic, via `references/research-playbook.md`): 5–7 searches per the §7.2 list.
- Synthesize: 5–7 candidate idea spaces, each one-sentence, tagged organic/research/hybrid.
- For each candidate: name one specific potential customer.
- Apply bias sentinel: schlep blindness, false consensus, anchoring.
- Surface Dalton's "three things that make ideas seem bad but actually make them good."
- Ask: "Which 2–3 resonate? We'll take them to `idea-pressure-test`."
- Update state doc + Session Log.

Required Reading: `references/state-document-protocol.md`, `references/bias-sentinel.md`, `references/research-playbook.md`, `references/tar-pit-detection.md`, `references/external-resources.md`, `references/case-studies.md`.

External resources to surface: PG *How to Get Startup Ideas*; YC *Where Do Great Startup Ideas Come From*; YC *How to Get and Evaluate Startup Ideas*.

Artifacts on request: Idea Candidate Brief (one-page markdown).

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-discovery/skills/idea-genesis/SKILL.md
git commit -m "skill: idea-genesis — organic + research tracks, refuses SISP framings"
```

---

## Task 16: Skill — market-intel

**Files:**
- Create: `plugins/startup-skills-discovery/skills/market-intel/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use YAML frontmatter from spec §7.2 Skill 4 verbatim. Body per §9 format. Process from §7.2 Skill 4:
1. Take topic from calling context (domain, problem, segment, or company).
2. Construct 5–10 queries using `references/research-playbook.md` across the 7 categories.
3. Execute searches (parallel WebSearch when possible).
4. WebFetch on 2–3 most signal-rich pages for substance.
5. Synthesize brief: Pain expressed (verbatim quotes w/ source); Vocabulary (5–10 exact customer words); Who's building; What's missing (from reviews); Why-now; Failed attempts; Tar-pit check (per `references/tar-pit-detection.md`).
6. Refuse TAM-as-vanity-metric — zero weight.
7. Update state doc Competitive Landscape + What We Know vs Assumed sections.
8. Return brief to calling skill or user.

Required Reading: `references/state-document-protocol.md`, `references/research-playbook.md`, `references/tar-pit-detection.md`, `references/case-studies.md`.

Artifacts on request: standalone "Market Intelligence Brief" markdown.

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-discovery/skills/market-intel/SKILL.md
git commit -m "skill: market-intel — parallel web research, structured brief"
```

---

## Task 17: Skill — idea-pressure-test

**Files:**
- Create: `plugins/startup-skills-discovery/skills/idea-pressure-test/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use YAML frontmatter from spec §7.2 Skill 5 verbatim. Body per §9 format. Process from §7.2 Skill 5:
1. Read state doc; pull idea + founder profile.
2. **Steel-man first**: explicit "Here's the strongest version of what you're proposing..."
3. Invoke `market-intel` if not yet run.
4. Score across YC 10-question framework (one paragraph analysis per dimension).
5. Apply Dalton's 4-criteria rubric from `references/scoring-rubrics.md`.
6. Tar-pit detection per `references/tar-pit-detection.md`.
7. Schlep-blindness detection (dismissing hard/boring/regulated).
8. SISP detection — refuse to evaluate technology-first framings.
9. "No competition" pushback.
10. Composite + binary recommendation per the rules in `references/scoring-rubrics.md`.
11. Bias sentinel throughout.
12. Surface real-world anchors from `references/case-studies.md`.
13. Update state doc.
14. Recommend next skill per scoring outcome.

Required Reading: `references/state-document-protocol.md`, `references/bias-sentinel.md`, `references/scoring-rubrics.md`, `references/tar-pit-detection.md`, `references/case-studies.md`, `references/external-resources.md`.

Artifacts on request: scored "Idea Assessment Memo" markdown.

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-discovery/skills/idea-pressure-test/SKILL.md
git commit -m "skill: idea-pressure-test — steel-man, score, tar-pit detection"
```

---

## Task 18: Skill — cofounder-fit

**Files:**
- Create: `plugins/startup-skills-discovery/skills/cofounder-fit/SKILL.md`

- [ ] **Step 1: Write the SKILL.md**

Use YAML frontmatter from spec §7.2 Skill 6 verbatim. Body per §9 format. Process from §7.2 Skill 6:
1. Read state doc for Founder Profile + idea.
2. Diagnose team gaps: domain expertise, technical, sales/distribution, design (for consumer).
3. Approach by gap type per §7.2 (technical, domain, sales — all with refusal patterns).
4. If considering a cofounder: YC's rules (work together first, near-equal equity, vesting) from `references/cofounder-frameworks.md`.
5. Produce 4-week trial protocol on request.
6. Bias sentinel: rushed cofounder choice; "we get along great"; ignoring financial commitments.
7. Update state doc Team section.
8. Recommend back to wherever the founder was.

Required Reading: `references/state-document-protocol.md`, `references/bias-sentinel.md`, `references/cofounder-frameworks.md`, `references/external-resources.md`.

External resources to surface: YC Cofounder Matching; PG *How to Pick a Cofounder*; YC *How to Apply and Succeed at YC* (team composition section).

Artifacts on request: 4-Week Cofounder Trial Protocol (markdown).

Keep under 250 lines.

- [ ] **Step 2: Commit**

```
git add plugins/startup-skills-discovery/skills/cofounder-fit/SKILL.md
git commit -m "skill: cofounder-fit — diagnose gaps, YC rules, trial protocol"
```

---

## Task 19: README.md

**Files:**
- Create: `README.md`

- [ ] **Step 1: Write the README**

Per spec §14 Step 5. Sections in order:
1. **What is this?** (3 paragraphs — elevator pitch, drawn from §1)
2. **The thesis** — block-quote the load-bearing passage from §4.1 verbatim.
3. **Who's it for?** — the 6 personas from §3.3 as a short bullet list.
4. **What's included (v0.1)** — 2 plugins, 6 skills, 1-paragraph each; 10 references mentioned as a single bullet.
5. **Install (Claude Code)** — exact commands from §11.2 Path A, scoped to the 2 v0.1 plugins:
   ```
   /plugin marketplace add quinnhall07/startup-skills
   /plugin install startup-skills-core@startup-skills
   /plugin install startup-skills-discovery@startup-skills
   ```
6. **Install (claude.ai)** — brief per §11.2 Path B.
7. **Quick start** — `/skill orientation` then describe what you want.
8. **Methodology and sources** — source list from §5 (YC, Mom Test, Lean Startup, Four Steps, Sean Ellis, Vohra, Kahneman/Tversky/Lovallo, Klein, Lenny, Andreessen, etc.).
9. **Status and roadmap** — current v0.1, what's coming in v0.2–v1.0 per §12, link to CHANGELOG.
10. **License** — PolyForm Noncommercial 1.0.0, brief explainer (noncommercial use; commercial use requires maintainer license).
11. **Contributing** — issues welcome; PR guide brief.
12. **Acknowledgments** — YC, Fitzpatrick, Ries, Blank, Ellis, Kahneman, Klein, Caldwell, Seibel, Friedman, Manalac, Bhat, Alstromer.

Tone: NOT marketing fluff. Direct prose. Use "Aggressive Epistemic Auditor" and "willing to wound" phrases — they signal quality.

- [ ] **Step 2: Commit**

```
git add README.md
git commit -m "docs: README for v0.1 — install, thesis, included skills, sources"
```

---

## Task 20: Smoke test — manifest validity + cross-link integrity

**Files:** none modified — verification only.

- [ ] **Step 1: Validate JSON manifests**

```
Get-Content .claude-plugin\marketplace.json | ConvertFrom-Json | Out-Null
Get-Content plugins\startup-skills-core\.claude-plugin\plugin.json | ConvertFrom-Json | Out-Null
Get-Content plugins\startup-skills-discovery\.claude-plugin\plugin.json | ConvertFrom-Json | Out-Null
```
Expected: no errors.

- [ ] **Step 2: Verify every skill path in marketplace.json exists**

Run (PowerShell):
```
$mp = Get-Content .claude-plugin\marketplace.json | ConvertFrom-Json
foreach ($p in $mp.plugins) { foreach ($s in $p.skills) { if (-not (Test-Path "$s\SKILL.md")) { Write-Error "MISSING: $s\SKILL.md" } } }
"All skill paths verified."
```
Expected: "All skill paths verified."

- [ ] **Step 3: Verify every reference cited in any SKILL.md actually exists**

Use Grep to list all `references/<file>.md` strings in plugins/, then Test-Path each. Expected: all references that v0.1 skills cite resolve. (v0.1 skills may forward-reference v0.2+ refs like `evidence-weighting-matrix.md` in some cases — if so, the missing ones should be only the explicitly-forward-referenced v0.2+ files, and the SKILL.md should already document them as "future".)

If any v0.1 skill references a v0.2+ file that's not listed in the spec as a forward reference, fix the SKILL.md (do not create the file early).

- [ ] **Step 4: Verify every SKILL.md is ≤ 250 lines**

```
Get-ChildItem -Recurse -Filter SKILL.md plugins | ForEach-Object { $lines = (Get-Content $_.FullName | Measure-Object -Line).Lines; if ($lines -gt 250) { Write-Error "TOO LONG ($lines): $($_.FullName)" } }
"All SKILL.md files within 250-line limit."
```

- [ ] **Step 5: No commit needed for verification.** If anything fails, return to the relevant task, fix, and re-run.

---

## Self-Review Checklist (run after writing the plan, before execution)

- [x] Every v0.1 skill in §7.1–§7.2 has its own task (Tasks 13–18 cover orientation, founder-context, idea-genesis, market-intel, idea-pressure-test, cofounder-fit — six total).
- [x] Every v0.1 reference in §12 v0.1 list has its own task (Tasks 3–12 cover all 10).
- [x] Repo scaffolding (Task 1) and JSON manifests (Task 2) precede content.
- [x] README is its own task (Task 19) after content is written.
- [x] Verification task (Task 20) at the end.
- [x] No placeholders — `quinnhall07` filled in everywhere; PolyForm license is verbatim-from-source; JSON manifests are complete in this plan.
- [x] Method/file names consistent — `STARTUP-STATE.md`, `.claude/startup-state.md`, plugin and skill names match spec §10 verbatim.
- [x] Spec coverage check: all v0.1 deliverables from §12 v0.1 list mapped to tasks.

---

## Execution notes

- Existing repo files (`Skills/`, `YC Startup School Resources/`, `startup-skills-spec-v0.2.md`, prior `gemini` doc) are NOT touched.
- Reference files use **original synthesis** of named sources — no quotation, but attribute by name (Fitzpatrick, Ries, Blank, Ellis, Kahneman, etc.) inline.
- SKILL.md files use the §7 YAML frontmatter verbatim. Body is original prose following §9.
- A few v0.1 SKILL.md files will reference v0.2+ files (e.g., `discovery-coach` forward references). Spec says forward references are fine — those files don't need to exist yet, but skills should only forward-reference files the spec defines.
