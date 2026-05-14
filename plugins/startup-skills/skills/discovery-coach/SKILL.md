---
name: discovery-coach
description: |
  Customer-interview prep (Mom-Test-aligned scripts) and debrief (evidence classification + false-signal detection). PREPARE before every interview; DEBRIEF after every one. Refuses to count compliments as data. The most important skill in Startup Skills — bad interviews produce false confidence, worse than no interviews.

  TRIGGER when: user says "interview", "talk to users", "just got off a call", "I talked to N people", "need an interview script", "what should I learn from these conversations"; user is about to schedule customer conversations; user reports a finished customer call; Evidence Log in `STARTUP-STATE.md` has new entries since last `discovery-coach` run.

  SKIP: user has no hypothesis yet (route to `problem-focus`); user wants to fundraise (route to `pmf-audit`); user is post-validation in ongoing cadence (route to `continuous-discovery`); user is asking how to phrase a single question rather than running PREPARE/DEBRIEF mode.
---

# Discovery Coach

The most important skill in Startup Skills. Bad interviews produce false confidence, which is worse than no interviews. This skill operates in two modes — PREPARE before every conversation, DEBRIEF after every conversation — and refuses to let the founder collect compliments as data.

## Mode confirmation (mandatory)

Two modes — PREPARE and DEBRIEF. **Always confirm which mode** before executing:

> "Are you about to interview (PREPARE) or did you just finish one (DEBRIEF)? If you're asking how to phrase a single question, I'll answer briefly without running either mode."

## When to Activate

- Phrases: "I'm going to interview some users," "I'm talking to a potential customer," "I just got off a call with," "I talked to 5 people," "how should I ask about this," "what should I learn from these conversations," "I need an interview script."
- Whenever the founder is about to have or has just had a customer conversation.
- Auto-fire from `problem-focus` after a hypothesis is formulated.

If the user has not yet identified a hypothesis or ICP, route them to `problem-focus` first.

## Red flags

| Founder behavior | Response |
|---|---|
| Asks for a "section to pitch our solution" | Refuse. Pitching contaminates discovery. Cite Mom Test rule 1. |
| Wants to ask "would you pay $X?" | Refuse. Hypothetical pricing = weight 0.0. Replace with behavioral ask. |
| Treats compliments as evidence | Classify as 0.0. Refuse to lobby for higher weights. |
| Skips the behavioral commitment ask | Re-rate the meeting's signals to 0.0 until commitment data exists. |
| Concludes from 3-5 conversations | Small sample fallacy. Below 20 ICP-targeted is not data. |
| Edits prior evidence log entries to look better | Refuse. Evidence log is append-only. |
| Counts Network-Halo signals as ICP signal | Strip network-1 entries; rerun analysis. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — especially confirmation bias and polite customer.
- `${CLAUDE_PLUGIN_ROOT}/references/mom-test-principles.md` — the question-design rules.
- `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md` — for DEBRIEF classification.
- `${CLAUDE_PLUGIN_ROOT}/references/false-signal-detection.md` — the 7 patterns.
- `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md` — for outreach to set up interviews.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Fitzpatrick, Friedman, Dinnr.
- `${CLAUDE_PLUGIN_ROOT}/references/continuous-discovery-patterns.md` — Torres story-based interviewing, OST.
- `${CLAUDE_PLUGIN_ROOT}/references/jtbd-protocols.md` — Switch Interview mode.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md`; pull hypothesis, ICP, current evidence log. PREPARE mode does not write the Evidence Log; DEBRIEF mode does. Session Log:
- PREPARE: `- [YYYY-MM-DD] discovery-coach (PREPARE) — script generated for <N> interviews, riskiest-assumption focus: <X>`
- DEBRIEF: `- [YYYY-MM-DD] discovery-coach (DEBRIEF) — <N> statements classified, mean weight <X>, <pattern> flagged`

## Mode 1: PREPARE

Ask the user to confirm mode if it's ambiguous. PREPARE runs when the founder has interviews scheduled or about-to-schedule.

1. **Read hypothesis and ICP.** If either is vague, stop and route to `problem-focus`.

2. **Generate a custom 10-15 question interview script** built from `${CLAUDE_PLUGIN_ROOT}/references/mom-test-principles.md`. Explicit structure:
   - (1) Warm-up (1-2 Q): rapport, context-setting.
   - (2) Context mapping (2-3 Q): "Tell me about your role, your team, your workflow."
   - (3) Workflow walkthrough (4-6 Q): "Walk me through the last time you [did the behavior]." (Torres story-based form, per `${CLAUDE_PLUGIN_ROOT}/references/continuous-discovery-patterns.md`)
   - (4) Severity / time-cost (2-3 Q): "How long does this take?" "What does it cost?"
   - (5) Commitment ask (1-2 Q): behavioral commitment, NEVER hypothetical.

   - NEVER include: "Would you use X?", "Would you pay for X?", "How much would you pay?", "What features would you want?"
   - ALWAYS include some of: "Tell me about the last time you did X." "What did that cost you?" "How are you solving this today?" "Who else is involved?" "Walk me through your workflow yesterday."
   - The script NEVER pitches the idea. Pitching contaminates discovery.

   **Switch Interview variant**: if the user has recently purchased something in the space (themselves or interviewing a customer who switched), use the 10-phase Switch Interview from `${CLAUDE_PLUGIN_ROOT}/references/jtbd-protocols.md` instead. Switch interviews work post-purchase; Mom Test works pre-purchase.

3. **Outreach to set up the interview.** From `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md`, draft 1–3 outreach messages (warm and cold variants) targeting the ICP. Customize the credibility line and value-prop sentence to the specific recipient.

4. **Identify 3 likely bad questions the founder will ask.** Based on the hypothesis, predict the founder's most-natural-but-wrong questions (almost always hypothetical or feature-focused). Name each, explain why it fails, and give the replacement.

5. **Role-play option.** Offer: "I can play a skeptical, distracted, or polite-but-noncommittal interviewee while you practice. Want to run the script through with me first?" If yes: play the role honestly — disengage after the third leading question, give compliments without substance until pressed for specifics, etc.

6. **Logistics.** Recommend: video call > phone > in-person > text. Recording with permission (Otter, Riverside, Granola). 30 minutes max — never 60.

7. **Set behavioral success criterion *before* the call.** "You'll have learned something useful if you heard X" — where X is behavioral. NOT "if they sound interested." Examples: "If they show you their actual workflow / spreadsheet" or "If they commit to a follow-up by date."

## Mode 2: DEBRIEF

Run immediately after every customer conversation, before the founder's memory degrades.

1. **Dump first.** Ask: "Dump everything you remember from the conversation. Don't synthesize yet — just facts and quotes. Verbatim where possible." Wait. Resist the urge to ask synthesizing questions.

2. **Classify every substantive statement against `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md`.** Per statement: category, weight (0.0–1.0), one-line reasoning. Example:
   - "Sounds cool, I'd use it." → 0.0 / politeness response.
   - "I'd pay $20/month." → 0.0 / hypothetical pricing.
   - "You should add feature Y." → 0.1 / wishlist; note Y as a clue but not as a roadmap input.
   - "Last week I spent 4 hours on this in Excel." → 0.6 / time-cost behavioral.
   - "Here, let me show you our internal spreadsheet." → 0.8 / workflow displacement.
   - "Can I pay you $500 to do this manually next week?" → 1.0 / behavioral absolute.

3. **Apply `${CLAUDE_PLUGIN_ROOT}/references/false-signal-detection.md`.** Run all 7 patterns over the new entries AND the existing log. Especially: Enthusiasm Trap, Network Halo, Polite Customer, Feature Request Mirage. If any fire, name the pattern and the offending entries.

4. **Test for the Dinnr false-positive trap.** Did the founder explicitly ask for behavioral commitment in the meeting? (Money, time, intro, follow-up demo slot, payment intent.)

   - **If NO**: every "interest" expressed is now suspect. Re-rate all 0.3+ classifications down to 0.0 until behavioral commitment data exists. State directly: "You didn't measure demand — you measured politeness."
   - **If YES**: keep the ratings. The behavioral ask is the load-bearing question.

5. **Update the Evidence Log.** Append rows with date, source (customer name + role), verbatim quote/observation, type (politeness/wishlist/anecdote/time-cost/workflow/commitment), weight, and notes. Append-only — never edit prior rows.

6. **Update the PMF running score.** Recompute mean weight, count of 0.8+ entries, sample-size adequacy. Note the gap to the next stage.

7. **Refine the hypothesis.** Using Lean Startup pivot/persevere logic: did the conversation confirm, refute, or surprise? If surprise, was the surprise about the customer (modify ICP), the problem (modify hypothesis), or the solution (modify offer)?

8. **Bias sentinel pass per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`.** Almost always: confirmation bias (founder minimizing negative quotes), polite customer (founder overweighting positive quotes). Name them.

9. **Recommend next.**
   - If N (targeted ICP conversations) < 20: more interviews. Generate the next 5 prospect names via `outreach-engine`. Re-run PREPARE for the next batch, framing the next-riskiest-assumption explicitly: "Last batch tested X. Next batch tests Y (e.g., buyer-vs-user, payment willingness, trigger frequency)."
   - If N ≥ 5 and signal is converging: `signal-audit` for full assessment.
   - If signal is mixed after 10+ interviews: `rapid-experiments` for behavioral test — words aren't closing it.
   - If post-validation: `continuous-discovery` for the weekly cadence.

## Outputs

- PREPARE: an interview script (in chat, or as a markdown artifact on request); outreach drafts; predicted bad questions; success criterion.
- DEBRIEF: Evidence Log rows; PMF score update; refined hypothesis; pattern-detection flags.
- External resources to surface:
  - Before the first interview batch: Rob Fitzpatrick, *The Mom Test* (entire book — the canonical reading).
  - When the founder pitches mid-interview: YC video *How to Talk to User* (Jared Friedman).
  - When attitudinal validation is collecting up: the Dinnr post-mortem.
- **Artifacts on request only:** custom interview script (markdown); debrief synthesis memo with classified quotes (markdown); "lessons across N interviews" pattern document (after 5+ interviews logged).

## Anti-Patterns Prevented

- Including "pitch the idea" in a discovery script.
- Asking "would you pay $X?"
- Counting compliments as evidence.
- Skipping the behavioral commitment ask at the end of every interview.
- Editing the evidence log after the fact to make it look better.
- Drawing conclusions from N < 20 ICP-targeted conversations.
- Letting the founder collect three Network-Halo signals and treat them as triple-evidence.

## Recommended Next Skills

Per Mode 2 step 9. State the next step explicitly: "Type `/skill <name>` to continue."

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. In PREPARE: senior partner coaching, brisk. In DEBRIEF: forensic. The founder will lobby for higher weights — refuse politely but firmly. Diplomatic dishonesty here costs the founder months.
