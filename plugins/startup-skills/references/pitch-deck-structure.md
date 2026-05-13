# Pitch Deck Structure

YC's 10–12 slide format for seed-stage decks. Attribution: synthesis of YC's *Demo Day* deck patterns, Sequoia's pitch deck template, and Lenny Rachitsky's analysis of decks that closed rounds. The deck is short, big-text, no-jargon. Traction is the load-bearing element; if there isn't traction, the deck should not be made (`artifact-builder` enforces this).

## The 10–12 slide format

Each slide: one idea, one headline, minimal text. The deck is a conversation prop, not a document.

### 1. Title

- Company name (large).
- One-sentence positioning. "X for Y" or "We do Z so that companies don't have to do W."
- Founder name(s), date, contact.

### 2. Problem

- Specific pain in customer language (verbatim if possible, per `market-intel`).
- WHO experiences it (named ICP from `problem-focus`).
- WHEN it bites (the trigger event).
- What it costs them today (time, money, errors).

NOT: "The world is changing." "Industries are being disrupted." Specific or nothing.

### 3. Solution

- What you built / are building, in one sentence.
- Screenshot or product shot (real, not mocked) if it exists.
- One line on why this solution is non-obvious or hard to copy.

NOT: technical details. NOT architecture diagrams. The solution is the answer to the problem.

### 4. Traction

- The most important slide. If you have it, lead with it. If you don't, the deck shouldn't exist yet.
- Numbers: revenue, customers, growth rate, retention, Sean Ellis score if ≥40%.
- Chart over time if 6+ months of data; single bold numbers if early.
- Logos of named customers if B2B (with permission).
- Verbatim customer quotes if particularly strong (with attribution).

### 5. Market size

- **Modest, bottom-up.** "We sell at $X to Y customers; the addressable cohort is Z." Compute total ARR if you capture the cohort.
- AVOID top-down TAM ("the $400B logistics market"). YC partners and serious investors will dismiss this — top-down TAM is a vanity exercise.
- If the market is structurally small at this archetype, name the path to category expansion (Airbnb started with conference attendees; the path to the broader vacation rental market was named).

### 6. Business model

- Pricing model (subscription / usage / take-rate / etc., per `pricing-frameworks.md`).
- Price point committed.
- Unit economics if available: gross margin, payback period.

### 7. Go-to-market

- Specifically how you'll acquire the first 100 customers (or how you have, if you have).
- Channels — the 3 you'll actually use. Founder-led sales pre-PMF (per `outreach-engine`).
- NOT: a list of all possible marketing channels. Specifics, not options.

### 8. Competition

- A 2D positioning chart (axes that matter for the customer's choice).
- Or a feature matrix.
- Honest about competition (per `idea-pressure-test` — "no competition" is a red flag, not a strength).
- What's your specific insight that competitors don't have?

### 9. Team

- Photos, names, prior companies / roles.
- One line per founder on founder-market fit.
- Notable advisors only if they actually advise.

### 10. Ask

- Round size (e.g., "Raising $X").
- Use of funds (3–4 bullets: hires, runway months, milestones).
- Specific milestone to be hit before the next round.

### 11–12. (Optional)

- Appendix: detailed financials, additional customer logos, demo screenshots, FAQ.
- Don't include unless the conversation calls for it.

## What never to include

- **TAM hand-waving.** "$400B market" without bottom-up reasoning.
- **Exit slides** pre-Series-B. "Acquisition by [BigCo]" or "IPO by 2030" — investors will discount the deck.
- **Long quotes.** Anything > 2 lines of body text per slide. Use the talk, not the slide.
- **Photographs as decoration.** Every image earns its place; no stock photos.
- **Awards lists** ("Featured in TechCrunch"). Not signal.
- **Vague projections.** "We project $10M ARR in year 3." Without basis, this is fiction; with basis, show the basis.
- **A "vision" slide that contradicts the traction.** If traction is 5 customers and the vision slide claims a 100M-user platform, the deck reads as fiction.

## Tone and design

- Sans-serif font (Helvetica, Inter, Söhne).
- One color, one accent color.
- Bullet sparingly; better to repeat the headline pattern across slides.
- Big numbers > paragraphs.

## When to refuse to make a deck

The `artifact-builder` skill refuses to produce a polished pitch deck if PMF stage is pre-signal. The reason: fundraising on speculation is selling fiction; serious investors see through it; the founder time is better spent on `discovery-coach`. The skill states this directly when the founder asks for a pre-signal pitch deck — and offers an alternative ("I can produce a one-pager that captures what we know and what we're testing — that's appropriate at this stage").

## Where this is used

`artifact-builder` uses this structure when producing pitch decks for founders at early-signal or higher stage. The skill marks any section where the state document is thin ("TRACTION: light here — update once Sean Ellis hits 30%+").
