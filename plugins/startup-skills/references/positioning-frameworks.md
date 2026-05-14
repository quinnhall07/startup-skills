# Positioning Frameworks

Positioning (April Dunford) and strategic narrative (Andy Raskin) — the pre-fundraising step most founders skip. `pitch-deck-structure.md` jumps from problem to ask without an explicit positioning step; this reference fixes that, and feeds the deck, the one-pager, the website, and cold email.

## April Dunford's 10-step positioning

Source: April Dunford, *Obviously Awesome* (2019). The thesis: positioning is a deliberate exercise, not a tagline written by a copywriter. It precedes messaging. Most early-stage founders default to the category they came from, which is almost never the category that makes their product look best.

### The 10 steps

1. **Understand the customers who love your product.** Not all customers — the ones who love it. They reveal what's distinctive. If you have no customers yet, use the strongest signal from `discovery-coach`: the interviews where the prospect leaned in.
2. **Form a positioning team.** Cross-functional. Product + sales + marketing + customer success. At pre-seed, this is the founders and the design partner who keeps coming back.
3. **Align on positioning vocabulary and process.** Definitions before debate. "Competitor," "category," "differentiator" — agree on what these mean before arguing about which is which.
4. **List your true competitive alternatives.** Not just direct competitors. "What would the customer do if you didn't exist?" Almost always includes: build it themselves, hire someone (consultant / agency / VA), do nothing (status quo), spreadsheet + manual process. The status quo is the most common competitor.
5. **Isolate unique attributes.** What only you have. Features, capabilities, distribution access (an existing audience), founder credibility (domain experience), partnerships, data.
6. **Map attributes to value.** Each attribute → benefit → underlying customer need it serves. A feature is not value. "Real-time sync" is a feature; "no one ever has the wrong version of the file" is value.
7. **Determine who cares most.** Best-fit customers are those for whom your unique value is highest-stakes. This is the high-expectation customer (HXC) from `pmf-survey`.
8. **Find your market frame.** What category puts your differentiation in the best light? Sometimes you're a better X in an existing category; sometimes you create a new category. The frame determines who you're compared to.
9. **Layer on trends.** Only when honest and directly relevant. "AI is hot" is not a trend you can ride if your product isn't AI. Trends amplify positioning that's already true; they don't substitute for it.
10. **Capture and share.** Position statement + sales messaging + marketing copy + product naming, all aligned. Positioning that lives in one founder's head is not positioning.

### The Dunford positioning statement template

```
For [best-fit customer segment]
Who [pain or need]
[Product name] is [market category]
That [unique value]
Unlike [primary competitive alternative]
We [primary differentiator]
```

Fill all six lines. If a line is vague ("for businesses who want to grow"), the positioning is not done.

## Andy Raskin's strategic narrative

Source: Andy Raskin, "The Greatest Sales Deck I've Ever Seen" (Medium, 2016), reverse-engineered from Zuora's Series-E sales deck. The thesis: a deck is a story. Stories have a structure that has worked for 4,000 years. Use it.

### The five-act structure

1. **Name the BIG, undeniable shift in the world.** A change in the rules of the game. Specific, recent, irreversible. "Buyers now research before talking to sales." "Software has eaten distribution." "Capital has gotten 10x cheaper." The shift is something the audience already half-believes; you crystallize it.
2. **Show the winners and losers under the new rules.** Some companies are thriving in the new world; others are dying. Name them. The audience now feels stakes.
3. **Tease the Promised Land.** What your customers become when they win under the new rules. Aspirational, specific, customer-centric (NOT product-centric). The Promised Land is a future state of the customer, not a feature list.
4. **Identify the obstacles** between the customer and the Promised Land. Three or four obstacles is the norm. Each one should feel real.
5. **Present your product as the magic gifts** that overcome each obstacle. Now — and only now — you show the product, mapped to obstacles. The product is the means; the Promised Land is the end.

## Where Raskin beats the traditional deck

- **Standard deck**: problem → solution → traction → market → ask. Logical but cold. Reads as a pitch.
- **Raskin**: change → winners/losers → promised land → obstacles → magic gifts. Narrative pulls the audience in. Reads as a worldview.
- Use **Raskin** for fundraising decks, high-stakes external pitches, sales conversations with executives, and the homepage hero.
- Use the **traditional structure** for due-diligence-style detail — investors past the first meeting expect numbers, not a story. `pitch-deck-structure.md` covers this.

The two are not opposed. The Raskin narrative usually occupies slides 1–4; the traditional structure (traction, business model, GTM, team, ask) occupies slides 5–10. The narrative front-loads the *why*; the structure back-loads the *can you execute*.

## Combining Dunford + Raskin

- Dunford produces *who you are*: the position statement, the competitive alternatives, the best-fit customer.
- Raskin produces *the story you tell*: the shift, the Promised Land, the magic gifts.
- Dunford feeds the website's positioning headline, the one-pager's opening line, the cold-email subject line, and the deck's title slide.
- Raskin feeds the deck's opening 3–4 slides, the website's above-the-fold narrative, and the cold-email body.
- Both feed into `artifact-builder` (for the pitch deck and one-pager) and `outreach-engine` (for cold email subject lines and opening paragraphs).

## When positioning needs revisiting

- **PMF survey HXC segment shifted** (per `pmf-survey`). The customers who would be "very disappointed" if your product disappeared are now a different cohort than they were six months ago. The position statement is now describing the wrong person.
- **Competitive landscape changed** — new entrant, incumbent shipped a competing feature, a category leader pivoted. Step 4 (competitive alternatives) needs redoing; everything downstream cascades.
- **Cold-email reply rates dropped despite the same offer.** Positioning goes stale before the offer does. The market's frame of reference moved; your subject line is now answering a question buyers stopped asking.
- **Sales objections converging on a new theme** ("we already have X for that," "we thought this was a Y tool"). The objection pattern tells you what frame the market is putting you in — and whether it's the frame you want. If it's not, you're being mis-categorized and step 8 needs another pass.
- **A new trend emerged that you can honestly ride** (step 9). Rare, but real — generative AI in 2022, remote work in 2020. The trend is a tailwind for positioning that's already true, never a substitute.

### Worked example of the template

```
For   Series B-C tech CFOs
Who   need SEC-format Scope 1-2 emissions reporting but have no
      sustainability team and no time to learn climate accounting
Carbon is   a Scope 1-2 reporting tool (NOT a "sustainability platform")
That  produces the SEC-ready report from utility bills and lease data in 4 hours
Unlike  hiring a Big-Four sustainability consultant ($80K, 6 weeks)
      or buying Persefoni / Watershed (built for enterprise, 3-month onboarding)
We     ship the report this quarter, not next year.
```

Every line is specific. Every line could be wrong (and therefore tested). That's the bar.

## Positioning anti-patterns

- **"Everything for everyone."** Vague positioning kills sales. Be specific about who it's NOT for. The narrower the wedge, the sharper the cut.
- **Category-create when category-fit suffices.** Creating a category is expensive (Drift spent ~$50M); only attempt when no existing category accommodates you. Most founders should pick a sharp frame inside an existing category.
- **Lead with features.** Customers buy outcomes; positioning leads with outcomes and reaches features last (per step 6).
- **Use category language no one uses.** "Decision-intelligence platform" instead of "BI tool" loses sales. Use the customer's vocabulary from `market-intel`.
- **Position against a competitor the customer doesn't think about.** If your buyer has never heard of competitor X, "Unlike X, we…" wastes a slide.

## Concrete anchor examples

- **Superhuman**: positioned as "email for busy executives," not "faster Gmail." Competitive alternative = Gmail + Boomerang plugins + Inbox Zero rituals. Differentiator = speed. Segment = executives whose calendars run their lives. Price ($30/mo) is consistent with the segment, not the category.
- **Drift**: created the "conversational marketing" category. High-cost category-create play; worked because no existing category fit the buyer-side shift Raskin would call the BIG change (buyers research before talking to sales, so the form-and-followup motion is dying). Without that shift, the category-create would have failed.
- **Stripe**: positioned as "payments for developers," not "a payment processor." Competitive alternative = Braintree + manual PCI integration. Differentiator = developer experience (7 lines of code, real docs). The frame chose the audience: every developer who'd ever touched the old APIs was pre-sold.
- **Linear**: positioned explicitly against Jira. Competitive alternative is named on the homepage. Differentiators = speed + design + opinionated workflow. The narrowness is the point — Linear is not "for all teams," it's for product-led software teams that hate Jira.

## Where this is used

- Loaded by the `positioning-narrative` skill, which guides founders through the Dunford 10 steps and Raskin five acts.
- Loaded by `artifact-builder` when producing pitch decks, one-pagers, and websites — to ensure the opening narrative is Raskin-shaped and the positioning statement is Dunford-shaped.
- Loaded by `outreach-engine` for cold-email subject lines (drawn from the position statement) and opening paragraphs (drawn from the Promised Land).
- Loaded by `pitch-deck-structure` when generating decks — slides 1–4 follow Raskin; the title-slide one-liner follows Dunford.

## Sources

- April Dunford, *Obviously Awesome* (2019): https://www.aprildunford.com/books
- Andy Raskin, "The Greatest Sales Deck I've Ever Seen" (2016): https://medium.com/the-mission/the-greatest-sales-deck-ive-ever-seen-4f4ef3391ba0
- Lenny Rachitsky, "Positioning with April Dunford": https://www.lennysnewsletter.com/p/positioning-april-dunford
- Sequoia Capital, "Writing a Business Plan": https://articles.sequoiacap.com/writing-a-business-plan
