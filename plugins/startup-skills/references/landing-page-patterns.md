# Landing Page Patterns

For Fake Door tests, signup landing pages, and early product landing pages. Tight, single-CTA, behavioral-evidence-capturing. No marketing fluff. Source: synthesis of Stripe early pages, Dropbox MVP, Buffer's two-step landing test, and current direct-response conventions.

## Universal anatomy

```
[Headline]                                     ← 6–10 words, specific value prop
[Subheadline]                                  ← 1 sentence, who it's for + when
[Single visible CTA — button]                  ← "Get Access" / "Reserve Spot" / "Start"
[Optional: 1–3 bullets of how it works]
[Email capture or payment intent]              ← single field
[Optional: signal — N companies, logos, quote]
```

That's the whole page. Mobile-first. Tailwind or equivalent for styling. No carousel, no FAQ above the fold, no testimonial section longer than the offer.

## Headline conventions

- **Specific over clever.** "Schedule patient appointments without insurance pre-auth hell" beats "The future of healthcare scheduling."
- **Direct second-person.** "You hire engineers; we screen them." beats "We are revolutionizing technical hiring."
- **Lead with the customer's pain in their own words** (from `references/research-playbook.md` vocabulary capture). Verbatim language is the difference between a 1% conversion and a 5%.

## Single-CTA discipline

One button. One color. Above the fold. Same text repeated every time it appears. "Get Access" everywhere or "Start Free Trial" everywhere — not a mix.

Multiple CTAs ("learn more" + "sign up" + "request demo") fragment intent and tank conversion. Pick the one the founder actually wants. Send everything to it.

## Behavioral evidence capture

The email field is the minimum. Stronger signal capture:

- **Email + role.** "Email + What's your role?" — adds ICP screening data.
- **Email + use case.** "Email + What would you use this for?" — captures intent in customer language for outreach later.
- **Email + commit-by-date.** "Email + When would you want to try this?" — captures time-urgency signal.
- **Email + small refundable deposit.** "Reserve your spot — $50, refunded if we don't ship by Jan 15." This converts the page from Fake Door to pre-order; weight jumps from 0.4 to 0.8.

Add fields one at a time. Each field costs 10–20% of conversion; budget accordingly.

## Conversion benchmarks (rough)

For a Fake Door page with traffic from a targeted ad or a relevant community post:

- 1% — generic page, weak headline, broad audience.
- 5% — specific headline in customer language, ICP-targeted traffic.
- 10–15% — specific headline + scarcity / time-bound framing + warm traffic.
- 20%+ — usually means the audience is hyper-pre-qualified (e.g., post in a niche subreddit). Be suspicious; the cohort is narrow.

A page converting <1% is either (a) wrong headline or (b) wrong traffic. Diagnose by running the same page against a different traffic source.

## What to never include on a Fake Door / signup page

- Pricing tables for a product that doesn't exist yet.
- Testimonials you don't have.
- A roadmap.
- "Coming soon" without a date.
- Social proof badges from awards lists.
- "Trusted by" logos of companies that aren't actually customers.
- A second CTA that contradicts the first.
- A chat widget. Chat widgets on Fake Door pages catch tire-kickers and waste founder time.

## Tech stack — pick one and move on

- **Carrd.** $19/year. Best for a one-page Fake Door in <2 hours. No code.
- **Framer.** $5–25/month. Best when you want some animation / responsive design polish.
- **Webflow.** $14–39/month. Best when you'll iterate the page a lot.
- **Hand-coded HTML + Tailwind + a static host (Vercel/Cloudflare).** Best when you already know HTML and want full control. Deploy time: hours.
- **Next.js + Vercel.** Overkill for a Fake Door page; appropriate once the page becomes the real product onboarding.

Avoid: WordPress (heavy), Squarespace (rigid), generic page builders that add tracking pixels you don't control.

## Two-step variant — the Buffer pattern

For higher-quality signal: page 1 describes the product and has "Plans and pricing →" as the CTA. Page 2 shows the pricing tiers; each has "Start now →" buttons that capture email + reveal "We're not quite ready yet — leave your email and we'll let you know on launch day." The two-step filters out casual interest and surfaces the cohort that clicked through the pricing — much higher intent than email-on-page-one.

Joel Gascoigne (Buffer) used this exact two-step to validate willingness-to-pay before writing a line of product code. Signal quality: 0.5+ versus 0.4 for one-step.

## Where this is used

`rapid-experiments` recommends specific page patterns to deploy. `artifact-builder` (v0.4) can produce landing pages on request, using these patterns. `outreach-engine` campaigns drive traffic to these pages with measured cohort tagging (UTM params at minimum).
