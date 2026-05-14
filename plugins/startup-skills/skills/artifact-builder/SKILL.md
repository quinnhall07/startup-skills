---
name: artifact-builder
description: |
  Produces polished external-facing deliverables (pitch decks, landing pages, one-pagers, investor emails, demo day scripts) ON DEMAND, pulled from `STARTUP-STATE.md`. Refuses pre-signal pitch decks. Marks thin sections explicitly so founders know substantiated vs. aspirational. Surfaces `positioning-narrative` if positioning section is empty.

  TRIGGER when: user explicitly requests an artifact — "create a pitch deck", "build me a landing page", "draft a one-pager", "investor email", "demo day deck", "fundraising materials"; calling skill surfaces an artifact option and user confirms.

  SKIP: user wants an interview script (route to `discovery-coach` PREPARE — canonical source); user wants outreach batch (route to `outreach-engine`); user wants MVP spec (route to `mvp-architect`); pre-signal pitch deck request (refuse OR produce one-pager with explicit thin-section warnings); user has no positioning yet AND pitch deck requested (route to `positioning-narrative` first).
---

# Artifact Builder

Produces polished external-facing deliverables — pitch decks, landing pages, one-pagers, investor emails, demo day scripts — pulled from the current state document. Refuses to produce a pitch deck pre-signal. Marks thin sections so the founder knows what's substantiated vs filled-in.

## When to Activate

Only on explicit request. The system never auto-generates artifacts; the founder must ask.

- Phrases: "create a pitch deck," "build me a landing page," "draft a one-pager," "investor email," "demo day deck," "fundraising materials," "make a logo," "produce a brand brief."
- Also: a calling skill may surface the artifact option ("I can also produce a Landing Page for this hypothesis if you'd like") and route here on user confirmation.

## Red flags

| Founder request | Response |
|---|---|
| Pre-signal pitch deck for fundraising | Refuse or produce with thin-section warnings + recommend `discovery-coach` instead. |
| Pitch deck without positioning committed | Route to `positioning-narrative` first. |
| TAM hand-waving ("$400B market") | Replace with bottom-up. Refuse top-down. |
| Inflated traction claims | Remove. Source every traction claim. |
| Vanity metrics on slides | Remove (page views, followers, "we've raised $X" before close). |
| Logos without permission | Refuse. Customer-permission required. |
| Generic investor email blast | Refuse. 1:1 personalization required. |
| Exit slides ("acquisition by X by 2030") on seed deck | Refuse. Investors discount the entire deck. |
| Pitch deck for an AI wrapper without distribution / moat | Surface `ai-era-anti-patterns.md` Trap 1. Force the moat narrative before polishing the deck. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/pitch-deck-structure.md` — 10–12 slide YC format; what never to include.
- `${CLAUDE_PLUGIN_ROOT}/references/landing-page-patterns.md` — Fake Door / signup page anatomy.
- `${CLAUDE_PLUGIN_ROOT}/references/one-pager-structure.md` — async one-page format.
- `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md` — outreach patterns including investor email shapes.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — for anchor examples.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — pitch-deck-as-fiction, false traction claims, vanity metrics.
- `${CLAUDE_PLUGIN_ROOT}/references/positioning-frameworks.md` — Dunford + Raskin; the deck spine.
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — AI-product narrative refusal cases.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md` thoroughly — this skill *consumes* the state to produce artifacts. Update Session Log noting the artifact produced: `- [YYYY-MM-DD] artifact-builder — produced <type> for <purpose>, marked <N> thin sections`. Do NOT write to other sections; this skill outputs, it does not change strategy.

## Process

1. **Read state.** All sections.

2. **Detect requested artifact type.** Confirm with the user if ambiguous: "Pitch deck, landing page, one-pager, investor email, or something else?"

3. **Routing per request type:**

   | Artifact | Prerequisite | Output Format | Thin Sections to Mark |
   |---|---|---|---|
   | Pitch Deck | PMF stage ≥ early-signal AND positioning committed | Markdown OR pptx skill | Traction, Market Size, Team |
   | Landing Page | Hypothesis + ICP committed | React or HTML + Tailwind | Value Prop, Social Proof |
   | One-Pager | Founder Profile + Current Hypothesis | Markdown (~400-500 words) | Traction / Validation-to-Date |
   | Investor Email | Specific named recipient | Plain text email | None — refuse if generic |
   | Demo Day Script | Pitch deck completed | Markdown spoken script | Same as deck |
   | Brand Brief | Founder Profile + One-Liner | Markdown brief for designer | Positioning if not committed |

   Pull each artifact's content from `STARTUP-STATE.md`: problem from Current Hypothesis + ICP; solution from One-Liner; traction from Evidence Log + PMF Running Score; market from Competitive Landscape + bottom-up math from Pricing × ICP count; business model from Pricing; team from Founder Profile + Team; ask from a direct question to the user ("how much are you raising, for what milestones?"). Landing page headlines use customer vocabulary from `market-intel`. Demo day scripts reformat deck content for spoken delivery (no full sentences in slides; full sentences in script); practice runtime ≤120 seconds.

   **Route elsewhere:** Interview script → `discovery-coach` PREPARE (canonical source). Outreach email batch → `outreach-engine`. MVP spec → `mvp-architect`. Logo / brand → produce a brand brief markdown (positioning, tone, color directions, typography directions, what to avoid) the user can take to a designer.

3a. **Positioning gate.** For pitch decks, one-pagers, and landing pages: check `STARTUP-STATE.md` Positioning section (schema v2). If empty AND PMF ≥ early-signal, state: "Your positioning isn't committed in state. Pitch deck without positioning is brittle — different audience will get different framings. Recommend running `positioning-narrative` first; it produces the deck spine. Want me to do that now, or proceed with thin-positioning warning?"

4. **Mark thin sections explicitly.** Wherever `STARTUP-STATE.md` is sparse, insert callouts in the artifact:
   - "TRACTION: [thin — only 3 ICP-targeted conversations logged at this date; update once 20+ conversations or Sean Ellis ≥ 30% achieved]."
   - "MARKET SIZE: [bottom-up calculation pending — current estimate is ICP × price; no top-down TAM by design]."

   **MANDATORY at end of every artifact**: append a Thin Section Summary:

   > **Thin Section Summary**: This artifact is N% substantiated (X of Y key claims backed by evidence). Ready for external use: [Yes / No, pending: [list]]. Date assessed: [YYYY-MM-DD].

   Non-negotiable. Founders will use the artifact externally; the markings keep them honest.

5. **Apply YC's pitch deck conventions** when producing decks:
   - Short slides, big text, no jargon.
   - Traction prominent if it exists (slide 4 of 10–12).
   - No TAM hand-waving — bottom-up only.
   - No exit slides pre-Series-B.
   - Real customer logos only, with permission.

6. **Bias sentinel pass.** Each refusal must include rationale:
   - **Pre-signal pitch deck**: "Pre-signal pitch decks are fiction because (1) founders confuse attitudinal interest with behavioral commitment, (2) serious investors see through weak traction, (3) deck-polishing time is `discovery-coach` time foregone. Strongly recommend a one-pager instead — appropriate at this stage."
   - **TAM hand-waving**: "Top-down TAM ($400B market) doesn't survive a 10-minute investor question. Use bottom-up: ICP count × committed price × capture rate."
   - **Inflated traction**: "Featured in TechCrunch is not traction. Logos of investors who haven't invested are not traction. Customer logos require permission AND active customer status."
   - **Vanity metrics on slides**: page views, social-media followers — flag and refuse to include.
   - **Generic investor email blast**: refuse. Investor emails are 1:1, customized per recipient.
   - **Exit slides on seed deck**: refuse. Investors discount the entire deck.

7. **Produce the artifact.** As a markdown artifact in claude.ai, or a file in Claude Code. For pitch decks: use the `pptx` skill for native PowerPoint output when invoked alongside this skill; otherwise produce markdown the user can paste into Google Slides or Keynote.

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

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Direct on refusals (pre-signal pitch decks, vanity metrics). When marking thin sections, do not soften — the marks are the value. A polished artifact with unmarked thin sections is worse than a rougher artifact that's honest about what's missing.
