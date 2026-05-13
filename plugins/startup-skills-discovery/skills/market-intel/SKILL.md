---
name: market-intel
description: Use whenever independent web research on a market, problem, customer segment, competitor, or domain is needed. Triggered automatically by other skills (idea-genesis, idea-pressure-test, problem-focus, outreach-engine, rapid-experiments, pmf-audit). Also use directly when the user asks "what's happening in X market," "who else is building Y," "is anyone complaining about Z online," "search for competitors," or "do some research on this." Runs 5-10 targeted searches in parallel using the research playbook — Reddit, G2/Capterra, Crunchbase, Product Hunt, LinkedIn job postings, Indie Hackers, failed-startup forums. Produces a structured market intelligence brief — pain expressed, language used, who's building, what's missing, why-now insight — NOT a full competitive analysis. Refuses to use TAM math as a substitute for behavioral evidence.
---

# Market Intel

Independent web research as a structured brief — pain expressed, exact customer vocabulary, who's building, what's missing, why-now, tar-pit check. Built so other skills can call it as a subroutine, or the founder can invoke it directly. Refuses TAM math as validation.

## When to Activate

- Auto-invoked by `idea-genesis`, `idea-pressure-test`, `problem-focus`, `outreach-engine`, `rapid-experiments`, `pmf-audit` when research is load-bearing.
- Direct invocation phrases: "what's happening in X," "who else is building Y," "is anyone complaining about Z online," "search for competitors," "do some research on this," "find me the players in this space," "what do reviews say about [tool]."

## Required Reading

- `references/state-document-protocol.md`
- `references/research-playbook.md` — query templates and source trust ladder.
- `references/tar-pit-detection.md` — to run the tar-pit check on any idea-space topic.
- `references/case-studies.md` — to surface real-company anchors when relevant.

## State Document Protocol

Read `STARTUP-STATE.md` to know the founder's archetype and current focus. Update Competitive Landscape and What We Know vs What We've Assumed sections with findings. Session Log: `- [YYYY-MM-DD] market-intel — researched <topic>, surfaced <key finding>`.

## Process

1. **Receive a topic** from the calling skill, or extract from the user's direct request. The topic is one of: a domain ("dental scheduling"), a problem statement ("emissions reporting for series-B startups"), a customer segment ("operations leads at construction firms"), or a named company ("PlanGrid").

2. **Construct 5–10 queries** across the seven categories in `references/research-playbook.md`. Required coverage: at least one query per category from forum pain, review complaints, job posting analysis, failed-startup retrospectives, and community language mapping. Additional queries fill out funding activity and adjacent communities when relevant.

3. **Execute searches.** Use parallel `WebSearch` where possible. Then pick the 2–3 highest-signal results (high-engagement Reddit threads, specific G2/Capterra reviews, substantive post-mortems) and `WebFetch` them for substance — do not rely on snippets.

4. **Synthesize a structured brief.** Required fields, in order:
   - **Pain expressed.** 3–5 verbatim quotes from forums or reviews. Each with source (URL or domain).
   - **Vocabulary.** 5–10 *exact words* customers use to describe the problem and the workarounds. Critical for outreach copy and interview scripts. Do not paraphrase — copy the words.
   - **Who's building.** 3–5 named companies/startups in the space. One sentence of positioning per entry.
   - **What's missing.** Gaps in existing solutions, drawn directly from negative reviews and failed-startup post-mortems.
   - **Why-now.** Any recent change — regulation, technology, market shift, demographic — that opens this. If none found, say so explicitly. "No discoverable why-now" is a signal in itself.
   - **Failed attempts.** Post-mortems found, with structural reasons. If three or more failed for the same reason, escalate to **tar-pit warning**.
   - **Tar-pit check.** Cross-reference against `references/tar-pit-detection.md`. If the topic matches a known tar pit pattern, name it and explain why.

5. **Refuse TAM-as-validation.** If during research you encounter top-down TAM figures ("the global X market is $XB"), do not include them in the brief. State explicitly: "TAM excluded — this brief weighs whether 50 specific desperate users exist, not whether the market is theoretically large."

6. **Write to state.** Update Competitive Landscape with the "who's building," "what's missing," and "tar-pit check" findings. Update What We Know vs What We've Assumed with each new fact: column 1 the claim, column 2 status (Known/Assumed/Disproven), column 3 source.

7. **Return the brief** to the calling skill, or render it to the user if direct-invoked.

## Outputs

- Writes to state: Competitive Landscape (existing alternatives + insufficient + why-now), What We Know vs Assumed table updated.
- **Artifact on request only:** Standalone "Market Intelligence Brief" as a clean markdown doc, suitable for sharing with cofounders or saving as a snapshot. Offer once: "I can also produce this as a standalone Market Intelligence Brief if you'd like."

## Anti-Patterns Prevented

- Summarizing summaries — without `WebFetch` the brief is just snippet aggregation, which is noise.
- Treating TAM as evidence.
- Skipping the tar-pit check on idea-space topics.
- Burying customer vocabulary in prose — keep the 5–10 exact-word list as its own bullet so outreach and interview scripts can reuse it verbatim.
- Quietly using vendor press releases or analyst reports as primary sources — the trust ladder demotes them.

## Recommended Next Skills

- Back to the calling skill, almost always.
- When direct-invoked and the brief surfaces a tar pit: route to `idea-genesis` to surface alternatives.
- When direct-invoked and the brief surfaces unexpected strength: route to `idea-pressure-test`.

## Tone

Brisk. No editorializing inside the brief — let the verbatim quotes speak. Editorial happens in the calling skill's response, not here. Per `references/tone-and-stance.md`.
