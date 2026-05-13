# Email Templates

Cold and warm outreach patterns for customer discovery and early sales. Source: YC's collected first-customer email corpus (Gustav Alstromer, Lenny Rachitsky's first-customer data set, multiple YC alumni writeups). Templates are starting points — customize the founder credibility line and the specific value-prop sentence for every recipient.

## Universal constraints

- **50–100 words.** Anything longer goes unread.
- **Plain text only.** No HTML, no images, no signature graphics. Plain text deliverability is dramatically better and signals founder-personal, not marketing-blast.
- **One sentence of founder credibility.** Why you specifically. Domain background or prior result.
- **One specific value-prop sentence.** Tied to the recipient's named problem or context. Generic "we help teams scale" is dead-on-arrival.
- **One clear CTA.** Specify a 15–20 minute call. Suggest two concrete times. NOT "let's connect," NOT "let me know when you're free."
- **No marketing language.** Strip every instance of: leverage, transform, accelerate, unleash, supercharge, enable, empower. Use direct verbs (help, do, run, ship).

## Template 1 — Warm intro

Highest response rate; reserve for second-degree network. Always confirm the intro is comfortable first.

```
Subject: Quick intro from <intro person>

Hi <FirstName>,

<Intro person> mentioned you've been dealing with <specific
problem from intro person's context> at <Company>.

I'm building <one-line: what you do> and would love 15 minutes
to learn how you handle <specific aspect of the problem>
today — not to pitch. I previously <one-line founder
credibility>.

Would Tuesday 2pm or Thursday 10am Pacific work for a call?

— <Your name>
```

Why it works: leans on the intro, explicitly says "not to pitch," asks about the customer's world (Mom Test rule 1), specific time anchors.

## Template 2 — Cold to specific role (B2B)

Use after `market-intel` has identified the exact role + the exact pain language. Customize the value-prop sentence to that pain.

```
Subject: <Specific pain phrase> at <Company>?

Hi <FirstName>,

Saw your team is hiring a <role> to handle <pain area> — that
suggests <specific implication, e.g. "you're losing hours each
week to manual reconciliation">.

I'm <one-line founder credibility, e.g. "ex-Stripe payments
infra, now building"> a tool that <specific value prop in
their language>. Would 15 minutes Tuesday 2pm or Thursday 10am
Pacific work to compare notes on how <Company> handles this
today?

Not a pitch — I'm validating whether what we're building lines
up with what teams like yours actually need.

— <Your name>
```

Why it works: the subject is the prospect's own problem named back; the implication shows you researched their job postings or G2 reviews; "not a pitch" disarms; specific times reduce decision friction.

## Template 3 — Cold to founder

Founder-to-founder. Use for early B2B SaaS and devtools where the founder is also the buyer.

```
Subject: <Your company> + <Their company>?

Hi <FirstName>,

Congrats on <recent specific — a launch, a funding round, a
product release>. I'm <one-line founder credibility>.

I'm building <one-line: what you do> for teams like
<Their company>. Two questions I think you could answer in 15
minutes that nobody else can:

1. <specific question about their workflow>
2. <specific question about their tooling decision>

Tuesday 2pm or Thursday 10am Pacific work?

— <Your name>
```

Why it works: opens with a real, recent specific (proves you didn't blast it); offers value (you're not just taking time, you're discussing their decision); the two questions narrow the ask.

## What never to include

- Generic compliments ("love what you're doing"). Reads as bot.
- Marketing-speak ("synergies," "accelerate growth," "leverage AI"). Reads as bot.
- A pitch deck attached or linked. The CTA is the call; the pitch comes later.
- A calendar link instead of specific times. Adds friction; reads as low-investment.
- A signature with title "Co-Founder & CEO." For a 2-person company, this is theater. Just your name.
- A second paragraph explaining your product. Save it for the call. The email's job is to earn the call, not close it.

## Response-rate benchmarks (rough)

- Warm intro: 30–60%.
- Cold to specific role with researched pain: 5–15%.
- Cold to founder with specific recent reference: 5–10%.
- Generic cold to "founder" with vague pitch: <1%. Don't.

If you're below the warm-intro range, the intro person didn't actually endorse you — the email reads like a forwarded sales pitch. If you're below the cold range, the pain language isn't specific enough.

## How `discovery-coach` and `outreach-engine` use this

- `discovery-coach` PREPARE uses Template 1 and 2 for outreach to set up interviews (not sales).
- `outreach-engine` (v0.3) uses Template 2 and 3 for actual sales outreach, with the funnel math from `sales-funnel-math.md` (v0.3) determining batch sizes.
- Every batch is customized per recipient; generic blasts are explicitly refused by both skills.
