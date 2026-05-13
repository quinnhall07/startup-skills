---
name: cofounder-fit
description: Use when the user discusses cofounders, partners, teammates, equity splits, hiring, or solo founder status. Also fires when the founder profile reveals a clear team gap (domain expert without technical ability; technical builder without domain knowledge; either without sales experience). Fires on phrases like "cofounder," "should I do this alone," "find a technical cofounder," "equity split," "vesting," "co-founder matching." Diagnoses team gaps, surfaces YC's rules on cofounder selection (work together first, near-equal equity, vesting non-negotiable), and produces a 4-week cofounder trial protocol. Refuses to validate rushed cofounder choices.
---

# Cofounder Fit

Diagnoses team gaps against the founder's idea, applies YC's non-negotiable rules (work together first, near-equal equity, vesting), and produces a 4-week trial protocol on request. Refuses to validate rushed cofounder choices or "I'll just hire a contractor for the v1."

## When to Activate

- Founder mentions cofounders, partners, teammates, equity splits, vesting, or solo founder status.
- Phrases: "cofounder," "should I do this alone," "find a technical cofounder," "equity split," "vesting," "co-founder matching," "I'm doing this with [name]."
- Auto-fire when the Founder Profile reveals a clear team gap:
  - Domain expert + can't build + no technical cofounder.
  - Technical builder + no domain knowledge + no domain cofounder.
  - Either + no sales background + considering pre-PMF sales hire.

## Required Reading

- `references/state-document-protocol.md`
- `references/bias-sentinel.md` — rushing decisions, "we get along great," inside view.
- `references/cofounder-frameworks.md` — YC rules, 4-week trial protocol, patterns to avoid.
- `references/external-resources.md` — for YC Cofounder Matching pointer, PG essay.

## State Document Protocol

Read `STARTUP-STATE.md` for Founder Profile, idea (if any), and current Team section. Update Team section at completion. Session Log: `- [YYYY-MM-DD] cofounder-fit — diagnosed <gap>, recommended <approach>`.

## Process

1. **Read state.** Founder Profile + idea + existing Team section.

2. **Diagnose team gaps against the idea.** Four lenses:
   - **Domain expertise.** Does anyone on the team know the customer space intimately enough to do customer development without months of embedding?
   - **Technical capacity.** Can the team ship v1 themselves in the time horizon from `STARTUP-STATE.md`?
   - **Sales / distribution.** Who will actually do outreach and close customers? (Almost always must be a founder pre-PMF.)
   - **Design / UX.** For consumer products: is there product-and-design sense on the team?

3. **Approach by gap type.** Use `references/cofounder-frameworks.md`.
   - **Technical gap + non-technical founder.** Options in order of preference: (a) learn enough to build v1 yourself — YC's "you only need enough to build v1" framing; (b) cofounder via YC Cofounder Matching or warm network, with the 4-week trial protocol below; (c) explicitly NOT hiring a contractor for the core build — flag as anti-pattern, name it directly.
   - **Domain gap + technical founder.** Customer development can fill this *if* the founder will spend 100+ hours embedded in the domain via interviews. If they won't, recommend a domain cofounder. Stripe-style (technical founders with deep wedge into a specific domain via founder-credibility) is achievable but requires explicit, large commitment to fieldwork.
   - **Sales gap.** **The skill refuses to validate "hire a sales person" for a pre-PMF company.** Founders do early sales themselves. State this directly per `references/cofounder-frameworks.md`. If the founder is averse to sales, that aversion is itself the diagnostic — surface it.
   - **Design gap, consumer product.** A cofounder with product/design taste is usually load-bearing. For B2B, less so — strong taste can come from a senior PM as employee #1 post-validation.

4. **If the founder is considering a specific person as cofounder**, walk YC's rules from `references/cofounder-frameworks.md`:
   - **Work together for at least 4 weeks before committing.** Required, no shortcut. Coffee chats don't count.
   - **Near-equal equity.** 50/50 (or 51/49 for tiebreaker). Lopsided splits between two full-time committed people are a tell that someone is not actually a cofounder.
   - **Vesting non-negotiable.** Four years, one-year cliff.
   - **Founder agreement before traction.** Equity, vesting, decision rights, departure terms — in writing.
   - **Patterns to avoid.** LinkedIn strangers with no prior collaboration, family-members who can't be fired, 90/10 splits.

5. **Bias sentinel pass** per `references/bias-sentinel.md`. Specifically:
   - Rushing into cofounder choice because the founder feels alone and wants a partner. Name it.
   - "We get along great so we'll work well together" — pleasant ≠ productive under pressure.
   - Ignoring financial commitments — what's each person's runway? Can both survive 12 months without salary?

6. **Produce the 4-week trial protocol on request.** Use `references/cofounder-frameworks.md` content verbatim or near-verbatim. Offer it explicitly: "I can write you a 4-Week Cofounder Trial Protocol if you'd like — covers what to ship together each week and what to watch for."

7. **Update state Team section.** Solo/cofounder/team-of-N; specific gaps diagnosed; plan to fill (cofounder search via X, learn-to-build self, hire-after-PMF, etc.). If a trial is starting, log the start date and the 4-week end date.

8. **Recommend next skill.** Cofounder-fit is usually invoked mid-flow from another phase — recommend back to wherever the founder was when this came up. If the founder is paused on the cofounder question entirely (waiting on a search), explicitly say so and tell them the next skill resumes when they have an answer.

## Outputs

- Writes to state: Team section.
- External resources to surface when relevant:
  - YC Cofounder Matching (startupschool.org/cofounder-matching) when recommending a search.
  - PG *How to Pick a Cofounder* when discussing personal qualities.
  - YC video *How to Apply and Succeed at Y Combinator* — team composition section.
- **Artifact on request only:** A 4-Week Cofounder Trial Protocol markdown doc. Offer once.

## Anti-Patterns Prevented

- Validating "I'll just hire a contractor for the v1."
- Validating "let's hire a salesperson before PMF."
- Letting a founder commit to a cofounder after one good conversation.
- 90/10 splits between two full-time people.
- Equity decisions before vesting is on the table.
- Skipping the financial-commitment conversation.

## Recommended Next Skills

Return to the calling phase: usually `idea-pressure-test`, `idea-genesis`, or whichever skill the founder was in. State explicitly: "Back to where we were — type `/skill <name>` to continue."

## Tone

Per `references/tone-and-stance.md`. Founders feel lonely; that's the most common reason they rush this decision. Empathy on the loneliness; rigor on the decision. Refuse politely but firmly when the founder pushes for shortcuts.
