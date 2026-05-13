---
name: idea-genesis
description: (startup-skills) Use when a founder has no idea, is uncertain between multiple ideas, wants to explore a domain, or is generating new candidates. Fires on phrases like "I have no idea," "what should I build," "I want to start something," "exploring," "brainstorming ideas," or "shopping for ideas." Runs two simultaneous tracks: (1) structured interview through the founder's lived experience, past frustrations, things they wished existed, and weird workarounds they currently use; (2) parallel web research on underserved problems in the founder's stated domain (Reddit, forums, G2 reviews, job postings, failed-startup post-mortems, Indie Hackers). Surfaces 5-7 candidate idea spaces with source attribution. Refuses to entertain Solution-In-Search-of-a-Problem (SISP) framings like "AI is cool, what could I apply it to?"
---

# Idea Genesis

Surfaces 5–7 candidate idea spaces grounded in (a) what the founder has actually lived and (b) what the public web reveals about pain in their domain. Refuses Solution-In-Search-of-a-Problem framings outright. Opens with Paul Graham's framing: the verb you want is not "think up" but "notice."

## When to Activate

- Founder explicitly says they have no idea, or have several and can't choose.
- Phrases: "I have no idea," "what should I build," "I want to start something," "exploring," "brainstorming ideas," "shopping for ideas."
- After `founder-context` for any founder routed via Option 1 from `orientation`.

Do NOT activate when the founder is already pressure-testing a specific idea — route to `idea-pressure-test`.

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — schlep blindness, false consensus, anchoring.
- `references/research-playbook.md` — for the parallel research track.
- `references/tar-pit-detection.md` — to flag obvious tar pits as candidates surface.
- `references/case-studies.md` — for pattern-matching candidates to known structures.
- `references/external-resources.md` — for the right essays/videos to surface.

## State Document Protocol

Read `STARTUP-STATE.md`; confirm Founder Profile is rich enough (domain, technical ability, archetype). If sparse, stop and route back to `founder-context`. Update One-Liner candidates and What We Know vs What We've Assumed at completion. Session Log: `- [YYYY-MM-DD] idea-genesis — surfaced <N> candidates across <organic/research/hybrid>`.

## Process

1. **Open with PG framing.** Verbatim or close: "The verb you want is not 'think up' but 'notice.' We're going to surface ideas you already have but haven't named."

2. **Refuse SISP openings.** If the founder says any variation of "AI is cool, what could I apply it to" or "I want to use blockchain / LLMs / whatever for something" — flat redirect: "That's a solution looking for a problem. We're not going to do that. Tell me about a problem you've personally hit at work, repeatedly, that you've had to hack around." Do not continue until they reframe.

3. **Organic track — 7 questions, one at a time.**
   1. "What's your job right now? What part of it makes you swear?"
   2. "What's a tool, file, spreadsheet, or workflow you've cobbled together for yourself because nothing existed?"
   3. "What have you Googled three or more times because you couldn't find a good answer?"
   4. "What do your coworkers complain about that you've stopped hearing because it's so constant?"
   5. "What did you wish existed during the last hard week at work?"
   6. "What's a 'schlep' you've personally endured — boring, tedious, regulated, unsexy?"
   7. "Whose job, in your professional network, looks like it's mostly fighting their tools?"

   Wait between each. The order matters: 1–4 surface lived pain; 5 reframes through wish-it-existed; 6 specifically targets schlep blindness; 7 expands to second-degree network.

4. **Research track — parallel, automatic.** As soon as the founder's domain is named (likely from Q1), launch 5–7 searches via `references/research-playbook.md`. Required search shape:
   - `site:reddit.com {domain} frustration`
   - `{domain} G2 reviews low rating` (substitute a known competitor if one was mentioned)
   - `Indie Hackers {domain}` / `site:indiehackers.com {domain}`
   - `YC alumni {domain}`
   - `failed startup {domain}` and `{domain} post-mortem`
   - LinkedIn job postings: `hiring {role in domain} site:linkedin.com`

   `WebFetch` the 2–3 highest-signal pages. Extract verbatim pain quotes.

5. **Synthesize 5–7 candidate idea spaces.** One sentence each. Tag each as `organic` (from the founder's lived experience only), `research` (from the public web only), or `hybrid` (both).
   - Good form: "Independent dental offices need a better scheduling tool — current ones don't integrate with insurance pre-auth, and reviews repeatedly call this out."
   - Bad form: "Make dentistry better." Reject candidates this vague; rewrite.
   For each candidate, name *one specific potential customer*: a named role, a named company, or — best — a named human the founder already knows who fits the profile.

6. **Bias sentinel pass per `references/bias-sentinel.md`.** Watch for:
   - **Schlep blindness** — if the founder dismisses any of the candidates because they're boring or hard, surface that bias by name and don't let them quietly drop the candidate without engaging.
   - **False consensus** — if a candidate is framed as "everyone has this problem," demand specificity.
   - **Anchoring** — if the founder locks onto the first candidate, force them to weigh at least three before committing.

7. **Surface Dalton's three counter-signals.** From `references/tar-pit-detection.md` and case studies: "Three things that make ideas seem bad but actually make them good — (1) hard to get started; (2) boring space; (3) existing competitors. Take the candidates with those signals seriously, not less seriously."

8. **Ask the founder to pick 2–3.** "Which 2–3 resonate most? We'll take those to `idea-pressure-test`."

9. **Update state document.** Log every candidate (including the not-chosen) under What We Know vs What We've Assumed → "Candidate idea spaces" with the tag and source. Add the chosen 2–3 as One-Liner candidates v1.

10. **Recommend next skill:** `idea-pressure-test` for the chosen 2–3. If the founder is too uncertain even to pick, recommend `market-intel` on the broadest candidate to deepen the research first.

## Outputs

- Writes to state: candidate list under What We Know vs What We've Assumed; chosen 2–3 under One-Liner; Session Log entry.
- External resources to surface, at the right moment:
  - When introducing the "notice, don't think up" framing → PG *How to Get Startup Ideas*.
  - When schlep blindness fires → PG *Schlep Blindness* (short, links well here).
  - When the founder asks "but what kind of idea is good?" → YC video *Where Do Great Startup Ideas Come From*.
- **Artifact on request only:** Idea Candidate Brief — a one-page markdown doc summarizing the 5–7 candidates with source, target customer, and rough hypothesis. Offer once, do not auto-generate: "I can produce an Idea Candidate Brief if you'd like to share it with a cofounder or save it for later."

## Anti-Patterns Prevented

- Solution-In-Search-of-a-Problem ideation.
- Vague "make X better" candidates that can't be tested.
- Quiet schlep-avoidance (rejecting the good ideas as boring).
- Anchoring on the first candidate and skipping pressure-test.

## Recommended Next Skills

- `idea-pressure-test` (default) for the 2–3 chosen.
- `market-intel` (deeper research) if the founder needs more independent evidence before choosing.
- `cofounder-fit` if the candidate clearly demands a team gap the founder cannot self-fill.

## Tone

Per `references/tone-and-stance.md`. Hard on candidate quality, not on the founder. Use Dalton's framings ("existing competitors is usually a good sign," "boring + tedious is the moat") at the natural moments. Do not soften when refusing SISP framings.
