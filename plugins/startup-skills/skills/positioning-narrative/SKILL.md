---
name: positioning-narrative
description: |
  Position the product (Dunford 10-step) and write the strategic narrative (Raskin 5-act). Output: position statement + competitive alternatives + narrative spine. Feeds `artifact-builder` for decks/websites and `outreach-engine` for cold email subject lines. Refuses positioning before early-signal PMF.

  TRIGGER when: user is about to write a pitch deck, website, cold email, or one-pager; user says "how do I describe what we do", "what's our positioning", "elevator pitch", "messaging", "narrative", "category"; PMF stage >= early-signal AND `STARTUP-STATE.md` Positioning section is empty.

  SKIP: user is pre-validation (positioning needs an HXC; route to `discovery-coach` and `signal-audit` first); user is already deep in artifact production (route to `artifact-builder` which surfaces this skill if positioning gap exists); user is asking about a logo or brand identity (out of scope).
---

# Positioning Narrative

Positioning (Dunford) tells you who you are. Strategic narrative (Raskin) tells the story. Most founders skip both and go from problem-focus -> MVP -> cold email, then wonder why pitch decks fail. This skill produces the positioning artifact that anchors every external-facing output.

## HARD-GATE

Do not proceed if PMF stage is pre-signal. Positioning requires an HXC (High-Expectation Customer, per Vohra/Superhuman blueprint). Pre-PMF, you don't yet know who your HXC is — positioning prematurely locks in the wrong frame.

If founder pushes back: state directly: "Pre-PMF positioning is theatre. Serious investors see through it; the time would be better spent on `discovery-coach` to find your HXC. I'll produce a one-pager instead — appropriate at this stage."

## When to Activate

- User is about to write a pitch deck, website, cold email, or one-pager AND the Positioning section of state is empty.
- User says "how do I describe what we do," "what's our positioning," "elevator pitch," "messaging," "narrative," "category."
- A calling skill (`artifact-builder`, `outreach-engine`) detected a positioning gap and routed here.
- PMF stage is at least early-signal per `pmf-audit`.

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/positioning-frameworks.md` — Dunford 10-step, Raskin 5-act.
- `${CLAUDE_PLUGIN_ROOT}/references/pmf-scoring.md` — HXC segmentation.
- `${CLAUDE_PLUGIN_ROOT}/references/pitch-deck-structure.md` — deck format.
- `${CLAUDE_PLUGIN_ROOT}/references/one-pager-structure.md` — pre-signal format.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`
- `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`

## State Document Protocol

Read entire state. Pull ICP, hypothesis, competitive landscape, PMF score, HXC definition (if exists). Update Positioning section (new in schema v2) at completion. Session Log: `- [YYYY-MM-DD] positioning-narrative — produced position statement + narrative for <HXC>, alternatives: <list>`.

## Process

1. **Read state.** PMF stage, HXC (from `pmf-audit`), ICP, competitive landscape. Verify gate: PMF stage >= early-signal. If not, route to `discovery-coach`.

2. **Dunford Step 1-4: customers + alternatives.**
   - Pull the "Very Disappointed" cohort from PMF survey (or top 5-10 paying customers if no survey).
   - Ask: "What would these customers do if your product disappeared tomorrow?" Capture **competitive alternatives** — including: status quo, manual spreadsheet, hiring someone, direct competitor, building it themselves.
   - Bad form: "we compete with [direct competitor X only]." Good form: 4-6 alternatives spanning categories.

3. **Dunford Step 5: isolate unique attributes.** What ONLY you have. Features, capabilities, distribution access, founder credibility, partnerships, regulatory advantage, data flywheel. Be specific. "Easier to use" is not unique. "Only product with HIPAA-compliant audit trail for therapy notes" is.

4. **Dunford Step 6-7: map to value, find best-fit customers.** For each unique attribute -> benefit -> underlying need. Then: best-fit customers are those for whom your unique value is HIGHEST-stakes. Often a subset of the HXC.

5. **Dunford Step 8: find market frame (category).** Two paths:
   - **Category-fit:** position within an existing category where you're the better X. Lower cost, faster traction. Use when an obvious category exists.
   - **Category-create:** define a new category. Expensive, multi-year. Use only when no existing category accommodates you (rare for pre-Series-A startups).
   Surface the recommendation explicitly. Default: category-fit.

6. **Dunford Step 9-10: layer trends + capture.** Only honest, directly-relevant trends. "AI is hot" is NOT a trend you can ride if your product isn't AI. Produce the position statement using the Dunford template:
   > For [best-fit customer segment]
   > Who [pain or need]
   > [Product] is [market category]
   > That [unique value]
   > Unlike [primary competitive alternative]
   > We [primary differentiator]

7. **Raskin 5-act strategic narrative (the deck spine).**
   1. **Name the BIG, undeniable shift.** What's changing in the world that makes the old way fail?
   2. **Winners and losers.** Some companies winning under new rules; others dying. Cite specific examples.
   3. **Tease the Promised Land.** What customers become when they win. Aspirational, specific.
   4. **Identify obstacles** to reaching the Promised Land.
   5. **Your product = magic gifts** that overcome each obstacle.

8. **Test against alternatives.** Run the position statement past the founder: "Would your current customer recognize themselves in this? Would your strongest customer say this matches what they love?" If no, revise.

9. **Bias sentinel pass:**
   - **"Everything for everyone"** — vague positioning. Force specificity about who it's NOT for.
   - **Category-create without justification** — expensive; default to category-fit.
   - **Lead with features** — customers buy outcomes. Position leads with outcomes.
   - **Use jargon-category that customers don't say** — "decision-intelligence platform" loses sales. Use customer vocabulary from `market-intel`.

10. **Update state.** Positioning section (new): position statement, competitive alternatives, unique attributes, best-fit customer (sharper than ICP), market category, strategic narrative. Surface to next-skill artifact production.

11. **Recommend next.**
    - For pitch deck: `artifact-builder` with the new positioning + narrative.
    - For cold email: `outreach-engine` (subject lines flow from positioning).
    - For website hero copy: `artifact-builder` for landing-page production.
    - To re-test positioning in customer conversations: `continuous-discovery`.

## Outputs

- Writes to state: Positioning section (full).
- **Artifact on request only:** Position Statement + Strategic Narrative one-pager (markdown), suitable for cofounder/advisor review or as the deck spine for `artifact-builder`.

## Anti-Patterns Prevented

- Pre-PMF positioning (theatre).
- "Everything for everyone" vague positioning.
- Category-create without justification.
- Lead-with-features messaging.
- Jargon-category that customers don't use.
- Skipping competitive alternatives (treating only direct competitors as alternatives).

## Recommended Next Skills

Per step 11. `artifact-builder` is the most common next; `outreach-engine` if cold email is next.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Use Dunford's framings directly ("you compete with the status quo first," "categories don't bend"). Refuse "we don't compete with anyone" — name it as a tell that the founder hasn't done positioning work.
