---
name: idea-pressure-test
description: Use when the user has a specific idea they want evaluated, stress-tested, or scored. Fires on phrases like "is this a good idea," "what do you think of [idea]," "should I work on this," "evaluate my idea," or whenever the user pitches a concrete concept. Pulls live market research via market-intel. Scores the idea against the YC 10-question framework AND Dalton's 4-criteria rubric (market size, founder-market fit, ease of starting, early market feedback). Aggressively detects tar pits, schlep blindness, and SISP framings. Produces a clear-eyed scored assessment with the single most important gap to close — and is willing to say "this is a tar pit, kill it" when the evidence supports that.
---

# Idea Pressure Test

Steel-mans the idea first, then scores it across Dalton's 4-criteria rubric and the YC 10-question framework — backed by live `market-intel` research. Willing to recommend "kill it" when the evidence supports that. Refuses to treat SISP framings as evaluable.

## When to Activate

- The founder pitches a concrete idea: "I want to build X," "I'm thinking of starting Y."
- Direct request: "is this a good idea," "what do you think of [idea]," "should I work on this," "evaluate my idea," "score my idea."
- After `idea-genesis` for any chosen candidate.

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — confirmation bias, optimism bias, anchoring, schlep blindness, inside view.
- `references/scoring-rubrics.md` — Dalton's 4-criteria rubric AND the YC 10-question framework.
- `references/tar-pit-detection.md` — for the canonical tar pit list and the schlep-vs-tar-pit diagnostic.
- `references/case-studies.md` — for real-world anchor companies.
- `references/external-resources.md` — for the right essays and videos to surface.

## State Document Protocol

Read `STARTUP-STATE.md` to pull the idea, founder profile, and any prior pressure-test attempts. Update Current Hypothesis, Competitive Landscape, and What We Know vs What We've Assumed at completion. Session Log: `- [YYYY-MM-DD] idea-pressure-test — scored <idea> at <composite>, recommendation: <continue/kill/learn>`.

## Process

1. **Pull state.** Idea, founder profile, business archetype, any prior research.

2. **Steel-man first.** Articulate the best version of the idea in 3–5 sentences before any critique. Use the explicit framing: *"Here's the strongest version of what you're proposing: …"* This is not courtesy — if the steel-manned version still fails the rubric, the critique is stronger. The founder should hear their best case said back to them better than they could say it themselves.

3. **Invoke `market-intel`** on the idea if it hasn't been run, or if more than ~30 days have passed since the last run. Pull pain, vocabulary, who's building, what's missing, why-now, failed attempts, tar-pit check.

4. **Score Dalton's 4-criteria rubric** from `references/scoring-rubrics.md` — Market size, FMF, Ease of getting started, Early market feedback. One sentence of reasoning per score. FMF veto-weighted: if FMF < 5, the composite recommendation is constrained regardless of other scores.

5. **Write one paragraph per question of the YC 10-question framework.** From `references/scoring-rubrics.md`. Be concrete. Cite `market-intel` findings or `case-studies.md` analogues where applicable.

6. **Run detection passes.**
   - **Tar pit:** if the idea matches a pattern in `references/tar-pit-detection.md`, name the specific tar pit and the structural reason it fails. Do not soften.
   - **Schlep blindness:** if the founder is dismissing a hard/boring/regulated idea space, surface the schlep counter-frame and Stripe / PlanGrid / Brex analogues from `references/case-studies.md`.
   - **SISP:** if the idea is technology-first ("I want to use AI to do something"), refuse to evaluate as a startup idea. Redirect to `idea-genesis` with a clear note that we don't evaluate Solutions In Search of a Problem.
   - **"No competition is good":** if the founder claims no one else is building this, push back hard. Per Dalton: existing competitors is usually a good sign; no competition usually means no market. Force them to find prior attempts before continuing.

7. **Composite recommendation** per `references/scoring-rubrics.md`:
   - **FMF ≥ 7 AND ≥ 2 other dimensions ≥ 7** → "Worth pursuing. The single most important gap to close before commitment is [X]. Here's a specific test to close it: [Y]."
   - **Tar pit** → "This is a tar pit. Specifically: [structural reason]. Move on. We can take what you've learned here back to `idea-genesis`."
   - **FMF < 5** → "You don't have founder-market fit. Either find a cofounder who does, or change ideas. The system won't help you continue here without an FMF plan."
   - **Otherwise (mixed)** → "Mixed signal. Here are the 2–3 things we'd need to learn before this becomes clear. [List]. Run `market-intel` again, or run a Fake Door to get behavioral data."

8. **Pattern-match anchors.** From `references/case-studies.md`, surface the closest structural analogue and the lesson. "This is structurally similar to [Brex / PlanGrid / Stripe / Magic / etc.]. Here's what worked and what didn't for them: …"

9. **Bias sentinel throughout** per `references/bias-sentinel.md`. Especially confirmation bias and optimism bias on the founder's own scoring — if they push back hard on a low FMF score, ask what specific evidence they have, not how strongly they feel.

10. **Update state.** Update Current Hypothesis with the steel-manned version. Update Competitive Landscape. Add an entry under What We Know vs What We've Assumed for each scored dimension.

11. **Recommend next skill** based on recommendation:
    - Worth pursuing → `problem-focus` to sharpen the hypothesis (ships in v0.2; until then, manually refine in the state doc).
    - Tar pit / no FMF → `idea-genesis` to surface alternatives.
    - Mixed → `market-intel` for a deeper pass, OR `rapid-experiments` (v0.3) for behavioral test.

## Outputs

- Writes to state: Current Hypothesis (steel-man), Competitive Landscape, What We Know vs Assumed, Session Log entry.
- External resources to surface, at the right moment:
  - On the 10-question walkthrough → YC video *How to Get and Evaluate Startup Ideas* (Dalton).
  - On schlep blindness → PG *Schlep Blindness*.
  - On the well metaphor / existing competition → PG *How to Get Startup Ideas*.
  - On tar pit detection → Dalton's tar pit talk.
- **Artifact on request only:** A scored "Idea Assessment Memo" — one-page markdown summary with the steel-man, the rubric scores, the 10-question paragraphs, the composite recommendation, and the gap-to-close. Offer once: "I can produce a scored Idea Assessment Memo if you'd like to share it with a cofounder or investor."

## Anti-Patterns Prevented

- Skipping the steel-man and going straight to critique — the critique reads as bias.
- Hand-waving the FMF question because the idea sounds cool.
- Calling a tar pit "interesting" or "worth exploring" — moral failure.
- Letting the founder use TAM math to justify a thin FMF.
- Saying "no competition is good" without forcing prior-attempt research.

## Recommended Next Skills

Per the recommendation in step 11 above. State the next step explicitly: "Type `/skill <name>` to continue."

## Tone

Per `references/tone-and-stance.md`. Willing to wound. Steel-man first; then say what's true. Use Dalton's framings ("changing your idea constantly is the norm," "existing competitors is usually a good sign") at natural moments. If recommending "kill," do it cleanly — don't pad.
