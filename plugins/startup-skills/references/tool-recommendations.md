# Tool Recommendations

*Pricing/availability current as of May 2026. Verify in-product before committing.*

Tool-agnostic recommendations for pre-PMF founders. The pattern: start with the lowest-friction free or cheap option; don't adopt enterprise tools for problems you don't yet have. Every category lists when to use, when to skip, and the tier most relevant for early-stage.

## Outbound prospecting

| Tool | When to use | Skip when |
|---|---|---|
| **Apollo.io** | Default for B2B outbound prospect list building (free tier: ~10K records, $49/mo for serious use) | You only need ~50 prospects (just LinkedIn search + spreadsheet) |
| **Hunter.io** | Finding email addresses for named prospects ($34–149/mo) | The contact info is in the prospect's LinkedIn bio already |
| **Clay.com** | Combining multiple data sources at scale, automation-heavy ($149+/mo) | Pre-PMF — overkill until you're sending 500+ emails/week |
| **LinkedIn Sales Navigator** | When the ICP requires advanced filters not in free LinkedIn ($99/mo) | Free LinkedIn search covers it (often it does) |
| **Smartlead** | Modern cold email at scale ($59-159/mo). Best deliverability + multi-inbox rotation post Feb 2024 rules | Pre-PMF — overkill until you're sending 200+ emails/week. |
| **Instantly** | Faster setup, built-in 160M B2B DB ($30-97/mo) | Same as Smartlead. |
| **Mailforge / Mailreef** | Domain hygiene + warmup ($16-50/mo per domain) | Avoid if using primary domain only. |

**Recommendation for v0.1 outreach:** Apollo + a spreadsheet. Build a list of 50–100 named individuals manually. CRM later.

## CRM

| Tool | When to use | Skip when |
|---|---|---|
| **Spreadsheet (Airtable, Google Sheets)** | Pre-PMF, <50 active prospects | Above 50 active, columns become unmanageable |
| **HubSpot CRM** | Free tier still useful but increasingly throttled in 2026 (contact limits, automation gating, email send caps tightened); switch to it once spreadsheet creaks but expect friction | Pre-PMF and <50 prospects — overkill |
| **Pipedrive** | Lightweight CRM, $14–49/mo. Best for founders who want pipeline visualization | Spreadsheet is still working |
| **close.com** | Sales-focused, $49–149/mo. Best when you'll do high-volume calling | You're not making 20+ calls/week |

**Recommendation:** Spreadsheet first. Migrate to HubSpot when you outgrow it (free tier handles ~1M contacts technically; in practice migrate around 100 active deals).

## Survey

| Tool | When to use | Skip when |
|---|---|---|
| **Tally** | Free, simple forms. Default for pre-PMF surveys including Sean Ellis. Note: now under Jotform (acquired); performance/feature parity may vary | You need advanced logic |
| **Google Forms** | Free, ugly. Acceptable but signals "not serious" | You're asking customers; aesthetics matter |
| **Typeform** | $25–83/mo. Polished, conversational style; higher completion rates | Cost matters more than aesthetics |
| **Userpilot / Intercom** | In-app surveys for active product users | No deployed product yet |

**Recommendation:** Tally for the Sean Ellis survey (see `pmf-scoring.md` in v0.4). Typeform when the survey is going to customers in a sales context.

## Landing page

| Tool | When to use | Skip when |
|---|---|---|
| **Carrd** | One-page Fake Door, $19/year–$99/year (tiered). Default for the fastest signup page | You need anything beyond one page |
| **Framer** | $5–25/mo. Best for designed-looking landing pages | The page is throwaway |
| **Webflow** | $14–39/mo. Best when you'll iterate the page many times | Carrd or Framer covers it |
| **Next.js + Vercel** | When the landing page becomes the product onboarding | Pre-product fit |
| **WordPress** | Almost never | Almost always |

**Recommendation:** Carrd for Fake Doors. Framer or hand-coded HTML for first product landing page.

## Email (transactional + marketing)

| Tool | When to use | Skip when |
|---|---|---|
| **Customer.io** | Lifecycle / behavioral email triggered by product events ($200+/mo) | Pre-PMF, no event triggers yet |
| **Mailchimp** | Free tier handles ~500 contacts. Default for a small list | Above 2,500 contacts; pricing scales unfavorably |
| **SendGrid** | Transactional email at scale, free for 100/day | Pre-product transactional volume |
| **Mailerlite** | Mailchimp alternative with better pricing | Already on Mailchimp |
| **Beehiiv / Substack** | Newsletter format | Sending product emails, not a newsletter |

**Recommendation:** Mailchimp free tier for a small list, until you have product events worth triggering on. Don't adopt Customer.io until there's a product.

## Analytics

| Tool | When to use | Skip when |
|---|---|---|
| **Plausible** | Privacy-friendly site analytics, $9–69/mo. Default for landing pages | Free tier of Google Analytics covers it (it does for most pre-PMF) |
| **PostHog** | Product analytics + feature flags, generous free tier | No product yet |
| **Mixpanel** | Mature product analytics, free tier ~20M events | PostHog covers it better at this stage |
| **Google Analytics 4** | Free site analytics, ugly | Want better UX (Plausible) |

**Recommendation:** Plausible for marketing pages. PostHog once product launches.

## Payment

| Tool | When to use | Skip when |
|---|---|---|
| **Stripe** | Default for everything. Cards, subscriptions, invoicing, marketplace | Almost never |
| **Lemon Squeezy** | Merchant of Record (handles tax/VAT globally). 5% + $0.50 per transaction | Stripe + a tax service (Stripe Tax) is cheaper above ~$100K ARR |
| **Paddle** | Merchant of Record for digital products. ~5% | Same as Lemon Squeezy |
| **Gumroad** | Digital downloads, courses, one-off products. ~10% | You're doing SaaS |

**Recommendation:** Stripe for SaaS. Lemon Squeezy for early-stage digital products under $100K ARR (handles tax compliance).

## AI build stack (2026)

| Tool | When to use | Skip when |
|---|---|---|
| **Lovable** | Best polish for landing pages + UI MVPs. Supabase integration. $20-50/mo. No SQL direct. | Production code with PII / payments / auth. |
| **Bolt.new** | Fastest prompt-to-deploy. $20-100/mo. | Past 3-5 components — code quality degrades sharply. |
| **Cursor** | Default for serious code. $20/mo Pro ($20 credit), $200/mo Ultra. | When team has no AI-IDE workflow yet. |
| **Claude Code** | The other serious option. Subscription-based, predictable pricing. | If you need IDE-native multi-file refactor. |
| **Replit Agent** | Autonomous long-running prototypes. $25/mo subscription BUT **pricing is unpredictable** — set hard budget cap (some founders report $600+ burns in days). | Cost-sensitive founders. |
| **v0** | Falling behind 2025-2026; not recommended for production. | Default skip. |

**Recommendation by MVP shape** (cross-reference `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` vibe-vs-craft gate):
- Landing/Fake Door: Carrd, Framer, or Lovable.
- Internal-tool prototype: Replit Agent or Lovable.
- Consumer mobile MVP: Cursor + Expo (production); Lovable for landing.
- B2B SaaS MVP (auth, payments, PII): **Cursor + Claude Code only**. Vibe-coding banned.
- Regulated industry: **Cursor + Claude Code with audit trail mandatory**.
- AI agent product: **Cursor + Claude Code**, AI infra stack.

## Cold email infrastructure (2026)

Post-Feb 2024 Gmail/Yahoo bulk-sender rules + Nov 2025 enforcement, cold email requires:

| Component | Recommendation |
|---|---|
| **Sending domains** | Buy 3-10 secondary domains (e.g., `try-acme.com`, `get-acme.com`). NEVER burn primary. |
| **Mailboxes** | Google Workspace or Microsoft 365 inboxes you own outright. 2-3 mailboxes per domain. ~30-50 emails/mailbox/day max. |
| **Warmup** | 2-6 weeks before sending. Mailreef, Mailforge, Warmforge, or Smartlead's built-in. |
| **Authentication** | SPF + DKIM + DMARC mandatory. Start `p=none`, escalate to `p=quarantine` then `p=reject`. |
| **Sending tool** | Smartlead (best deliverability/multi-inbox) or Instantly (faster setup). |
| **Data** | Apollo (seed list, $49/mo) → Clay (waterfall enrichment + AI personalization, $149/mo) → NeverBounce/ZeroBounce (verification, ~$10 per 10k). |
| **List-Unsubscribe** | One-click header (RFC 8058) mandatory. |
| **Spam complaint rate** | ≤0.3% (Gmail recommends <0.1%). |

**Reply rate benchmarks** (custom domain + Outlook): 5.9% strong; Gmail: 3.5% strong; webmail: 1.2-2.1% strong.

For full deliverability protocol, load `${CLAUDE_PLUGIN_ROOT}/references/distribution-by-archetype.md`.

## LinkedIn outbound (2025-2026)

| Component | Recommendation |
|---|---|
| **Connection requests** | ~100/week hard cap (algorithm penalty above). Personalized note (9.36% reply rate). |
| **Sales Navigator** | $99/mo. Use for filter precision + 50 InMail credits/month. |
| **InMail** | 18-25% reply for personalized; reserve for high-priority. |
| **DM (after connecting)** | 5-15% reply rate; depends on relationship. |
| **Content strategy** | Comment-first (30-80 word comments on ICP posts) before posting your own. Personal profile > company page. Document carousels: 6.60% engagement. |

## Signal-based outbound (intent data)

| Tool | Best for | Cost |
|---|---|---|
| **Common Room** | Hiring + news + job-change signals. 150M jobs + 8M news daily. | Mid-market |
| **Clay** | Combining signals + AI personalization | $149+/mo |
| **6sense** | Enterprise intent + ABM | $50k+/yr — overkill pre-PMF |
| **Free signals** | BuiltWith, Crunchbase, LinkedIn job listings, GitHub stars | Free |

**Recommendation pre-PMF**: free signals + Clay/Apollo workflow. Skip 6sense.

---

## CMS / docs / blog

| Tool | When to use | Skip when |
|---|---|---|
| **Notion** | Public docs, blog, lightweight CMS — fast to publish | You need SEO control |
| **Ghost** | Newsletter + blog ($9–199/mo) | Substack or Beehiiv simpler |
| **MDX / Astro / Hugo** | Self-hosted static blog, full control | Maintenance overhead |
| **Webflow CMS** | Marketing site with editorial workflow | Notion is faster |

**Recommendation:** Notion for early docs and blog. Migrate when SEO becomes load-bearing.

## What this list deliberately omits

- **HRIS / payroll / legal** tools — not pre-PMF concerns.
- **Customer support tools** (Intercom, Zendesk) — overkill; founders should be in customer email directly pre-PMF.
- **Project management** (Linear, Asana, Jira) — pre-team, pick whatever the team uses; this is not a startup-relevant decision.
- **Design tools** (Figma) — universal default; not worth recommending.

## Where this is used

`rapid-experiments` recommends specific tools for each experiment type. `outreach-engine` recommends prospecting + CRM stack. `pricing-model` references payment options. `pmf-audit` (v0.4) references survey tools.
