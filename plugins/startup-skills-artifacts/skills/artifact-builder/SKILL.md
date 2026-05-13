---
name: artifact-builder
description: Use whenever the user explicitly asks for a polished, external-facing deliverable. Fires on phrases like "create a pitch deck," "build me a landing page," "draft a one-pager," "investor email," "demo day deck," "fundraising materials," "make a logo," "produce a brand brief." All artifacts are generated FROM the current state document, reflecting current validated understanding — never speculation. Routes internally to the right format (pptx for decks via the pptx skill if available, React/HTML for landing pages, markdown for one-pagers and emails). Will refuse to produce a polished pitch deck if PMF stage is pre-signal — fundraising on speculation is dishonest. Will flag any sections where the state document is thin so the founder knows what's substantiated vs filled-in.
---

# Artifact Builder

Produces polished external-facing deliverables — pitch decks, landing pages, one-pagers, investor emails, demo day scripts — pulled from the current state document. Refuses to produce a pitch deck pre-signal. Marks thin sections so the founder knows what's substantiated vs filled-in.

## When to Activate

Only on explicit request. The system never auto-generates artifacts; the founder must ask.

- Phrases: "create a pitch deck," "build me a landing page," "draft a one-pager," "investor email," "demo day deck," "fundraising materials," "make a logo," "produce a brand brief."
- Also: a calling skill may surface the artifact option ("I can also produce a Landing Page for this hypothesis if you'd like") and route here on user confirmation.

## Required Reading

- `references/state-document-protocol.md`
- `references/pitch-deck-structure.md` — 10–12 slide YC format; what never to include.
- `references/landing-page-patterns.md` — Fake Door / signup page anatomy.
- `references/one-pager-structure.md` — async one-page format.
- `references/email-templates.md` — outreach patterns including investor email shapes.
- `references/case-studies.md` — for anchor examples.
- `references/bias-sentinel.md` — pitch-deck-as-fiction, false traction claims, vanity metrics.

## State Document Protocol

Read `STARTUP-STATE.md` thoroughly — this skill *consumes* the state to produce artifacts. Update Session Log noting the artifact produced: `- [YYYY-MM-DD] artifact-builder — produced <type> for <purpose>, marked <N> thin sections`. Do NOT write to other sections; this skill outputs, it does not change strategy.

## Process

1. **Read state.** All sections.

2. **Detect requested artifact type.** Confirm with the user if ambiguous: "Pitch deck, landing page, one-pager, investor email, or something else?"

3. **Routing per request type:**

   - **Pitch deck:**
     - **If PMF stage is pre-signal: REFUSE.** State the reason directly: "Pre-signal pitch decks are speculative fiction. Serious investors will see through it; the time would be better spent on `discovery-coach` to lift the evidence quality. I can produce a one-pager instead — that's appropriate at this stage. Or I can produce a deck flagged with thin-section warnings, if you understand the trade-off."
     - **If PMF is early-signal or higher:** produce a 10–12 slide YC-style deck per `references/pitch-deck-structure.md`. If a `pptx` skill (Anthropic's official PowerPoint skill) is available in this environment, use it for native pptx output. Otherwise produce as markdown the user can paste into Google Slides or Keynote.
     - Pull each slide's content from the state: problem from Current Hypothesis + ICP; solution from One-Liner; traction from Evidence Log + PMF Running Score; market from Competitive Landscape + bottom-up math from Pricing × ICP count; business model from Pricing; team from Founder Profile + Team; ask from a question to the user ("how much are you raising, for what milestones?").

   - **Landing page:** build as React or static HTML per `references/landing-page-patterns.md`. Single-page, clear value prop, single CTA. Mobile-responsive. Tailwind for styling. The headline uses customer vocabulary from `market-intel`; the value prop is the One-Liner from state.

   - **One-pager:** markdown per `references/one-pager-structure.md`. Problem, solution, traction (or validation-to-date for pre-signal), ask, contact. Single page, ~400–500 words.

   - **Investor email / cold email:** draft to a specific named recipient using `references/email-templates.md`. Customize the credibility line and value prop. 50–100 words, plain text, single CTA. Refuse generic blasts — investor emails specifically must be personalized per recipient.

   - **Demo day script:** 2-minute spoken script with slide cues. Pulls from the pitch deck content; reformatted for spoken delivery (no full sentences in slides; full sentences in script). Practice runtime ≤120 seconds.

   - **Interview script** (if requested standalone): route to `discovery-coach` PREPARE mode — that's the canonical source.

   - **Outreach email batch** (if requested standalone): route to `outreach-engine` — that's the canonical source.

   - **MVP spec** (if requested standalone): route to `mvp-architect`.

   - **Logo / brand:** route to Claude Design if available in the environment, otherwise produce a brand brief markdown the user can take to a designer (positioning, tone, color directions, typography directions, what to avoid).

4. **Mark thin sections explicitly.** Wherever the state document is sparse, insert a callout in the artifact:
   - "TRACTION: [thin — only 3 ICP-targeted conversations logged at this date; update once 20+ conversations or Sean Ellis ≥ 30% achieved]."
   - "MARKET SIZE: [bottom-up calculation pending — current estimate is ICP × price; no top-down TAM by design]."

   This is non-negotiable. Founders will use the artifact externally; the markings keep them honest about what is substantiated vs aspirational.

5. **Apply YC's pitch deck conventions** when producing decks:
   - Short slides, big text, no jargon.
   - Traction prominent if it exists (slide 4 of 10–12).
   - No TAM hand-waving — bottom-up only.
   - No exit slides pre-Series-B.
   - Real customer logos only, with permission.

6. **Bias sentinel pass.** Especially:
   - **Pitch-deck-as-fiction.** Puffery in projections, "we'll be at $50M ARR in year 3" without basis. Refuse.
   - **False traction claims.** "Featured in TechCrunch" is not traction. Logos of investors who haven't invested are not traction.
   - **Vanity metrics.** Page views, social-media followers — not on slides.

7. **Produce the artifact.** As a markdown artifact in claude.ai, or a file in Claude Code. For pitch decks specifically: if `pptx` skill is available, use it for native PowerPoint; otherwise produce markdown.

8. **Log the artifact** in `STARTUP-STATE.md` Session Log: what type, what purpose, what thin sections were flagged.

## Outputs

- The artifact requested (pitch deck, landing page, one-pager, investor email, demo day script, brand brief).
- Writes to state: Session Log entry only. This skill does not change strategy or evidence — it surfaces what's in the state document.

## Anti-Patterns Prevented

- Pre-signal pitch decks.
- TAM hand-waving on market size slides.
- Inflated traction.
- Investor email blasts.
- Exit slides on seed decks.
- Vanity-metric slides (followers, page views).
- Auto-generating artifacts without explicit user request.

## Recommended Next Skills

Whichever skill the founder was in before invoking this one. Artifact-builder is a sidecar; it doesn't drive the journey forward by itself. If a pitch deck was produced and the founder is preparing to raise, recommend a `signal-audit` first to ensure the traction story is honest.

## Tone

Per `references/tone-and-stance.md`. Direct on refusals (pre-signal pitch decks, vanity metrics). When marking thin sections, do not soften — the marks are the value. A polished artifact with unmarked thin sections is worse than a rougher artifact that's honest about what's missing.
