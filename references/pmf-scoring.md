# PMF Scoring — Sean Ellis 40% Rule + Superhuman Blueprint

The operating reference for `pmf-audit`. The Sean Ellis survey is the leading indicator; Rahul Vohra's Superhuman blueprint is the operational engine that lifts a sub-40% score above the threshold. Marc Andreessen's qualitative complement confirms what Ellis predicts.

Attributions: Sean Ellis (original blog posts, ~2009 onward); Rahul Vohra (First Round Review, *How Superhuman Built an Engine to Find Product/Market Fit*, 2018); Marc Andreessen (*The Only Thing That Matters*, 2007); Brian Balfour (channel-product fit, model-product fit essays).

## The Sean Ellis survey

### The core question

> "How would you feel if you could no longer use [product]?"

Options:
- **Very disappointed**
- Somewhat disappointed
- Not disappointed (it isn't really useful)
- N/A — I no longer use it

### Filtering criteria — non-negotiable

The survey is *only* sent to users who have:
- Used the product at least **twice**
- In the last **14 days** (active users, not lapsed)
- Experienced **core value** (not just signed up)

Surveying the entire email list (including inactives) artificially suppresses the score. Surveying signups who never experienced value also suppresses it. The threshold is meaningful only on active, value-experiencing users.

### Sample size

**Minimum 40 valid responses.** Below 40, the score is too noisy to act on. Aim for 100+ when the user base supports it.

### Computing the score

> **PMF Score = (Very Disappointed / Total Valid Responses) × 100**

- **≥ 40%** → significant. Leading-indicator threshold met. Sustainable growth and paid acquisition are now on the table.
- **< 40%** → not yet. Scaling and paid acquisition are FROZEN. Return to Build-Measure-Learn.

The 40% threshold is the operational gate for every Startup Skills decision that involves spending money on growth. `outreach-engine` refuses paid acquisition below it. `signal-audit` flags any scaling decision against it.

### Survey delivery

- **Tools (per `tool-recommendations.md`):** Tally (free) or Typeform for external delivery. Userpilot or Intercom for in-app surveys (best response rates).
- **Email to users:** short, founder-personal. "I'm working on understanding which users get the most value. Quick 60-second survey, would mean a lot." Single button to the survey. No corporate "we'd love your feedback" framing.
- **Response window:** 1–2 weeks. Send a single reminder at day 7.

## Rahul Vohra's Superhuman blueprint — engineering PMF

When Superhuman first ran the survey, they scored **22%** — well below the 40% threshold. Vohra's team did not launch broadly. Instead, they used the survey *data* to engineer the score upward. They lifted it to **58%** through deliberate segmentation and feature work.

### Segment to the High-Expectation Customer (HXC)

From the "Very Disappointed" cohort, filter by demographic and behavioral profile. Find the pattern. Superhuman's HXC turned out to be founders and executives who lived in their inbox 5+ hours per day. The HXC is the cohort whose love of the product can be replicated.

In `pmf-audit`, the founder identifies the HXC by running cross-tabulations on the "Very Disappointed" cohort:
- Role / job title
- Company size
- Industry
- Use frequency / use depth
- Geography

The HXC is the segment with the highest "Very Disappointed" percentage *within* itself.

### Analyze polarity

For the "Very Disappointed" cohort, ask the open-ended follow-up:

> "What is the main benefit you receive?"

The verbatim answers reveal the core value proposition. The company doubles down on this. For Superhuman, the answer was overwhelmingly **speed**. They built every subsequent feature against speed; everything else was deprioritized.

### Convert fence-sitters

For the "Somewhat Disappointed" cohort, ask:

> "What is holding you back from loving this?"

This dictates the next product roadmap. Build the things that move fence-sitters to "Very Disappointed."

### Ignore the rest

For "Not Disappointed," **ruthlessly discard the feedback.** Building features for users who don't love the product is the most expensive mistake post-PMF. It dilutes the product, slows iteration, and never converts that cohort.

### 50/50 engineering split

After segmentation, polarity analysis, and fence-sitter identification:

- **50% of engineering** expands HXC value (deepens what the cohort already loves).
- **50% of engineering** overcomes fence-sitter objections (converts "Somewhat Disappointed" → "Very Disappointed").

This split is the operational discipline. It runs for as many quarters as it takes to cross 40%.

### Re-run quarterly

PMF is not a one-time measurement. Re-run the survey every quarter. The score should track upward as engineering follows the 50/50 split. If it doesn't, the segmentation is wrong (chose the wrong HXC) or the polarity analysis was misread.

## Andreessen's qualitative complement

Marc Andreessen's *The Only Thing That Matters* describes PMF qualitatively: "You can feel product/market fit when it's happening." Symptoms:

- Servers are melting. You can't keep up with the load.
- The phone is ringing with customer interest you didn't seek out.
- Organic word-of-mouth is the primary acquisition channel.
- Support is overwhelmed by users telling you what to build next.
- Press shows up unbidden.

These are lagging indicators — they confirm what Sean Ellis predicts. If the Ellis score is high but the Andreessen indicators are absent after 6+ months, something is wrong. The most common cause: the HXC is too small a segment to generate the qualitative signals at the company level, even though the cohort itself loves the product. Re-examine TAM for the HXC specifically.

## Where this is used

`pmf-audit` runs the full Sean Ellis + Vohra workflow on user request. `signal-audit` (v0.2) surfaces when the founder is ready to escalate to a full `pmf-audit`. `outreach-engine` (v0.3) uses the 40% threshold as the gate for paid acquisition. `pivot-decision` references the score as input to the continue/adjust/pivot recommendation. `artifact-builder` refuses to produce polished pitch decks below the threshold.
