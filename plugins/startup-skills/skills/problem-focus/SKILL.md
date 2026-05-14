---
name: problem-focus
description: |
  Drill recursively until the ICP is specific, locatable, and testable. Turns "companies need better X" into "the head of sustainability at Series B-C tech startups needs to report Scope 1-3 to their board, currently builds it manually in Excel." Refuses to proceed if the ICP can't be found online in concentrated form.

  TRIGGER when: after `idea-pressure-test` recommends pursuing the idea; user describes problem abstractly ("companies need better X", "people struggle with Y", "the problem is..."); user says "who is this for", "define my ICP", "narrow down my customer"; Current Hypothesis in `STARTUP-STATE.md` is vague OR ICP fields are empty.

  SKIP: idea is still vague / not pressure-tested (route to `idea-genesis` or `idea-pressure-test` first); founder already has a sharp ICP and is ready to interview (route to `discovery-coach` PREPARE); founder is post-PMF refining HXC (route to `pmf-audit`).
---

# Problem Focus

The hardest skill to do well. Drills "companies want to reduce carbon emissions" down to "the head of sustainability at Series B-C tech startups needs to report Scope 1-3 emissions to their board, currently builds it manually in Excel." Refuses to proceed if the ICP can't be located in the wild — if the ICP doesn't exist online in concentrated form, the founder can't reach them.

## When to Activate

- After `idea-pressure-test` recommends pursuing the idea.
- When the user describes a problem at an abstract level: "companies need better X," "people struggle with Y," "the problem is…", "who is this for," "define my ICP," "narrow down my customer."
- Whenever the Current Hypothesis in `STARTUP-STATE.md` is vague or the ICP fields are empty.

## Red flags

| Founder claim | Response |
|---|---|
| "Small businesses" as the ICP | 30M companies in US. Not narrow. Reject; re-narrow. |
| "Everyone has this problem" | False consensus. Drill back to step 2. |
| Anchoring on 2-3 interview responses | Small sample fallacy. Below 20 ICP-targeted is not data. |
| Defines ICP without buyer-vs-user distinction (B2B) | Force the split. Many B2B failures are buyer/user mismatches. |
| Can't name 5 specific people who fit the ICP | The ICP doesn't exist concretely. Drill further or change. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — false consensus, narrow-well failure, small sample fallacy.
- `${CLAUDE_PLUGIN_ROOT}/references/research-playbook.md` — for the ICP-validation searches.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — for narrow-start anchors (Stripe→YC startups, Facebook→Harvard, Airbnb→conferences).
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — for Mom Test, Jared Friedman video, Steve Blank.
- `${CLAUDE_PLUGIN_ROOT}/references/jtbd-protocols.md` — Switch interview prep (if post-purchase analysis).
- `${CLAUDE_PLUGIN_ROOT}/references/continuous-discovery-patterns.md` — story-based interview shape.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md`; pull idea and any prior ICP attempts. Update Current Hypothesis, Target Customer, and What We Know vs What We've Assumed sections at completion. Session Log: `- [YYYY-MM-DD] problem-focus — sharpened hypothesis to <ICP>, riskiest assumption: <X>`.

## Process

1. **Read state.** Note the level of vagueness in the existing hypothesis. If sharp already, skip to riskiest-assumption identification.

2. **Recursive specificity — drill one question at a time.** Wait for each answer before the next.
   - **Who specifically?** Job title, company size, industry, geography. "Companies" is not an answer. "Heads of sustainability at Series B-C tech startups in the US/EU" is.
     - **Bad**: "Small businesses." / "Developers." / "Managers."
     - **Good**: "Operations leads at 100-2000-person tech companies doing supply-chain work, US/EU, $2M+ annual tool spend." / "Data engineers building ETL pipelines for non-technical stakeholders, at 500-5000-person companies, fintech/biotech." / "Dental practice owners, 1-5 offices, US, 50-200 patient visits/week."
   - **In what situation exactly?** What trigger, what time of week/month/quarter, what task. "When they need to report" is not an answer. "When their board meeting agenda lands at week 11 of each quarter and they have 5 business days to prepare emissions data" is.
   - **Doing what?** What action, with what tools. "Tracking emissions" is not an answer. "Pulling utility bills from 4 office leases, normalizing Scope 1-2 data, manually estimating Scope 3 from procurement records in Excel" is.
   - **What does it cost them today?** Time (hours per week), money (consultants, software, headcount), errors, missed opportunities, escalations.
   - **What do they do right now to solve this?** Current workaround = real demand signal. If they're not doing anything, the pain isn't acute enough yet.

3. **Map the current workflow in detail.** Who does what, with what tools, how often, at what cost. Draw it as a numbered list or a small diagram in markdown. This is the most valuable thing the founder owns at this stage.

4. **Distinguish buyer from user (B2B only).** Many B2B failures are buyer/user mismatches. Identify: who *uses* the tool daily? Who *pays* for it? Who *evaluates* it for purchase? Often three different people. Capture each.

5. **Invoke `market-intel`** to validate that the customer type exists in concentrated form online. **Concentration thresholds (one or more must hold):**
   - ≥500 clear matches on LinkedIn for the exact role + company-size combo.
   - ≥100 active members in subreddits, Slack/Discord communities, or industry forums discussing the problem.
   - ≥50 named participants in a niche community (Indie Hackers thread, Pavilion/RevGenius/MicroConf-style).

   **If none of these hold, REFUSE to proceed.** State directly: "I can't find your ICP at scale on the public web. Either the ICP doesn't exist in the numbers you claim, or they're a profile that doesn't congregate online — which means your distribution will be brutally hard. We need to narrow further (good) or change the ICP (also good)."

6. **Extract customer language from `market-intel`.** Pull 5–10 *exact words* the ICP uses for the problem and the workaround. These become non-negotiable for the interview script (`discovery-coach`) and outreach copy (`outreach-engine`).

7. **Formulate the hypothesis** in the standard Lean Startup format:

   > "We believe [specific customer type] experiences [specific problem] when [specific situation] and will [specific behavior change: pay / switch / use weekly] because [specific insight about why now]."

   Each bracketed field must be filled with concrete content from steps 2–4. Generic placeholders fail.

8. **Identify the single riskiest assumption.** What one thing would have to be true for this to work? Common shapes: "they'll pay for it" / "they can find us" / "we can deliver it for less than they pay" / "the trigger event happens often enough" / "the buyer ≠ the user, and the buyer cares enough to fund this."

   Also identify the second and third most-risky to avoid anchoring on one. If the founder pushes back, that's data — note it.

9. **Pre-commit success and kill criteria.** The founder must specify, in advance, what evidence would convince them to continue ("5+ paying pilot customers in 8 weeks") and what would make them stop ("zero paid commitments by week 4 from 30 ICP-targeted conversations"). No moving goalposts. Per the falsification pre-commitment override in `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`.

10. **Bias sentinel pass.** Especially:
    - **False consensus:** "everyone has this problem" — drill back to step 2.
    - **Narrow-well failure:** if the ICP is "small businesses" (30M companies in the US), that's not narrow — it's the opposite. Reject and re-narrow.
    - **Small sample fallacy:** if the founder is anchoring on 2–3 interview responses to define the ICP, name it.

11. **Surface PG's narrow-well metaphor.** A small number of people who desperately need this beats a large number who are mildly interested. Facebook started at Harvard. Stripe started at YC startups. Airbnb started at design conferences. Narrow is correct — anchors from `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md`.

12. **Update state.** Current Hypothesis (filled with the new formulation). Target Customer (all fields). What We Know vs Assumed (each fact, with source). Pre-committed success and kill criteria.

13. **Recommend next skill.**
    - Default: `discovery-coach` (PREPARE mode) for 5+ targeted interviews against the riskiest assumption.
    - If founder wants behavioral evidence before more conversations: `rapid-experiments` to design a Fake Door or Concierge MVP.

## Outputs

- Writes to state: Current Hypothesis, Target Customer (all fields including buyer/user split), What We Know vs Assumed, kill/success criteria.
- External resources to surface:
  - Rob Fitzpatrick, *The Mom Test* (problem definition section).
  - YC video *How to Talk to User* (Jared Friedman).
  - PG, *How to Get Startup Ideas* (the well metaphor).
  - Steve Blank, *Four Steps to the Epiphany* (Customer Discovery).
- **Artifact on request only:** Hypothesis & ICP one-pager (markdown). Offer once.

## Anti-Patterns Prevented

- "Companies" / "people" / "users" as ICP.
- "Small businesses" as a narrow ICP (it isn't).
- Skipping the buyer-vs-user check in B2B.
- Formulating the hypothesis with placeholders still in it.
- Setting success criteria after seeing the data ("HARKing").
- Validating an ICP that doesn't exist in concentrated form on the public web.

## Recommended Next Skills

`discovery-coach` (PREPARE) is the default. `rapid-experiments` if the founder prefers behavioral testing first.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Drill until specific. Refuse to accept vague answers as final. When the ICP can't be found online, name the implication directly — distribution is the problem, not the product.
