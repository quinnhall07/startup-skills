---
name: cofounder-fit
description: |
  Diagnose team gaps against the founder's idea. Applies YC's non-negotiable rules (work 4 weeks first, near-equal equity, vesting). Produces a 4-week trial protocol on request. Refuses pre-PMF sales hires and contractor v1 builds.

  TRIGGER when: founder mentions cofounders, partners, teammates, equity splits, vesting, or solo status; user says "cofounder", "should I do this alone", "find a technical cofounder", "equity split", "vesting", "co-founder matching", "I'm doing this with [name]"; auto-fire when Founder Profile reveals a clear team gap (domain expert + can't build + no technical cofounder; technical builder + no domain knowledge + no domain cofounder).

  SKIP: founder is in active conflict with existing cofounder (route to `cofounder-decision`); founder is asking about hiring an employee, not a cofounder (out of scope); founder is post-PMF asking about VP hires (out of scope for v2).
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

## Red flags

| Founder pattern | Response |
|---|---|
| "I'll just hire a contractor for the v1" | Refuse. Contractor builds v1 you cannot maintain. |
| "Let's hire a salesperson before PMF" | Refuse. Founder does sales pre-PMF. No exceptions. |
| "We're going 90/10 because I had the idea" | Ideas worth ~5%. Refuse the split for two full-time committed people. |
| "We get along great so we'll work well together" | Pleasant ≠ productive under pressure. Demand the 4-week shipping trial. |
| "I met them on LinkedIn last month" | LinkedIn-stranger cofounder. Demand 4-week trial. |
| Considering family-member cofounder | Surface the unfireable risk. |
| Won't sign vesting agreement | Not a real cofounder. State directly. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — rushing decisions, "we get along great," inside view.
- `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md` — YC rules, 4-week trial protocol, patterns to avoid.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — for YC Cofounder Matching pointer, PG essay.
- `${CLAUDE_PLUGIN_ROOT}/references/founder-resilience-protocols.md` — cofounder alignment one-liner.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md` for Founder Profile, idea (if any), and current Team section. Update Team section at completion. Session Log: `- [YYYY-MM-DD] cofounder-fit — diagnosed <gap>, recommended <approach>`.

## Process

1. **Read state.** Founder Profile + idea + existing Team section.

2. **Diagnose team gaps against the idea.** Four lenses:
   - **Domain expertise.** Does anyone on the team know the customer space intimately enough to do customer development without months of embedding?
   - **Technical capacity.** Can the team ship v1 themselves in the time horizon from `STARTUP-STATE.md`?
   - **Sales / distribution.** Who will actually do outreach and close customers? (Almost always must be a founder pre-PMF.)
   - **Design / UX.** For consumer products: is there product-and-design sense on the team?

3. **Approach by gap type.** Use `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md`.
   - **Technical gap + non-technical founder.** Options in order of preference: (a) learn enough to build v1 yourself — YC's "you only need enough to build v1" framing; (b) cofounder via YC Cofounder Matching or warm network, with the 4-week trial protocol applied; (c) explicitly NOT hiring a contractor for the core build — flag as anti-pattern, name it directly.
   - **Domain gap + technical founder.** Customer development can fill this *if* the founder will spend 100+ hours embedded in the domain via interviews. If they won't, recommend a domain cofounder. Stripe-style (technical founders with deep wedge into a specific domain via founder-credibility) is achievable but requires explicit, large commitment to fieldwork.
   - **Sales gap.** **The skill refuses to validate "hire a sales person" for a pre-PMF company.** Founders do early sales themselves. State this directly per `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md`. If the founder is averse to sales, that aversion is itself the diagnostic — surface it.
   - **Design gap, consumer product.** A cofounder with product/design taste is usually load-bearing. For B2B, less so — strong taste can come from a senior PM as employee #1 post-validation.

4. **If the founder is considering a specific person as cofounder**, walk YC's rules from `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md`:
   - **Work together for at least 4 weeks before committing.** Required, no shortcut. "4 weeks" means: both founders complete at least ONE shipped artifact (validation experiment, landing page + outreach batch, 20 customer interviews) AND both attend customer conversations AND both make decisions on the changes. **Coffee chats don't count. Async-only work doesn't count.**
   - **Near-equal equity.** 50/50 (or 51/49 for tiebreaker). Lopsided splits (90/10, 70/30) between two full-time committed people are a tell that someone is not actually a cofounder.
   - **Vesting non-negotiable.** Four years, one-year cliff.
   - **Founder agreement before traction.** Equity, vesting, decision rights, departure terms — in writing.
   - **Patterns to avoid.** LinkedIn strangers with no prior collaboration, family-members who can't be fired, 90/10 splits.

5. **Bias sentinel pass** per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`. Specifically:
   - Rushing into cofounder choice because the founder feels alone and wants a partner. Name it.
   - "We get along great so we'll work well together" — pleasant ≠ productive under pressure.
   - Ignoring financial commitments — what's each person's runway? Can both survive 12 months without salary?

6. **Produce the 4-week trial protocol on request.** Use `${CLAUDE_PLUGIN_ROOT}/references/cofounder-frameworks.md` content verbatim or near-verbatim. Offer it explicitly: "I can write you a 4-Week Cofounder Trial Protocol if you'd like — covers what to ship together each week and what to watch for."

7. **Update state Team section.** Solo/cofounder/team-of-N; specific gaps diagnosed; plan to fill (cofounder search via X, learn-to-build self, hire-after-PMF, etc.). If a trial is starting, log the start date and the 4-week end date.

8. **Recommend next skill.** State explicitly which skill and how to invoke:
   - Returning to mid-flow (most common): "Back to where we were — type `/skill <originating-skill-name>` to continue."
   - If founder is starting a cofounder trial: schedule a 4-week return check-in via Session Log.
   - If founder is in active cofounder conflict with a current partner: route to `cofounder-decision` (NOT this skill).
   - If founder needs FMF help separately: route to `founder-context`.

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

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Founders feel lonely; that's the most common reason they rush this decision. Empathy on the loneliness; rigor on the decision. Refuse politely but firmly when the founder pushes for shortcuts.
