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

## Brian Balfour — Four Fits framework

PMF alone is insufficient for $100M scale. The Four Fits ([Reforge](https://brianbalfour.com/essays/product-market-fit-isnt-enough)) extend the lens:

1. **Market ↔ Product** — desperate desire from a meaningful segment (the Sean Ellis test).
2. **Product ↔ Channel** — products are built for channels; channels don't bend. A product requiring education rarely fits viral or SEO channels.
3. **Channel ↔ Model** — high-touch sales needs high ARPU to amortize CAC; PLG needs low-friction monetization.
4. **Model ↔ Market** — does the segment prefer to pay this way? (B2C subscriptions, B2B annual contracts, marketplace take-rate, etc.)

When growth stalls despite "good product," misfit is almost always one of the latter three. Each fit changing forces re-evaluation of the others.

## Retention curves as leading indicator (Casey Winters)

**PMF = flattened retention curve on key action at appropriate frequency + MoM growth in new-user cohorts.** ([Casey's Guide to Finding PMF](https://www.caseyaccidental.com/p/caseys-guide-to-finding-product-market-fit))

Protocol:
1. Define ONE key action (Pinterest: save; Grubhub: order; Slack: send message in shared channel).
2. Define natural frequency (weekly for utility, monthly for transactional, daily for communication).
3. Plot cohort retention by signup month, % performing key action over time.
4. Look for flattening within <12 months. If the curve still decays at month 12, no PMF.

For deeper retention diagnostics, load `${CLAUDE_PLUGIN_ROOT}/references/retention-metrics.md`.

## Andrew Chen — Power User Curve (L7 / L28)

Histogram of users by number of active days in 28-day window ([Andrew Chen, Power User Curve](https://andrewchen.com/power-user-curve/)):

- **Smile curve** = mass at 1 day (newbies) + mass at 27-28 days (power users). Healthy.
- **Frown curve** = mass in the middle, no power-user tail. No PMF; nobody loves it enough to use it constantly.
- **Facebook reference**: 60%+ of MAUs return daily.

Andrew Chen's three "magic metrics":
1. Flattening cohort retention.
2. Actives / registered > 25%.
3. Smile-shaped power user curve.

## PMF Treadmill / Collapse (Winters + Mosavat + Balfour)

PMF is **not static**. Expectations rise — exponentially under AI ([Reforge: PMF Collapse](https://www.reforge.com/blog/product-market-fit-collapse)):
- Chegg lost ~87% valuation when ChatGPT/AI Overviews reset user expectations overnight.
- Stack Overflow traffic collapsed when LLMs satisfied the core JTBD.

**AI-substitution test**: "Is your core JTBD now achievable in ChatGPT/Claude in <30 seconds?" If yes, you're on the treadmill. Re-segment to HXC for whom your differentiation still holds, OR pivot.

## Andreessen qualitative signals — operationalized

Translate "I know it when I see it" into detectable observables:

**PMF present:**
- Usage growing faster than you can add capacity (servers, seats, support).
- Sales cycles collapse to "yes, here's my card" within one meeting. **Operational test:** median sales-cycle length shrinks 20-40% over 90 days ([Mercury: Measuring PMF](https://mercury.com/blog/measuring-product-market-fit)).
- CS team permanently behind on inbound.
- Inbound press / recruiting / investor DMs arrive unsolicited.
- Word-of-mouth spreading without prompting — track via "How did you hear about us?" free-text. ≥30% "from a friend/colleague" = real organic share. 50-70% = strong PMF.

**PMF absent (anti-signals):**
- Reviewers say "interesting" or "promising" (Andreessen: "kind of blah").
- Deal cycles *lengthen* instead of shorten.
- Each new customer requires bespoke customization to close.
- You can't name 3 customers who would scream if you shut down tomorrow.

**Anti-self-deception protocol**: if you're explaining *why* growth is slow with narrative ("market not ready," "education problem," "long sales cycle is normal for our segment"), you don't have PMF. PMF doesn't need an explanation.

## Anti-PMF signals table

| Signal | Diagnostic |
|---|---|
| Customers say "I love it" but don't refer | Talk is cheap; track actual referrer share, not testimonials. <30% organic = no real love. |
| High activation, low retention | Activation flow hacking dopamine, product doesn't deliver. Check D30/D1 ratio. |
| Churn reasons = "got busy / priorities shifted" | Polite for "not valuable enough." Real PMF gets prioritized through busy. |
| Sales cycles lengthening | Positioning breaking, or chasing wrong ICP. |
| Pricing pushback intensifying | Value perception decoupling from cost. Either competitor matched you or expectations rose (treadmill). |
| Bespoke customization required per deal | "Service masquerading as product." Marginal CS cost should decrease, not stay flat. |
| NRR below 90% | Anti-PMF regardless of sales velocity. ([First Round Levels](https://www.firstround.com/levels)) |
| Champion-dependent renewals | If champion leaving = churn, product hasn't earned organizational love. |
| Narrative-as-explanation for flat metrics | PMF doesn't need narrative. |

## AI-product PMF specifics (token-cost-aware)

Top-of-funnel signups *lie* in AI because COGS scales with usage. New tests:
- **LTV / inference-cost ratio ≥ 3x.** If a power user's annual COGS exceeds 1/3 of their ARR, unit economics collapse at scale.
- **Margin per active user trend.** Should *improve* with cohort age. Flat or declining = no real moat.
- **Cost-per-retained-user**, not cost-per-signup, as the acquisition KPI.

**Calling BS on "vibes-based" PMF claims**:
- Twitter screenshots ≠ retention. Demand cohort data.
- "$X ARR in Y days" with no D30/D90 retention disclosed = almost always anti-PMF (paid acquisition + novelty).
- "Users love it" without VD% on a Sean Ellis survey = unfalsifiable.
- If the product would die when the base model improves 20%, it has model-PMF, not product-PMF.

For full AI-era PMF anti-patterns, load `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md`.

## First Round's "Levels of PMF"

| Level | Sean Ellis | ARR | NRR | Notes |
|---|---|---|---|---|
| Pre-PMF | <30% | <$1M | <90% | Building/iterating |
| Nascent | 30-40% | $1-3M | 90-100% | Approaching threshold |
| Developing | 40-50% | $3-10M | 100-110% | Threshold met, scaling experiments |
| Strong | 50-60% | $10-30M | 110-120% | Scaling channels |
| Extreme | >60% | >$30M | >120% | Category-defining |

Source: [First Round Levels of PMF](https://www.firstround.com/levels).

## Where this is used

`pmf-audit` runs the full Sean Ellis + Vohra workflow on user request. `signal-audit` (v0.2) surfaces when the founder is ready to escalate to a full `pmf-audit`. `outreach-engine` (v0.3) uses the 40% threshold as the gate for paid acquisition. `pivot-decision` references the score as input to the continue/adjust/pivot recommendation. `artifact-builder` refuses to produce polished pitch decks below the threshold.
