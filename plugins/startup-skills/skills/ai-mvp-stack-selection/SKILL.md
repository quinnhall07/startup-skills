---
name: ai-mvp-stack-selection
description: |
  Match an MVP to the right AI-build stack (Lovable, Bolt, Cursor + Claude Code, Replit Agent, v0). Enforces the vibe-vs-craft gate — refuses vibe-coding for regulated/payments/auth/PII surfaces. Surfaces the 1000x/10x prototype-vs-production tradeoff explicitly. Token-cost-aware pricing nudges for AI products.

  TRIGGER when: user is starting an MVP and asks about stack; user says "Lovable", "Bolt", "Cursor", "Claude Code", "v0", "Replit Agent", "vibe code", "AI build", "no-code", "build my MVP fast"; technical ability < "can build" AND product is non-trivial; founder is in regulated industry (health/legal/fin) AND mentions any AI build tool.

  SKIP: founder already has a working production MVP (route to `outreach-engine` or `signal-audit`); founder is at idea-validation phase with no committed hypothesis (route to `rapid-experiments` for behavioral test first); founder is asking about model selection (Claude vs. GPT) rather than build stack — out of scope.
---

# AI-MVP Stack Selection

The 2024–2026 AI-MVP stack collapsed timelines from months to days, but production hardening is still 10x slower under vibe-code foundations. This skill picks the right stack for the founder's specific MVP shape AND enforces the vibe-vs-craft gate that prevents shipping LLM-generated auth/payments/PII code into production.

## HARD-GATE

If the MVP touches ANY of: **auth (passwords, tokens, sessions), payments (Stripe, billing), PII (HIPAA, GDPR, financial PII), enterprise SLAs, regulated industry (health, legal, fin)** — vibe-coding is BANNED. Craft-code only (Cursor + Claude Code with review).

Cite the studies if the founder pushes back: **322% more privilege-escalation paths and 153% more design flaws in LLM-generated code** (Stack Overflow, MIT Sloan). Code churn doubles, copy-paste rises 48%, maintenance cost ~4x by year two. The 1000x faster prototype + 10x slower production tradeoff is real.

Founders pay the production-hardening cost regardless. Better to pay it once with a clean foundation than 10x with a vibe-code foundation.

## When to Activate

- Phrases: "what should I build with," "Lovable," "Bolt," "Cursor," "Claude Code," "v0," "Replit Agent," "vibe code," "AI build," "no-code," "build my MVP fast."
- Founder is starting an MVP and asking about the stack.
- Technical ability is below "can build" AND the product is non-trivial.
- Founder is in a regulated industry (health, legal, fin) AND mentions any AI build tool — fires automatically to enforce the hard-gate.

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — vibe-vs-craft, 8 traps.
- `${CLAUDE_PLUGIN_ROOT}/references/mvp-examples.md` — canonical narrow MVPs.
- `${CLAUDE_PLUGIN_ROOT}/references/tool-recommendations.md` — tier 1 stack.
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — especially perfectionism and "fake Steve Jobs."
- `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`

## State Document Protocol

Read `STARTUP-STATE.md`. Pull archetype, hypothesis, technical ability, time horizon, MVP / Experiment Plan, and (new in schema v2) regulated-industry flag. Update MVP / Experiment Plan with chosen stack + vibe-vs-craft decision logged. Session Log: `- [YYYY-MM-DD] ai-mvp-stack-selection — chose <stack>, vibe-vs-craft: <vibe/craft>, regulated: <Y/N>`.

## Process

1. **Read state.** Hypothesis, archetype, technical ability, regulated-industry flag, time horizon.

2. **Verify validation signal exists.** Same gate as `mvp-architect` step 2: if no behavioral signal from `rapid-experiments`, route there first OR log explicit pre-validation risk acknowledgment.

3. **Determine the MVP shape.** Ask the founder which one closest fits:
   - Landing page / Fake Door (testing demand only)
   - Internal-tool prototype (no users yet)
   - Consumer mobile MVP
   - B2B SaaS MVP (auth, payments, PII)
   - Regulated industry MVP
   - AI agent product

4. **Decision matrix (the core artifact):**

   | MVP shape | Recommended stack | Vibe-code OK? | Time to deploy |
   |---|---|---|---|
   | Landing / Fake Door | Carrd, Framer, Lovable | Yes | Hours–days |
   | Internal-tool prototype | Replit Agent, Lovable | Yes | Days |
   | Consumer mobile MVP | Cursor + Expo (production), Lovable for landing | Partial — review every shipped path | 1–3 weeks |
   | B2B SaaS MVP | Cursor + Claude Code, Next.js, Supabase | **NO** | 2–6 weeks |
   | Regulated (health/legal/fin) | Cursor + Claude Code, audit trail mandatory | **NO. Period.** | 4–8 weeks |
   | AI agent product | Cursor + Claude Code; AI infra stack | **NO** | 3–6 weeks |

5. **Pricing predictability nudges:**
   - **Lovable:** $20–50/mo predictable; great for landing/UI; no SQL.
   - **Bolt.new:** $20–100/mo; fastest prompt-to-deploy; degrades sharply past 3–5 components.
   - **Replit Agent:** $25/mo BUT **pricing unpredictable** — founders report burning $600+ in days on top of subscription. Set a hard budget cap.
   - **Cursor:** $20/mo Pro = $20 credit pool, Ultra $200; check `tool-recommendations.md` for current.
   - **Claude Code:** subscription-based, predictable.
   - **v0:** falling behind; not recommended for production work as of late 2025–2026.

6. **Token-cost-economics warning (if AI-product).** If the founder is building an AI-product, surface the COGS math NOW: "Your gross margin per active user is the load-bearing metric. AI products run 30–60% COGS-to-revenue (vs <10% traditional SaaS). Instrument cost-per-request from day 1. See `ai-era-anti-patterns.md` Trap 3."

7. **Vibe-vs-craft gate decision (mandatory, logged).** Based on steps 3–4, surface the decision:
   - **Vibe-code path:** prototype only. NOT for production users. Throwaway after validation.
   - **Craft-code path:** production-ready foundation. Slower start, sustainable.
   - **Hybrid:** vibe-code the UI/landing; craft-code the API/auth/data layer. Most common for consumer products.

   Log the decision in `STARTUP-STATE.md` MVP / Experiment Plan with date + rationale.

8. **Reference Class Forecasting** per `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md`. Whatever stack is chosen, force outside-view timeline. "Your estimate × 3" if uncertain. Founders consistently underestimate Lovable/Bolt timelines because the demo is 1 hour and they assume production is 1 week.

9. **Bias sentinel pass.**
   - **"I'll just use Lovable for everything"** — false economy. Lovable for landing + craft-code for production = correct stack mix.
   - **"Vibe-coding is fine, I'll harden later"** — denial. Studies say production-hardening LLM-generated code is 10x slower than starting fresh.
   - **"Replit Agent is cheaper"** — check pricing unpredictability. The $25/mo headline hides $600 burns.

10. **Update state.** MVP / Experiment Plan: chosen stack, vibe-vs-craft, predicted timeline, budget cap, regulated-industry log entry.

11. **Recommend next.**
    - If craft-code: invoke `mvp-architect` to ruthlessly cut features against the chosen stack's capabilities.
    - If vibe-code: invoke `rapid-experiments` to verify the prototype is testing the right hypothesis BEFORE building.
    - In parallel: `outreach-engine` to recruit hair-on-fire first customers.

## Outputs

- Writes to state: MVP / Experiment Plan (stack, vibe/craft, timeline, budget), Session Log.
- **Artifact on request only:** A Stack Decision Memo (markdown) capturing the choice rationale, budget cap, and vibe/craft commitment — suitable for cofounder/advisor review.

## Anti-Patterns Prevented

- Vibe-coding auth/payments/PII surfaces.
- "Lovable for everything" stack monoculture.
- Replit Agent without a budget cap.
- Skipping token-cost economics for AI-products.
- Pre-validation stack commitment (build the wrong thing twice).

## Recommended Next Skills

Per step 11. `mvp-architect` next for craft-code. `rapid-experiments` for vibe-code validation. `outreach-engine` in parallel.

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Direct on the regulated/PII refusal — cite the studies, don't soften. Use Karpathy's vibe-coding framing as the cultural anchor, but enforce the production boundary.
