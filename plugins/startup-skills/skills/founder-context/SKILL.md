---
name: founder-context
description: |
  Capture who the founder is: domain expertise, technical ability, time horizon, resources, archetype, risk tolerance, starting point. Without this, every later skill speculates. Runs parallel domain research while interviewing. Pattern-matches the founder to known case-study analogues.

  TRIGGER when: right after `orientation` for any new founder; Founder Profile section of `STARTUP-STATE.md` is empty OR stale (>90 days); founder reports context change ("I left my job", "I have a cofounder", "I just raised", "I lost runway"); founder says "I work in", "I've been a", "I can't code", "I have X months", "I'm doing this solo", "I have a cofounder".

  SKIP: Founder Profile is already populated AND <90 days old AND user hasn't reported a context change (ask "anything changed since last time?" — if no, skip to routing based on Current Starting Point); user is mid-flow in another skill.
---

# Founder Context

Captures who the founder is, what they know, what they have, and what they're willing to lose. Without this, every later skill speculates. Domain expertise determines what idea spaces are real for this person. Resource reality determines what's possible in the next 90 days. Risk tolerance determines what counts as a real commitment.

## When to Activate

- Right after `orientation` for any new founder.
- Whenever the founder reports a context change: left a job, found a cofounder, raised capital, lost runway, changed time commitment.
- Whenever the Founder Profile section of `STARTUP-STATE.md` is empty, stale (>90 days), or contradicts what the user is now saying.
- On phrases like "I work in," "I've been a," "I can't code," "I have X months," "I'm doing this solo," "I have a cofounder," "I just left my job," "I raised X."

Auto-fire only if: (Founder Profile is empty OR stale >90 days) AND (user phrase matches one of the explicit triggers OR user is in mid-orientation flow). Do not fire silently mid-conversation when Profile is fresh.

## Red flags

| Founder claim | Response |
|---|---|
| "I work in X" but vague on actual scars | Drill: "What part makes you swear? Last time you wanted to throw the keyboard?" |
| "I can build it myself" but no shipping history | Verify with one specific build. If none, FMF technical leg is shaky. |
| "I have six months" + full-time-on-savings | Demand specific runway months. "Live with it" needs a floor in dollars. |
| "My cofounder will handle X" but X is sales pre-PMF | Route to `cofounder-fit` immediately. Sales is founder work pre-PMF. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md` — read/write rules.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — scan for founder-market fit gaps, inside view, optimism bias.
- `${CLAUDE_PLUGIN_ROOT}/references/research-playbook.md` — for the parallel domain research.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — for pattern-matching the founder to known structures.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — for the right reading to surface.
- `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md` — runway floor, sustainable pace check.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md` — voice.

## State Document Protocol

Read `STARTUP-STATE.md` at activation. Confirm the Founder Profile section is empty or stale. Update the Founder Profile section at completion. Append a Session Log entry: `- [YYYY-MM-DD] founder-context — captured profile, surfaced <N> open questions`.

## Process

1. **Read state.** Skim the existing document. If Founder Profile is already populated and fresh, ask whether anything has changed; do not re-run the full intake.

2. **Sequenced intake — one question at a time.** Wait for each answer before asking the next.
   1. **Domain expertise.** "What's an industry, role, or workflow you've spent more than a few thousand hours inside? Not interest — depth."
   2. **Technical ability.** "Can you build the v1 of your idea yourself? If not, who does?"
   3. **Time horizon.** "Realistically, how many weeks until something testable is in front of users?"
   4. **Resource reality.** "Are you solo nights-and-weekends, full-time on savings, or funded with a team? Each shapes what's possible."
   5. **Business archetype.** "Best fit so far: B2B SaaS, consumer, marketplace, devtools, hardware, services-to-product, content/media — which?"
   6. **Starting point.** "Where are you right now? No idea / problem observed / product built / customers but stalled."
   7. **Risk tolerance.** "Worst case: this doesn't work in six months. Can you live with that? What's the floor?"

3. **Parallel domain research.** As soon as Q1 is answered, launch web research on the stated domain using `${CLAUDE_PLUGIN_ROOT}/references/research-playbook.md`. 4–6 searches across forum pain, review complaints, job postings, and failed-startup retrospectives in the founder's domain. Surface a 4-bullet domain context note alongside the interview. Do not stall the questions waiting for research; let it run.

4. **Pattern-match to case studies.** Mandatory pattern-match: compare the profile to `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md`. If no clean match, web search for fresh analogues. Surface the closest analogue and the lesson — don't force-fit, but don't skip. Example: "Your background is structurally similar to Tracy Young at PlanGrid — domain expert + technical cofounder, schlep-heavy regulated B2B. Here's what worked for them: …"

5. **Surface questions only the founder could answer.** From the research, identify 2–3 ambiguities — things the public web cannot resolve. Ask only the founder. Examples: "Reviews say the existing tools fail on X; is X actually what your people complain about, or is it Y?" "Job postings suggest companies hire Z roles to handle this; do those roles in *your* network buy software, or do they build it in-house?"

6. **Bias sentinel pass.** Apply `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`. Especially watch for:
   - **Founder-market fit gap:** founder lacks domain experience AND can't build. Name it directly. Ask how they plan to compensate (cofounder search, embed in industry, etc.).
   - **Inside view on timeline:** Q3's answer is almost always optimistic. Note it without lecturing.
   - **Risk tolerance shallow:** "can live with it" plus full-time-on-savings warrants a specific runway question — how many months exactly?

7. **Write to state.** Update Founder Profile section completely. Update Starting Point. If a strong case-study analogue surfaced, log it under Competitive Landscape → "Reference analogue" with the lesson distilled.

8. **Recommend next skill** based on Starting Point:
   - No idea → `idea-genesis`.
   - Problem observed / have an idea → `idea-pressure-test`.
   - Talking to customers → `discovery-coach`.
   - Product built, need customers → `outreach-engine`.
   - Customers but stalled → `signal-audit` then `pivot-decision`.

## Outputs

- Writes: Founder Profile section (complete), Starting Point, optional Reference analogue under Competitive Landscape, Session Log entry.
- External resources surfaced at the right moment:
  - For non-technical founders unsure how to build: YC video *Should You Start a Startup* + YC Cofounder Matching.
  - For founders with no domain experience: PG *How to Get Startup Ideas* (founder-market fit section).
  - For founders unsure between archetypes: Dalton's *How to Get and Evaluate Startup Ideas*.

This skill produces no standalone artifacts. The Founder Profile in the state document is the artifact.

## Anti-Patterns Prevented

- Skipping straight to ideas before knowing whether the founder can ship them.
- Generic advice that doesn't account for the founder's real constraints.
- Validating "I have six months" without asking what's actually in the bank.
- Letting founder-market fit gaps slide because the conversation is going well.

## Recommended Next Skills

Per Starting Point answer in step 8 above. Always tell the founder how to invoke: "Type `/skill idea-genesis` to start, or just say 'let's go.'"

## Tone

Senior partner doing intake at office hours. Specific. No softening "great answer!" between questions. When a real gap surfaces (FMF, runway floor), name it directly per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`.
