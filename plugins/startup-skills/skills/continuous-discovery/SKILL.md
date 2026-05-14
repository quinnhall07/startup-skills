---
name: continuous-discovery
description: |
  Maintain the customer-discovery cadence after validation. Builds and updates an Opportunity Solution Tree (Torres). Forces weekly customer touchpoints to prevent PMF drift. Routes assumption tests to `rapid-experiments`. Refuses to let the team stop interviewing after launch.

  TRIGGER when: user is post-MVP launch or PMF stage >= early-signal; user asks "what features should I build next", "what should be on the roadmap", "are we still doing customer interviews", "weekly customer cadence"; calendar trigger (>14 days since last logged customer interview); a new feature request arrives that hasn't been independently validated.

  SKIP: user is pre-validation (route to `discovery-coach` PREPARE/DEBRIEF instead); user is at pre-signal stage with <20 ICP conversations (still building the foundation; route to `discovery-coach`); user is in a pivot decision (route to `pivot-decision`).
---

# Continuous Discovery

Discovery is not a one-time validation sprint. After PMF, the cohort changes, expectations rise, competitors ship. Founders who stop interviewing after validation drift out of PMF within 6–18 months — the PMF Treadmill (Reforge/Balfour). This skill enforces Teresa Torres's weekly cadence and maintains the Opportunity Solution Tree as the team's shared map of outcome → opportunity → solution → assumption-test.

## HARD-GATE — do not proceed past this without:

- [ ] User is post-validation (MVP shipped OR PMF stage >= early-signal). If pre-validation, route to `discovery-coach` first.
- [ ] User confirms commitment to weekly cadence (1 interview per week minimum, ongoing).
- [ ] Existing Opportunity Solution Tree in `STARTUP-STATE.md` OR willingness to build one in this session.

If any unchecked: STOP. Either route to the correct skill, or ask the founder to commit to the cadence before continuing. Refuse to do roadmap work without the gate.

## When to Activate

- Phrases: "what features should I build next," "what should be on the roadmap," "are we still doing customer interviews," "weekly customer cadence," "a customer asked for X — should we build it."
- Calendar trigger: >14 days since the last logged customer conversation in `STARTUP-STATE.md`.
- Whenever a new feature request arrives that has not been independently validated by >=20 ICP users.
- Auto-fire from `signal-audit` when retention shows decay and the team has stopped interviewing.

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/continuous-discovery-patterns.md` — Torres OST, story-based interviewing, 5 assumption categories, the Product Trio.
- `${CLAUDE_PLUGIN_ROOT}/references/mom-test-principles.md` — interview hygiene; applies forever, not just pre-validation.
- `${CLAUDE_PLUGIN_ROOT}/references/evidence-weighting-matrix.md` — for classifying new interview data against the existing log.
- `${CLAUDE_PLUGIN_ROOT}/references/jtbd-protocols.md` — Switch interview for post-purchase analysis and churn understanding.
- `${CLAUDE_PLUGIN_ROOT}/references/retention-metrics.md` — to tie discovery findings to retention diagnostics.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — independence-check failure, pedestal bias, recency bias.
- `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`

## State Document Protocol

Read `STARTUP-STATE.md` at activation. This skill maintains TWO sections: the Opportunity Solution Tree (new in schema v2) and the Evidence Log (appends new interviews; append-only). Session Log entry: `- [YYYY-MM-DD] continuous-discovery — interview #N, surfaced <X> opportunities, assumption tests queued: <Y>`.

## Process

1. **Read state.** Pull existing OST (if any), current Sean Ellis score, retention metrics, recent Session Log. Verify the state file has a post-validation marker (MVP shipped or Sean Ellis >= 40%). If not, stop and route to `discovery-coach`.

2. **Cadence check.** Scan the Session Log for the last `discovery-coach` (DEBRIEF) or `continuous-discovery` entry. If >14 days ago, surface directly: "It's been N days since your last logged customer interview. Cadence is the load-bearing discipline of this skill. Schedule one this week before continuing." Do not bypass.

3. **Define / read the outcome.** Single top-of-tree outcome, measurable. Example: "increase D28 retention from 18% to 25%." If no outcome exists in the OST section, force the founder to commit one before proceeding. No outcome = no tree = no skill.

4. **Story-based interviewing prep (PREPARE mode).** Use Torres's question shape: "Tell me about the last time you [behavior]." Scope each question by opportunity. Generate 6–10 questions, NEVER hypothetical, NEVER pitching. Apply the same anti-patterns as `discovery-coach` PREPARE.

5. **Interview debrief (DEBRIEF mode).** Run the evidence-weighting protocol from `discovery-coach` DEBRIEF, AND additionally:
   - Map each surfaced pain/need to an **opportunity** on the OST.
   - Mark whether the opportunity is new (add to tree) or recurring (increment count).
   - Apply the independence check: have >=20 ICP users mentioned this independently, or just this one? One customer's request is a clue, not a mandate.

6. **OST maintenance.** Update the tree:
   - New opportunities: add as children of the outcome (in **customer language**, never solutions).
   - New solutions: add as grandchildren of opportunities. Multiple solutions per opportunity is healthy.
   - New assumption tests: add as leaves under solutions.
   - Surface the highest-priority opportunity to test next (most-cited + tied to outcome).

7. **Assumption mapping.** For the top solution under the top opportunity, run Torres's 5-category check (desirability, viability, feasibility, usability, ethical — per `continuous-discovery-patterns.md`). Identify the riskiest assumption. Route to `rapid-experiments` for the cheapest test (<=1-day experiment). Do not let the team build the solution before testing the assumption.

8. **Retention link.** Pull current retention metrics from `STARTUP-STATE.md`. If retention is decaying or flat-but-low, surface the connection directly: "D28 dropped from 22% to 17%. The opportunities surfacing in your interviews are likely correlated. Prioritize tests against the opportunities most-cited by users who churned." Run a Switch interview per `jtbd-protocols.md` with churned users if none exist in the log.

9. **PMF Treadmill check** (per `retention-metrics.md` and `continuous-discovery-patterns.md`). If any opportunity is "what AI/competitor X already does," surface the treadmill question: "Is your core JTBD now achievable in ChatGPT/Claude in <30 seconds? If yes, your moat is eroding. Discovery should focus on workflow-embedding opportunities, not feature-parity ones." Name the drift before it ossifies.

10. **Bias sentinel pass** per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`. Especially:
    - **Independence-check failure.** Founder treats one customer's feature request as a roadmap mandate. Name it.
    - **Pedestal bias** (Annie Duke). Founder runs interviews but doesn't ship the assumption test. Talking != learning. Pin the next experiment with a date.
    - **Recency bias.** Last week's three interviews should not outweigh the prior 20. Weight by cohort, not by recency.

11. **Update state.** OST section with new nodes. Evidence Log append-only with new interview rows. Session Log with this entry. Never edit prior rows.

12. **Recommend next.**
    - If a clear assumption test is queued: `rapid-experiments`.
    - If retention is decaying and opportunities are workflow-related: `signal-audit` to check PMF drift.
    - If three or more interviews surface the same opportunity not addressable in the current product: `pivot-decision` (consider adjust, not full pivot).
    - Otherwise: schedule next interview, return next week. State the date explicitly.

## Outputs

- Writes to state: Opportunity Solution Tree section, Evidence Log appends, Session Log.
- External resources to surface:
  - Teresa Torres, *Continuous Discovery Habits* — canonical reading for the OST and the weekly cadence.
  - Reforge/Brian Balfour, *Why Product-Market Fit Isn't Enough* — the PMF Treadmill.
  - Bob Moesta, *Demand-Side Sales* — Switch interview technique for churn.
- **Artifact on request only:** Updated OST as a markdown visual (or Mermaid diagram) suitable for sharing with the Product Trio (PM + designer + engineer).

## Anti-Patterns Prevented

- Stopping discovery after launch.
- Treating one customer's request as a roadmap mandate.
- Building features without running the assumption test first.
- Ignoring retention signals when prioritizing opportunities.
- Letting the OST become a wishlist rather than an evidence-grounded tree.
- Allowing the team to delegate interviews ("the PM handles that"). The whole Product Trio attends — that is the point.
- Confusing feature-parity with competitors for opportunity discovery.

## Recommended Next Skills

Per Step 12. `rapid-experiments` for assumption tests; `signal-audit` for retention drift; `pivot-decision` for chronic opportunity gaps. State the next step explicitly: "Type `/skill <name>` to continue."

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md` and `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`. Direct on cadence enforcement. The skill's value IS friction — refuse "we're too busy to interview this week" without naming the cost (PMF Treadmill drift, cohort opacity, roadmap-by-loudest-customer). Empathy on the workload; rigor on the discipline. Cadence is non-negotiable.
