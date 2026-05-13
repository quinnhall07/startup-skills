# False Signal Detection

Seven false-signal patterns that masquerade as validation. Every founder produces several of these per month. The job of `discovery-coach` (DEBRIEF) and `signal-audit` is to identify them by name and refuse to count them as evidence.

Sources: synthesis of Fitzpatrick (*The Mom Test*), Sean Ellis (PMF posts), Brian Balfour, and the CB Insights / First Round post-mortem corpus.

## 1. The Enthusiasm Trap

**Symptoms.** Customer reports were uniformly positive. Multiple "I love that you're working on this," "this is exactly what I need," "let me know when it ships."
**Why it fires.** Customers want to be supportive, especially of an obviously hard project. Enthusiasm is a social lubricant, not an economic signal.
**Detection question.** What did each enthusiastic person *do* after the meeting? Pay anything? Make an introduction? Send a follow-up?
**Response.** "Enthusiasm without follow-through is weight 0.0. We need behavioral evidence. Go back to the most enthusiastic people and ask for a specific commitment — money, time, or an internal referral. If they say no when the cost is real, you know."

## 2. The Small Sample Fallacy

**Symptoms.** Conclusions drawn from 3–5 conversations. "Everyone I talked to said…"
**Why it fires.** Three conversations feel like a meaningful sample to a founder under time pressure. Tversky and Kahneman called this the "law of small numbers" — the unwarranted belief that small samples reflect the larger population.
**Detection question.** How many ICP-targeted conversations? (Not "people I talked to" — specifically inside the target customer profile.)
**Response.** "Three is not data. Minimum threshold for conclusions is 20 ICP-targeted conversations. You're at <N>. Until then, every conclusion is a hypothesis, not a finding."

## 3. The Launch-Day Spike

**Symptoms.** Big traffic / signup / press spike around launch. Hacker News, Product Hunt, Twitter virality.
**Why it fires.** Launch creates curiosity, not demand. The cohort that signed up at launch was responding to novelty; their retention 30 days later is the actual signal.
**Detection question.** What's the W4 retention on the launch cohort? What percentage of launch-day signups have used the product twice?
**Response.** "Launch spike is curiosity, not PMF. Wait for retention data. If W4 retention on the launch cohort is below your archetype's benchmark, the spike was noise. Read Andreessen's qualitative-PMF post for the right things to look for instead."

## 4. The Network Halo

**Symptoms.** Strong positive signal — from friends, ex-colleagues, your spouse's coworkers, your YC batch.
**Why it fires.** Your network is biased toward you. They want to support you. They are not your customer. Their feedback is a different kind of data than feedback from people who don't know you.
**Detection question.** Who in your evidence log is in your second-degree network or closer? Strip those rows. What remains?
**Response.** "Discount network feedback. Run the same conversation with a 0-degree stranger from the same ICP. If they say the same thing, your network is signal. If they don't, your network is the halo."

## 5. The Polite Customer

**Symptoms.** Specific past quotes that sound positive — "they said they'd love it," "they seemed really interested" — but no commitment in the room.
**Why it fires.** Politeness is the default human response to a stranger pitching them an idea. Without an explicit ask for commitment, the customer never has to disappoint you, so they don't.
**Detection question.** What did you specifically ask them to commit to in the meeting? Money? Time? An introduction? What was their response?
**Response.** "If you didn't ask for commitment, you didn't measure demand — you measured politeness. Run the meeting again with a specific ask: 'Would you give me $X to do this manually for a week?' or 'Would you introduce me to two other people?' Politeness collapses against an ask."

## 6. The Feature Request Mirage

**Symptoms.** Customers happily list features they'd want. The founder maps each request to product backlog.
**Why it fires.** When you ask "what would you want?", customers are eager to help — and customers don't know what they want until they see it. The wishlist is the customer doing the founder's job badly.
**Detection question.** Behind the requested feature, what *behavior* is the customer trying to perform that they can't perform today?
**Response.** "Feature requests are not roadmap. They are clues about the underlying job. Drill: 'When you say you'd want X, walk me through the last time you needed to do that thing. What did you do instead?' That answer is signal. The feature name is noise."

## 7. Press / Social Attention as Demand

**Symptoms.** Article placement, viral tweet, popular post on r/startups, follow count up.
**Why it fires.** Attention metrics correlate weakly (or not at all) with paying-customer acquisition. Press coverage generates curiosity from the wrong people — other founders, journalists, lookers. Conversion to paid is brutally low.
**Detection question.** From the last <attention spike>, how many paying customers were acquired? What's their LTV?
**Response.** "Press is not demand. The cohort that comes from press is overwhelmingly tire-kickers. Track conversion from each press-driven touchpoint to a paying customer. If that ratio is <1%, press is a distraction from the GTM motion you should be running."

## How `discovery-coach` and `signal-audit` use this

After each interview debrief, run the seven-pattern scan over the evidence log — not just the new entries. False signals frequently compound; a founder will collect three Enthusiasm-Trap inputs in a row and become more confident, not less, when in fact each new false signal reduces total signal quality (because the founder is now triple-anchored on noise).

Name the pattern. Show the offending entries. Strip or downgrade weights. Continue.
