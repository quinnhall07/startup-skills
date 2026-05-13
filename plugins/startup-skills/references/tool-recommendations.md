# Tool Recommendations

Tool-agnostic recommendations for pre-PMF founders. The pattern: start with the lowest-friction free or cheap option; don't adopt enterprise tools for problems you don't yet have. Every category lists when to use, when to skip, and the tier most relevant for early-stage.

## Outbound prospecting

| Tool | When to use | Skip when |
|---|---|---|
| **Apollo.io** | Default for B2B outbound prospect list building (free tier: ~10K records, $49/mo for serious use) | You only need ~50 prospects (just LinkedIn search + spreadsheet) |
| **Hunter.io** | Finding email addresses for named prospects ($34–149/mo) | The contact info is in the prospect's LinkedIn bio already |
| **Clay.com** | Combining multiple data sources at scale, automation-heavy ($149+/mo) | Pre-PMF — overkill until you're sending 500+ emails/week |
| **LinkedIn Sales Navigator** | When the ICP requires advanced filters not in free LinkedIn ($99/mo) | Free LinkedIn search covers it (often it does) |

**Recommendation for v0.1 outreach:** Apollo + a spreadsheet. Build a list of 50–100 named individuals manually. CRM later.

## CRM

| Tool | When to use | Skip when |
|---|---|---|
| **Spreadsheet (Airtable, Google Sheets)** | Pre-PMF, <50 active prospects | Above 50 active, columns become unmanageable |
| **HubSpot CRM** | Free tier is genuinely generous; switch to it once spreadsheet creaks | Pre-PMF and <50 prospects — overkill |
| **Pipedrive** | Lightweight CRM, $14–49/mo. Best for founders who want pipeline visualization | Spreadsheet is still working |
| **close.com** | Sales-focused, $49–149/mo. Best when you'll do high-volume calling | You're not making 20+ calls/week |

**Recommendation:** Spreadsheet first. Migrate to HubSpot when you outgrow it (free tier handles ~1M contacts technically; in practice migrate around 100 active deals).

## Survey

| Tool | When to use | Skip when |
|---|---|---|
| **Tally** | Free, simple forms. Default for pre-PMF surveys including Sean Ellis | You need advanced logic |
| **Google Forms** | Free, ugly. Acceptable but signals "not serious" | You're asking customers; aesthetics matter |
| **Typeform** | $25–83/mo. Polished, conversational style; higher completion rates | Cost matters more than aesthetics |
| **Userpilot / Intercom** | In-app surveys for active product users | No deployed product yet |

**Recommendation:** Tally for the Sean Ellis survey (see `pmf-scoring.md` in v0.4). Typeform when the survey is going to customers in a sales context.

## Landing page

| Tool | When to use | Skip when |
|---|---|---|
| **Carrd** | One-page Fake Door, ~$19/year. Default for the fastest signup page | You need anything beyond one page |
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
