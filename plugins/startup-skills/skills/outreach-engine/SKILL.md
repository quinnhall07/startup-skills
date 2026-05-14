---
name: outreach-engine
description: |
  Founder-led, do-things-that-don't-scale outreach. Builds prospect lists, drafts YC-style cold email, computes funnel math backwards from goal, runs Continuous Launch. 2026-current on deliverability (post-Feb 2024 rules), LinkedIn algo (comment-first), signal-based outbound. Refuses paid acquisition pre-PMF, sales hires pre-PMF, press-as-acquisition.

  TRIGGER when: user says "first customers", "cold email", "sales", "how do I get people to buy", "getting traction", "launching", "outreach", "do I need a salesperson", "should I run ads"; auto-fire from `mvp-architect` to recruit first customers in parallel with build; PMF stage ≥ early-signal and user asks how to scale acquisition (after `pmf-audit` confirms 40%+).

  SKIP: user has no committed pricing (route to `pricing-model` first); user has no sharp ICP (route to `problem-focus`); user wants to do brand/content marketing (out of scope — this is founder-led customer acquisition only); user is at scaling stage post-PMF wanting paid acquisition strategy (deeper than this skill).
---

# Outreach Engine

Founder-led, do-things-that-don't-scale outreach. Built around Gustav Alstromer's *How to Get Your First Customers*. Refuses paid acquisition pre-PMF. Refuses sales-hire-before-PMF. Refuses press-as-acquisition-channel. Computes the funnel math backwards from goal so the founder sees real outreach volume needed.

## HARD-GATE — refuse if any are missing:

- [ ] `STARTUP-STATE.md` ICP section is sharp (named role + company size + industry + geography). If vague, route to `problem-focus`.
- [ ] `STARTUP-STATE.md` Pricing section has a committed price. If empty, route to `pricing-model`.
- [ ] User is doing founder-led outreach personally (NOT delegating to an SDR).

**Three non-negotiable refusals:**
- **REFUSE paid acquisition pre-PMF.** Cite Gustav Alstromer + Sean Ellis. Burns runway, pollutes signal.
- **REFUSE sales hire pre-PMF.** Founder MUST do early sales. No exceptions.
- **REFUSE press/PR as customer acquisition.** Press = curiosity, not customers. Conversion <1%.

If user pushes back on any of these: state plainly. Do not soften.

## When to Activate

- Phrases: "first customers," "cold email," "sales," "how do I get people to buy," "getting traction," "launching," "marketing," "do I need a salesperson," "how do I do outreach," "should I run ads."
- Auto-fire from `mvp-architect` to recruit first customers in parallel with the build.

## Red flags

| Founder behavior | Response |
|---|---|
| Cold-email blasts from primary domain without SPF/DKIM/DMARC | Refuse. Deliverability is broken. Set up infrastructure first. |
| Pre-PMF paid acquisition | Refuse. Cite Gustav + Ellis. |
| Pre-PMF sales hire | Refuse. Founder does sales. No exceptions. |
| Treats press as customer acquisition | Refuse. <1% conversion. Brand activity, not GTM. |
| Networking-as-procrastination (events, podcasts, threads) | Name it. Selling = asking specific people for money. |
| "Pipeline" of unreplied prospects | Ghosted. Remove from list. Pipeline = `next concrete step on calendar`. |
| Mass-blast LinkedIn DMs | Volume Tax penalty + <1% reply. Comment-first. |
| Cold email open rate "60%" | Apple Mail privacy + Google image pre-fetch inflate. Trust reply rate. |

## Required Reading

- `${CLAUDE_PLUGIN_ROOT}/references/state-document-protocol.md`
- `${CLAUDE_PLUGIN_ROOT}/references/bias-sentinel.md` — launch fallacy, networking-as-procrastination.
- `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md` — YC patterns (warm intro, cold to role, cold to founder).
- `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md` — realistic conversion rates, backwards math.
- `${CLAUDE_PLUGIN_ROOT}/references/tool-recommendations.md` — Apollo, Hunter, HubSpot, Pipedrive, close.com.
- `${CLAUDE_PLUGIN_ROOT}/references/case-studies.md` — Stripe Collison installation, Airbnb manual outreach, DoorDash founder-as-driver.
- `${CLAUDE_PLUGIN_ROOT}/references/external-resources.md` — Gustav, Kat Manalac, PG, Lenny.
- `${CLAUDE_PLUGIN_ROOT}/references/distribution-by-archetype.md` — channel-product fit.
- `${CLAUDE_PLUGIN_ROOT}/references/positioning-frameworks.md` — subject lines flow from positioning.
- `${CLAUDE_PLUGIN_ROOT}/references/ai-era-anti-patterns.md` — Trap 7: cold-email blasting post-Feb 2024.
- `${CLAUDE_PLUGIN_ROOT}/references/aggressive-consultation-archetype.md`

## State Document Protocol

Read `STARTUP-STATE.md`; pull ICP, pricing, MVP/Experiment plan. Update Active Experiments (the outreach batch IS an experiment) and Next Action sections. Session Log: `- [YYYY-MM-DD] outreach-engine — built <N>-prospect list, sent <M> outreaches by date <X>`.

## Process

1. **Read state.** ICP (must be specific — if vague, route to `problem-focus`). Pricing (must be committed — if not, route to `pricing-model`). MVP or experiment plan.

2. **Invoke `market-intel`** to find specific instances of the ICP if not already done. Pull customer vocabulary; you'll reuse it in the outreach.

3. **Prospect list construction.**
   - **For B2B:** build a list of 50–100 named individuals. Use LinkedIn search with the ICP's exact role + company size + tech stack. Tools per `${CLAUDE_PLUGIN_ROOT}/references/tool-recommendations.md`: Apollo.io for list-building, Hunter.io for email finding. Warm network first per Gustav's order of difficulty:
     1. Personal network (current and ex-colleagues, founder friends).
     2. Startups (especially YC alumni if you have access).
     3. Small companies (10–200 employees).
     4. Large companies.
   - **For B2C:** define 3–5 acquisition channels rather than individual prospects. Specific subreddits, Discord servers, Slack communities, Indie Hackers, niche newsletters.

4. **Email infrastructure check (NEW for 2026).** Per `${CLAUDE_PLUGIN_ROOT}/references/tool-recommendations.md` and `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md`:

   - **Sending domains**: Buy 3-10 secondary domains (e.g., `try-acme.com`). NEVER burn primary. Why: post-Feb 2024 Gmail/Yahoo bulk-sender rules + Nov 2025 enforcement.
   - **Mailboxes**: Google Workspace or Microsoft 365. 2-3 per domain. ≤30-50 emails/mailbox/day.
   - **Warmup**: 2-6 weeks via Mailreef/Mailforge/Smartlead built-in.
   - **Authentication**: SPF + DKIM + DMARC mandatory. Start `p=none` → escalate.
   - **Sending tool**: Smartlead (best deliverability) or Instantly (faster setup).
   - **Data**: Apollo (seed list, $49/mo) → Clay (waterfall enrichment + AI personalization, $149+/mo) → NeverBounce (verification).
   - **List-Unsubscribe**: one-click header (RFC 8058) mandatory.
   - **Spam complaint rate**: ≤0.3%.

   If founder has none of this set up, **deliverability is broken before they send the first email**. Spend the 2-6 weeks on infrastructure FIRST, OR use warm intros only.

   Then draft using `${CLAUDE_PLUGIN_ROOT}/references/email-templates.md`. Custom per recipient. Body personalization > first-line personalization. "Timeline hooks" outperform "problem hooks" (10% vs 4.4% reply per modern benchmarks).

5. **Funnel math — backwards from goal**, using updated benchmarks in `${CLAUDE_PLUGIN_ROOT}/references/sales-funnel-math.md`:

   Realistic 2026 founder-led cold outbound:
   - Reply rate: 3-5% (average), 5-10% (good), 10-15% (elite).
   - Reply → scheduled call: 30-50%.
   - Cold → paying customer: **~1% of total sends** (B2B SMB SaaS, typical).

   Example for 10 paying customers in 8 weeks (B2B SaaS):
   - 333 qualified conversations needed (3% close).
   - 6,660 cold outreaches (5% schedule rate).
   - Realistic mix: 4,000 cold + 500 warm intros + LinkedIn inbound-led-outbound.
   - ~580/week of focused work. Full-time founder activity.

   Surface this math explicitly. If math implies infeasible volume: re-price up (fewer customers needed), expand timeline, or narrow ICP further (higher response rate).

6. **Tracking system.** Recommend a spreadsheet (Airtable or Google Sheets) for the first 50–100 prospects. CRM is overkill pre-PMF. Columns: name, role, company, contact info, outreach date, response status, next concrete step, conversation notes. Migrate to HubSpot CRM (free tier) above 100 active prospects.

7. **Qualifying call structure.** Coach the founder on running the call:
   - Open with their problem, not your pitch. (First 5 minutes: ask about their world, their workflow, the trigger event from your hypothesis.)
   - 60% asking about their world, 40% talking about the solution (only after understanding the problem).
   - Identify BANT or MEDDICC signals on the call: budget, authority, need, timeline (BANT); metrics, economic buyer, decision criteria, decision process, identify pain, champion (MEDDICC).
   - End with a specific next step + date. NOT "we'll be in touch." "Tuesday at 2pm, I'll send the pilot proposal."

8. **LinkedIn outbound (2025-2026 algo shift).** LinkedIn moved from Relationship Graph → Interest Graph. Volume-based DM blast is dead.

   **Inbound-Led Outbound framework (current best practice):**
   - Comment meaningfully on 10-20 ICP posts daily (30-80 words each).
   - Algo then surfaces YOUR posts to people whose content you engaged with.
   - DM becomes a follow-up channel, not an open.
   - One case study: replacing 100 cold DMs with 50 thoughtful comments → 300% lift in inbound connection requests from target ICP.

   **Channel hierarchy (current reply rates):**
   - Personalized connection request (with message): 9.36% reply / 29-45% acceptance.
   - Personalized InMail: 18-25% (elite 30-40%).
   - Templated mass DM: <1%.

   **Volume cap**: ~100 connection requests/week hard cap (algo penalty above).

9. **Continuous Launch sequence** per Kat Manalac's *The Best Way to Launch Your Startup* + 2026 reality.

   | Platform | Cadence | Tactic |
   |---|---|---|
   | Launch YC | Once per batch + relaunches at milestones | Driven via YC Launch HN partnership |
   | Hacker News (Show/Launch HN) | Every meaningful release | Post Mon-Tue 8-10am PT; reply every comment in first 2 hours |
   | Product Hunt | Major releases only | 12:01am PT launch; pre-hunt 5-10 supporters; founder replies all day |
   | X / Twitter | Daily-weekly | Video > GIF > image > text; threads with a punchline; 2-min dwell time = 22× algo boost |
   | LinkedIn | 2-3 posts/week | First-person stories + original data; comment-first |
   | Indie Hackers | Milestone-based | "We hit $X MRR" posts with full breakdown |
   | Reddit | Niche subs after 2-3 weeks of authentic participation | Be a real participant first; never lead with promo. **#1 cited domain in ChatGPT/Gemini/Perplexity/Google AI Overviews** as of early 2026 — distribution leverage matters more than ever. |

10. **Signal-based outbound (free + cheap stack).** Per `${CLAUDE_PLUGIN_ROOT}/references/distribution-by-archetype.md`. Pre-PMF, skip enterprise tools ($50k+/yr 6sense). Use:
    - **Free signals**: BuiltWith (tech stack), Crunchbase (funding), LinkedIn job listings (hiring intent), GitHub stars (devtools).
    - **Hiring signal**: Job posts naming a competitor's tool, or for a role your tool replaces → highest intent.
    - **Funding signal**: Series A/B in your ICP segment within 30 days → budget unlocked.
    - **Job change signal**: Champion moves to a new company → reach within 14 days.
    - **Tech-stack signal**: They installed complementary tool / dropped competitor.
    Run weekly trigger query → Clay/Apollo workflow.

11. **Onboarding as sales — Stripe Collison Installation.** White-glove the first 10 customers. Do the setup for them. Sit on a video call as they use it. Manually run the experience. This is the highest-quality customer development you'll do; treat it as research, not as support burden.

12. **Bias sentinel pass.** Especially:
    - **Launch fallacy.** "Once we launch, users will come." Launch generates curiosity, not demand. Demand exists or doesn't before launch.
    - **Networking-as-procrastination.** Founders attend events, podcasts, Twitter threads — anything that feels like "marketing" without actually selling. Selling is the founder asking specific people for money. Anything else is procrastination dressed up.
    - **Sunk cost on prospects.** A prospect who hasn't responded to 4 emails is not "in pipeline" — they ghosted. Remove from list and move on.

13. **Update state.** Active Experiments (the outreach batch with success criterion — "10 paying customers by week 8"). Next Action — Human (specific outreach volume per week). Next Action — Claude (the artifacts to produce on request).

14. **Recommend next.**
    - `discovery-coach` (DEBRIEF) after the first 5 customer conversations — interpret signal before continuing.
    - `signal-audit` after 20+ conversations — full PMF check.
    - `pmf-audit` once product launched and 40+ active users exist.

## Outputs

- Writes to state: Active Experiments (outreach as experiment), Next Action sections.
- External resources to surface:
  - YC video *How to Get Your First Customers* (Gustav).
  - YC video *The Best Way to Launch Your Startup* (Kat Manalac).
  - Paul Graham, *Do Things That Don't Scale*.
  - Lenny Rachitsky's GTM articles.
- **Artifacts on request only:** prospect list (markdown or CSV); batch of 5–10 outreach email drafts customized per recipient; outreach tracking spreadsheet template; qualifying call script (Mom-Test-aligned, post-discovery transition to pitch); Continuous Launch sequencing plan with platform-specific post drafts. Offer each once at the relevant moment.

## Anti-Patterns Prevented

- Cold blasting identical emails.
- "Let's connect" as a CTA.
- Outreach without funnel math.
- "We'll launch and see what happens."
- Paid acquisition before Sean Ellis 40%.
- Sales hire before PMF.
- Press/PR mistaken for distribution.
- "Networking" as a substitute for selling.

## Recommended Next Skills

Per step 14. State explicitly: "Type `/skill <name>` to continue."

## Tone

Per `${CLAUDE_PLUGIN_ROOT}/references/tone-and-stance.md`. Direct on refusals. Use Gustav's framings ("do things that don't scale"). When the founder hedges on the funnel math ("I'll figure that out as I go"), refuse to proceed without it.
