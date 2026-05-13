---
name: founder-context
description: Use this skill to capture founder context — domain expertise, technical ability, time horizon, business archetype, resource reality, risk tolerance, and starting point. Fires on user messages that introduce personal background, professional history, or constraints — phrases like "I work in," "I've been a," "I can/can't code," "I have X months to try this," "I'm doing this solo/with a cofounder." Also fires when a significant context change is reported (left job, found cofounder, raised money). Runs structured intake one question at a time, AND launches parallel web research on the founder's stated domain in the background. Generates the Founder Profile section of the state document and surfaces 2-3 questions only the founder could answer.
---

# Founder Context

Captures who the founder is, what they know, what they have, and what they're willing to lose. Without this, every later skill speculates. Domain expertise determines what idea spaces are real for this person. Resource reality determines what's possible in the next 90 days. Risk tolerance determines what counts as a real commitment.

## When to Activate

- Right after `orientation` for any new founder.
- Whenever the founder reports a context change: left a job, found a cofounder, raised capital, lost runway, changed time commitment.
- Whenever the Founder Profile section of `STARTUP-STATE.md` is empty, stale (>90 days), or contradicts what the user is now saying.
- On phrases like "I work in," "I've been a," "I can't code," "I have X months," "I'm doing this solo," "I have a cofounder," "I just left my job," "I raised X."

## Required Reading

- `references/state-document-protocol.md` — read/write rules.
- `references/bias-sentinel.md` — scan for founder-market fit gaps, inside view, optimism bias.
- `references/research-playbook.md` — for the parallel domain research.
- `references/case-studies.md` — for pattern-matching the founder to known structures.
- `references/external-resources.md` — for the right reading to surface.

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

3. **Parallel domain research.** As soon as Q1 is answered, launch web research on the stated domain using `references/research-playbook.md`. 4–6 searches across forum pain, review complaints, job postings, and failed-startup retrospectives in the founder's domain. Surface a 4-bullet domain context note alongside the interview. Do not stall the questions waiting for research; let it run.

4. **Pattern-match to case studies.** After the seven questions, compare the profile to `references/case-studies.md`. If there's a strong structural analogue, say so explicitly: "Your background is structurally similar to Tracy Young at PlanGrid — domain expert + technical cofounder, schlep-heavy regulated B2B. Here's what worked for them: …" If no clean match, do a quick web search for fresh analogues rather than force-fitting.

5. **Surface questions only the founder could answer.** From the research, identify 2–3 ambiguities — things the public web cannot resolve. Ask only the founder. Examples: "Reviews say the existing tools fail on X; is X actually what your people complain about, or is it Y?" "Job postings suggest companies hire Z roles to handle this; do those roles in *your* network buy software, or do they build it in-house?"

6. **Bias sentinel pass.** Apply `references/bias-sentinel.md`. Especially watch for:
   - **Founder-market fit gap:** founder lacks domain experience AND can't build. Name it directly. Ask how they plan to compensate (cofounder search, embed in industry, etc.).
   - **Inside view on timeline:** Q3's answer is almost always optimistic. Note it without lecturing.
   - **Risk tolerance shallow:** "can live with it" plus full-time-on-savings warrants a specific runway question — how many months exactly?

7. **Write to state.** Update Founder Profile section completely. Update Starting Point. If a strong case-study analogue surfaced, log it under Competitive Landscape → "Reference analogue" with the lesson distilled.

8. **Recommend next skill** based on Starting Point:
   - No idea → `idea-genesis`.
   - Problem observed / have an idea → `idea-pressure-test`.
   - Talking to customers → `discovery-coach` (v0.2; until then, log interviews manually in Evidence Log).
   - Product built, need customers → `outreach-engine` (v0.3; until then, focus on writing a 50–100 prospect list manually).
   - Customers but stalled → `signal-audit` (v0.2) then `pivot-decision` (v0.4).

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

Senior partner doing intake at office hours. Specific. No softening "great answer!" between questions. When a real gap surfaces (FMF, runway floor), name it directly per `references/tone-and-stance.md`.
