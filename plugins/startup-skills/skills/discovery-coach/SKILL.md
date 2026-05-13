---
name: discovery-coach
description: >
  (startup-skills) The most important skill. Use before AND after every customer conversation. Fires on "I'm going to interview users," "I just got off a call," "I need an interview script," or "what should I learn from these conversations." PREPARE mode generates Mom-Test-aligned scripts. DEBRIEF mode classifies every statement by evidence weight, surfaces false signals, and refines the hypothesis.
---

# Discovery Coach

The most important skill in Startup Skills. Bad interviews produce false confidence, which is worse than no interviews. This skill operates in two modes — PREPARE before every conversation, DEBRIEF after every conversation — and refuses to let the founder collect compliments as data.

## When to Activate

- Phrases: "I'm going to interview some users," "I'm talking to a potential customer," "I just got off a call with," "I talked to 5 people," "how should I ask about this," "what should I learn from these conversations," "I need an interview script."
- Whenever the founder is about to have or has just had a customer conversation.
- Auto-fire from `problem-focus` after a hypothesis is formulated.

If the user has not yet identified a hypothesis or ICP, route them to `problem-focus` first.

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — especially confirmation bias and polite customer.
- `${CLAUDE_PLUGIN_ROOT}/references/mom-test-principles.md` — the question-design rules.
- `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md` — for DEBRIEF classification.
- `${CLAUDE_PLUGIN_ROOT}/references/false-signal-detection.md` — the 7 patterns.
- `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md` — for outreach to set up interviews.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Fitzpatrick, Friedman, Dinnr.

## State Document Protocol

Read `STARTUP-STATE.md`; pull hypothesis, ICP, current evidence log. PREPARE mode does not write the Evidence Log; DEBRIEF mode does. Session Log:
- PREPARE: `- [YYYY-MM-DD] discovery-coach (PREPARE) — script generated for <N> interviews, riskiest-assumption focus: <X>`
- DEBRIEF: `- [YYYY-MM-DD] discovery-coach (DEBRIEF) — <N> statements classified, mean weight <X>, <pattern> flagged`

## Mode 1: PREPARE

Ask the user to confirm mode if it's ambiguous. PREPARE runs when the founder has interviews scheduled or about-to-schedule.

1. **Read hypothesis and ICP.** If either is vague, stop and route to `problem-focus`.

2. **Generate a custom 12–18 question interview script** built from `${CLAUDE_PLUGIN_ROOT}/references/mom-test-principles.md`. Required shape:
   - Open-ended, past-behavior focused.
   - NEVER include: "Would you use X?", "Would you pay for X?", "How much would you pay?", "What features would you want?"
   - ALWAYS include some of: "Tell me about the last time you did X." "What did that cost you?" "How are you solving this today?" "How long have you used that?" "Walk me through your workflow yesterday." "Who else is involved?"
   - Sequence: warm-up → context-mapping → workflow-walkthrough → severity / time-cost → commitment ask.
   - End with a behavioral commitment ask: "Would you give me $X to do this manually for a week?" / "Would you introduce me to two others with this problem?" / "Can I sit in on your next <task>?"
   - The script NEVER pitches the idea. Pitching contaminates discovery. If the founder asks for a "section to pitch our solution," refuse and explain the Mom Test rule.

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

4. **Test for the Dinnr false-positive trap.** Did the founder explicitly ask for behavioral commitment in the meeting? If not, every "interest" expressed in the conversation is now suspect — re-rate any 0.3+ classifications down toward 0.0 until commitment data exists.

5. **Update the Evidence Log.** Append rows with date, source (customer name + role), verbatim quote/observation, type (politeness/wishlist/anecdote/time-cost/workflow/commitment), weight, and notes. Append-only — never edit prior rows.

6. **Update the PMF running score.** Recompute mean weight, count of 0.8+ entries, sample-size adequacy. Note the gap to the next stage.

7. **Refine the hypothesis.** Using Lean Startup pivot/persevere logic: did the conversation confirm, refute, or surprise? If surprise, was the surprise about the customer (modify ICP), the problem (modify hypothesis), or the solution (modify offer)?

8. **Bias sentinel pass per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`.** Almost always: confirmation bias (founder minimizing negative quotes), polite customer (founder overweighting positive quotes). Name them.

9. **Recommend next.**
   - If N (targeted ICP conversations) < 20: more interviews. Generate the next 5 prospect names from `outreach-engine` (v0.3 — for now, brainstorm with founder) and re-run PREPARE for the next batch.
   - If N ≥ 5 and signal is converging: route to `signal-audit` for full assessment.
   - If signal is mixed after 10+ interviews: route to `rapid-experiments` (v0.3) for behavioral test — words are not closing it, design a behavioral signal.

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
