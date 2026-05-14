# Distribution by Archetype

Some sales/GTM motions work for some products and never for others. Channel-product fit is one of Brian Balfour's Four Fits (product/market, market/channel, channel/model, model/product) — channels don't bend to your wishes; products are built for channels. Pick the motion the archetype rewards or burn runway. Source: Balfour, *Why Product-Market Fit Isn't Enough*.

## Developer tools / API products

**Motion**: free tier (when network effects or aggregated data create real value) + self-serve onboarding + word-of-mouth amplification on Twitter, Hacker News, and GitHub.

**The founder-sales-first exception**: every devtools success story did founder sales *first*, then scaled via product. Stripe ran 12–18 months of "Collison Installation" — the founders personally walking customers through integration, sometimes on the customer's laptop. Twilio did early B2D enterprise sales with Jeff Lawson dialing into Salesforce devs himself. Vercel was founder-led for ~18 months before self-serve dominated revenue. HashiCorp did the same in infra. The pattern: founder sales until 3–5 reference logos exist, *then* let the product carry distribution.

**Why marketing-team marketing fails here**: developers buy on peer recommendations on Twitter, GitHub stars, a Hacker News thread, or a blog post from someone they already follow. A marketing org with a content calendar, paid ads, and lead-scoring pipeline burns budget for zero ROI because the buyer wasn't reachable through any of those surfaces.

## B2B SMB SaaS (Calendly, Notion, Slack early)

**Motion**: Founder-led sales — *not* a sales team — for the first 100 customers. Calendly's Tope Awotona personally onboarded users for years. Notion's Ivan Zhao ran a Discord and did demos. Slack's Stewart Butterfield emailed every early team.

Cold outreach works in this archetype *if* the pain is acute and the message uses the customer's vocabulary (see `market-intel`). Hire a junior salesperson only after 10–20 paying customers at $100+/mo AND founder sales is proven repeatable. Hiring an SDR to fix a broken message just produces more failed conversations.

Pete Koomen's YC advice: pre-sell $1k/mo contracts to 2 agencies *before* writing code. If you can't sell a slide deck to two buyers, the product won't fix that. Source: YC Library, *Enterprise Sales for Founders*.

## B2B mid-market / enterprise SaaS

**Motion**: warm intros + reference customers + AE-led sales. First 5–10 logos come from founder relationships and second-degree network introductions. Stand up a Customer Advisory Board after 10 logos — the CAB becomes the warm-intro engine for the next 50.

Sales cycles of 6–12 months are normal. Custom POCs (proofs-of-concept) are normal. Security questionnaires and SOC 2 reviews are normal. The founder must run the first 10 cycles personally to learn the cadence before delegating to an AE.

**NEVER cold-email blast enterprise.** A reputation destroyed at a F500 buyer stays destroyed across that buyer's career and their LinkedIn network. One sloppy spray-and-pray sequence can foreclose the buyer for years.

## Consumer (Airbnb, Uber, TikTok)

**Motion**: virality with an internal incentive to refer, OR paid acquisition at sufficient scale to compound.

- **Airbnb**: manual seeding (Chesky-as-photographer in NYC, Craigslist cross-posting hacks) until ~500 listings, then network effects took over.
- **Uber**: paid acquisition from day one — VC-backed burn to seed both supply (driver bonuses) and demand (rider credits) simultaneously.
- **TikTok**: paid user acquisition combined with algorithmic retention; ByteDance reportedly spent $1B+ on US user acquisition for Musical.ly / TikTok before the algorithm carried it.

No "founder sales" path exists for consumer. A founder cannot acquire 1M users by hand; the math doesn't close. Either the product self-distributes (k-factor > 1) or capital pays for distribution.

## Marketplace

**Motion**: solve one side at a time, manually, until that side has enough density to attract the other.

- **DoorDash**: restaurants first (supply side). The PaloAltoDelivery.com landing page tested demand; supply was hand-curated.
- **Airbnb**: hosts first. Without 500 listings in a city, no guest searches converted.
- **Uber**: drivers first in each new city — guaranteed-pay shifts until rider demand caught up.

Rule of thumb: ~50 suppliers / ~500 customers on one side before attempting to scale the other. **Liquidity is the only marketplace metric that matters.** Half-built marketplaces fail because liquidity is zero on both sides — neither side stays.

Take rate starts at 15–20% (Uber 20–25%, Airbnb 14–16%, DoorDash 15–30% blended). Adjust based on what each side tolerates without churning.

## Hardware / deep-tech

**Motion**: Kickstarter pre-orders for consumer hardware, OR enterprise pilot contracts for deep-tech / industrial.

Refundable deposit landing pages count as strong demand evidence (weight 0.8 per `evidence-weighting-matrix`) — a buyer who put down $100 has skin in the game beyond a survey response.

Founder demos at trade shows (CES, SHOT Show, Bauma, RSA) beat cold email by 10x. Hardware buyers want to touch the thing and meet the team. Cold emails about hardware are filtered out as spam by category.

YC's current RFS (Request for Startups) has explicit hardware focus from partners Diana Hu, Nicolas Dessaigne, Tyler Bosmeny, and Philip Johnston — hardware is back inside the YC thesis after a decade of pure-software dominance.

## AI agent products (2025–2026)

**Motion**: vertical AI sold to specific named industries via founder-led demos.

- **Sierra** (Bret Taylor): customer service agents, founder-led enterprise sales.
- **Harvey**: legal AI, founder-led to AmLaw 100 firms.
- **Mercury** (and AI-banking peers): vertical onboarding via founder relationships.
- **Lyzr** and other vertical-agent companies: same founder-led B2B sales until 10+ logos.

Distribution-as-moat matters more in AI than in any prior wave: the model layer is commodifying fast, so the durable advantage is the embedded workflow, the data feedback loop, and the buyer relationship. Per Andrew Chen's *Revenge of the GPT Wrappers* — wrapper companies win when they own a regulated vertical's distribution, lose when they sit on top of someone else's UX.

"Workflow embedding" + "regulated-industry trust" beat raw UI advantages. A clunky agent inside Epic beats a beautiful agent that no hospital will install.

## Content / community / creator-economy (Substack, newsletters, Discord)

**Motion**: founder builds the audience first, the product second. The pre-existing audience is the distribution moat; without it, the product launches into silence.

Per Rob Fitzpatrick's *The Embedded Entrepreneur*: 2–4 weeks of *listening* inside the target community before any pitch — read every thread, learn the in-group vocabulary, surface what people repeatedly complain about. Then participate. Then offer.

Monetize at ~1k engaged subscribers minimum — Kevin Kelly's "1000 True Fans" floor. Below that, the audience is too thin to support paid product economics regardless of conversion rate.

## What fails for each archetype

| Archetype | What NOT to do | Why |
|---|---|---|
| Devtools | Outbound sales team; trade-show booths | Developers actively distrust sales and avoid sponsored booths |
| B2B SMB | Hiring an SDR before PMF; paid Google ads | CAC will exceed LTV; SDR amplifies a broken message |
| Enterprise | Cold-email blasts; free trials without legal review | Burns reputation permanently; trials trigger procurement and security gates |
| Consumer | Founder-led 1:1 sales | Cannot scale to N millions of users by hand |
| Marketplace | Building both sides simultaneously | Liquidity stays zero on both sides; both churn |
| Hardware | "Build it and they will come" — assume demand without pre-orders | Manufacturing capital lost on inventory that doesn't sell |

## Cross-cutting anti-patterns (any archetype)

- **Press as acquisition** — a TechCrunch piece generates curiosity, not customers. Conversion from press to paying user is typically <1% and the cohort churns fast (see Magic case in `case-studies.md`).
- **Networking-as-procrastination** — attending events, going on podcasts, posting threads — anything that *feels* like distribution work but never asks a specific named person for money. The tell: zero scheduled discovery calls on the founder's calendar this week.
- **Paid acquisition pre-PMF** — burns runway and pollutes the PMF signal. Paid users behave differently from organic; you can't read the retention curve. Per Gustav Alstromer and Sean Ellis: no paid acquisition until the `pmf-audit` Sean Ellis survey crosses 40%.

## Where this is used

Loaded by `outreach-engine` (to pick the motion before computing funnel math), `pricing-model` (motion determines whether $99/mo self-serve or $50k/yr ACV is the target), `signal-audit` (which signals count for which motion), `idea-pressure-test` (does the proposed motion match the archetype?), and `mvp-architect` (build the channel-shaped MVP, not a generic one).

## Sources

- Brian Balfour, *Four Fits for $100M+ Growth*: https://brianbalfour.com/essays/product-market-fit-isnt-enough
- YC Library, Pete Koomen, *Enterprise Sales for Founders*: https://www.ycombinator.com/library/LF-enterprise-sales-for-founders
- YC Library, Gustav Alstromer, *How to Get Your First Ten Customers*: https://www.ycombinator.com/library/9h-how-to-get-your-first-ten-customers
- Andrew Chen, *Revenge of the GPT Wrappers*: https://andrewchen.substack.com/p/revenge-of-the-gpt-wrappers-defensibility
- Lenny Rachitsky, *How the most successful B2B startups got their first customers*: https://www.lennysnewsletter.com/p/how-the-most-successful-b2b-startups
- Rob Fitzpatrick, *The Embedded Entrepreneur*: https://www.embeddedentrepreneur.com/
