# Research Playbook

This reference is loaded by every skill that runs parallel web research — `market-intel`, `founder-context`, `idea-genesis`, `idea-pressure-test`, and others. It codifies which searches produce signal, which produce noise, and how to extract substance from the results.

## Operating principle

Active research, never passive consultation. When the founder mentions a problem, customer, competitor, or market, the system launches searches *before* responding. The founder receives synthesis grounded in independent evidence — not just more questions about evidence they don't have.

## Search categories and query templates

Use `{placeholder}` substitution. Aim for 5–10 queries per topic, drawn across categories.

1. **Forum pain — what people actually complain about**
   - `site:reddit.com {domain} frustration`
   - `site:reddit.com {domain} "I hate"`
   - `site:reddit.com {domain} "workaround"`
   - `site:news.ycombinator.com {domain} pain`
   Signal: unfiltered language, current workarounds, named tools that fail.

2. **Review complaints — what current tools fail at**
   - `{competitor} G2 reviews bad`
   - `{competitor} Capterra 1 star`
   - `{competitor} alternatives`
   - `{competitor} "switched from"`
   Signal: the gap between what tools promise and what they deliver. Highest-quality source of "what's missing."

3. **Job posting analysis — companies paying to solve the problem**
   - `hiring {role solving the problem} site:linkedin.com`
   - `"job description" {pain word} {industry}`
   - `"we are looking for" {role} {pain word}`
   Signal: budget exists. If companies are hiring full-time staff to handle the problem, the problem is real and funded.

4. **Failed-startup retrospectives — why this doesn't work**
   - `{domain} startup post-mortem`
   - `{domain} startup shutdown`
   - `"we tried" {idea space} "failed"`
   - `site:cbinsights.com {domain}`
   - `site:medium.com "post-mortem" {domain}`
   Signal: the structural reasons others have failed. If you find five post-mortems with the same cause, you've found a tar pit.

5. **Funding activity — where capital sees value**
   - Crunchbase search: `{domain} funding`
   - `{domain} "Series A" OR "Series B" 2024`
   - `{domain} "raised"`
   Signal: market structure and timing. Not validation of any specific idea.

6. **Community language mapping — exact words customers use**
   - Subreddit searches for the domain
   - Discord/Slack community archives
   - Indie Hackers threads
   - LinkedIn group posts
   Signal: vocabulary for outreach, interview scripts, and landing-page copy. Customer language is non-negotiable for cold email response rates.

7. **Adjacent / wedge entry points**
   - Niche subreddits and forums one degree out from the main domain
   - Indie Hackers "I built X to solve Y" threads
   - Reddit `/r/SideProject`, `/r/SaaS`, domain-specific subs
   Signal: where the early-adopter type already congregates. Critical for first-customer acquisition.

## Source trust ladder

- **High signal:** G2/Capterra reviews; Reddit threads with high comment counts; Indie Hackers retrospectives; specific named-founder post-mortems; LinkedIn job descriptions with detailed pain language.
- **Medium signal:** Crunchbase (structured data, but founding-team narratives are PR); HN comment threads on related stories; product community Slacks.
- **Low signal / noise:** Press releases; vendor marketing pages; aggregator listicles ("Top 10 X tools 2024"); TAM estimates from industry reports.
- **Zero weight:** company-authored case studies; awards lists; founder Twitter self-narration.

## WebFetch the 2–3 best pages

After search returns, pick the 2–3 most signal-rich results (high-comment Reddit threads, specific reviews, a substantive post-mortem) and `WebFetch` them. Extract verbatim quotes and exact customer language — not summaries of summaries.

## What this playbook refuses

- **TAM as validation.** Top-down market sizing has zero weight. The system cares about whether 50 specific desperate users exist, not whether the market is theoretically large.
- **"Industry report says X."** Reports are sales documents for the analyst firm. Cite only when the underlying data is named and traceable.
- **Press coverage as demand.** Press generates curiosity, not customers. Distinguish.
