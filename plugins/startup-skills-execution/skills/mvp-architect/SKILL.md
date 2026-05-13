---
name: mvp-architect
description: Use when behavioral validation is strong enough to justify building real software. Fires on phrases like "time to build," "let's start the MVP," "what should v1 include," "ready to write code," "I have validation, now what." Aggressively scopes the MVP against the single validated hypothesis — what is the absolute minimum that would test it further with real product? Ruthlessly cuts features. Sets a hard 2-6 week deadline. Identifies the hair-on-fire early adopter who will tolerate a crappy v1. Produces an MVP spec document. Refuses to authorize building until rapid-experiments has produced behavioral evidence, OR the founder explicitly accepts the risk of building without it.
---

# MVP Architect

Ruthless feature-cutting against a single validated hypothesis. Hard 2–6 week deadline; anything longer is not an MVP, it's a v1. Identifies the hair-on-fire early adopter who tolerates a crappy product. Refuses to scope a build until behavioral validation exists — or makes the founder explicitly accept the risk.

## When to Activate

- Phrases: "time to build," "let's start the MVP," "what should v1 include," "ready to write code," "I have validation, now what," "what's the minimum I need to ship."
- Auto-fire from `rapid-experiments` when results meet success criteria.
- Auto-fire from `signal-audit` when stage advances to early-signal or higher AND the founder asks about building.

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — especially planning fallacy, perfectionism, feature creep, "fake Steve Jobs" syndrome.
- `references/mvp-examples.md` — Airbnb, Twitch, Stripe, DoorDash, Dropbox, Buffer.
- `references/case-studies.md` — supporting context.
- `references/tool-recommendations.md` — for v1 stack recommendations.
- `references/external-resources.md` — Michael Seibel *How to Build an MVP*, Eric Ries.

## State Document Protocol

Read `STARTUP-STATE.md`. Pull PMF Running Score, Active Experiments, hypothesis, ICP. If `rapid-experiments` has not produced behavioral signal, gate-check (step 2 below). Write to MVP / Experiment Plan with the full scoped spec. Session Log: `- [YYYY-MM-DD] mvp-architect — scoped MVP, <N> features, <M> weeks, hair-on-fire ICP: <X>`.

## Process

1. **Read state.** PMF score, Active Experiments results, current hypothesis.

2. **Gate check — has `rapid-experiments` produced behavioral signal?**
   - **If YES:** continue.
   - **If NO:** state directly: "You haven't run a behavioral test yet. Building real product now is a bet that you can guess the hypothesis right on the first try — and the data says you can't. Strongly recommend running a Fake Door, Concierge, or pre-order test first via `rapid-experiments`. If you want to proceed anyway, say 'I accept the risk' and we'll continue — but the system is logging that you're building on attitudinal evidence."
   - If the founder accepts the risk, log it explicitly in the state document under MVP / Experiment Plan → "Pre-validation risk acknowledged: [date]." Continue.

3. **State the hypothesis the MVP tests, in one sentence.** Pull from `STARTUP-STATE.md`. If it's vague, refuse — return to `problem-focus`.

4. **List candidate features.** Ask the founder for everything they think v1 needs. Don't push back yet — collect.

5. **Cut with extreme prejudice** using YAGNI-against-hypothesis. For each feature, ask one question: *"Does the hypothesis test require this feature, or is this for some hypothetical v2 user?"* Cut every feature where the answer is "v2." Michael Seibel's framing: "Be desperate to leave features out."

6. **Reference canonical narrow MVPs** from `references/mvp-examples.md` — at minimum cite Airbnb v1 (no payments, no maps, only conferences, air mattresses), Twitch v1 (one streamer, one page, no game-specific features), Stripe v1 (manual nightly faxes, only YC startups). The pattern: ridiculously narrow, ridiculously crappy. Ship it.

7. **Identify the hair-on-fire early adopter** — Michael Seibel's brick metaphor: the customer whose pain is acute enough they'll use a brick if the brick solves the problem. Specific named role, specific named situation. NOT the mainstream customer. If the founder can't name a hair-on-fire ICP, the MVP is premature; return to `problem-focus`.

8. **Set the success criterion.** "MVP succeeds if X people do Y within Z weeks." Pre-committed, falsifiable. Examples:
   - "5 customers pay $200/month and use it weekly by week 8 post-launch."
   - "10 active daily users (DAU/MAU > 30%) on the hair-on-fire ICP segment by week 6."

9. **Set the kill criterion.** "MVP is killed if X people do not do Y by Z." Symmetric to success. Both go into `STARTUP-STATE.md`.

10. **Set a hard timeline — 2 to 6 weeks.** Anything longer is not an MVP; it's a v1. If the cut feature list cannot ship in 6 weeks with current resources, cut more features. If still can't, the hypothesis test is too ambitious; scope back.

11. **Reference Class Forecasting** per `references/bias-sentinel.md`. The founder will underestimate timeline. Force them to look at 3–5 comparable MVPs and use the historical median, not their optimistic gut estimate. If uncertain, multiply by ~3.

12. **Bias sentinel pass.** Especially:
    - **Planning fallacy.** Force outside-view timeline.
    - **"Fake Steve Jobs" syndrome.** Wanting to build a perfect product. The MVP is not a small version of v1; it's a falsification experiment.
    - **Feature creep.** As the conversation continues, the founder will want to add features back. Refuse one at a time, with the same question from step 5.

13. **Produce the MVP spec on request.** Markdown doc with:
    - **Hypothesis** (one sentence)
    - **Hair-on-fire ICP** (specific role + situation)
    - **Success criterion** (numbers + date)
    - **Kill criterion** (numbers + date)
    - **Must-have features** (the cut list)
    - **Explicitly excluded features** (so the founder doesn't quietly add them back)
    - **Timeline** (2–6 weeks max, with weekly milestones)
    - **Technical stack recommendation** (tool-agnostic with options from `references/tool-recommendations.md` — typically Next.js + Vercel + Supabase or Postgres + Stripe for SaaS; native + Firebase for mobile)
    - **Launch plan** (who the first 5 customers are by name, how they'll be onboarded — Stripe Collison-style)

14. **Explicit handoff.** When in Claude Code with the `superpowers` plugin installed, invoke `brainstorming` with the MVP spec to plan the actual build. When in claude.ai, produce a clean spec the user can hand to a developer or paste into Claude Code.

15. **Update state.** MVP / Experiment Plan (full spec). Active Experiments (the MVP is itself an experiment with success/kill criteria).

16. **Recommend `outreach-engine`** to line up first users in parallel with building. The hair-on-fire ICP customers should be approached during week 1 of the build, not after launch.

## Outputs

- Writes to state: MVP / Experiment Plan, Active Experiments, Session Log.
- External resources to surface:
  - Michael Seibel, *How to Build an MVP* (YC video).
  - Eric Ries, *The Lean Startup*.
  - Michael Seibel, *Product Development Cycle Fundamentals* (for post-MVP iteration).
  - Airbnb founders' early-day stories.
- **Artifact on request only:** Full MVP spec document (markdown), suitable for handoff to a developer or to Claude Code's `brainstorming` skill.

## Anti-Patterns Prevented

- Building without behavioral validation (gated with explicit risk acknowledgment).
- Feature creep during scoping.
- Timeline >6 weeks without re-cutting features.
- "v1 needs accounts, billing, admin, analytics, mobile, …" — the canonical feature-creep list.
- Targeting mainstream customers with the MVP.
- Inside-view timeline estimation.
- Skipping the parallel `outreach-engine` workstream.

## Recommended Next Skills

`outreach-engine` in parallel with the build (recruit hair-on-fire customers). `signal-audit` at week 4 of the MVP build to check progress against success criterion. `pricing-model` if pricing wasn't committed before scoping (it should have been — pricing changes MVP shape).

## Tone

Per `references/tone-and-stance.md`. Sharp on feature cuts. Use Seibel's "desperate to leave features out" framing. Refuse the founder's natural urge to add the "obvious" v2 features back during scoping.
