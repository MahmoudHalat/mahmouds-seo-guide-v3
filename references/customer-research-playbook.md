# Customer Research Playbook

Load when: "customer research", "ICP research", "analyze transcripts", "voice of customer", "VOC", "JTBD", "jobs to be done", "what do customers say", "talk to customers", "support ticket analysis", "persona building", "messaging input needed".

Most SEO briefs and marketing copy fail because the writer guessed the audience's language. This file is the systematic replacement for guessing. Two modes, one extraction framework, confidence tags, synthesis to messaging input.

---

## 1. Two Research Modes

| Mode | What | When | Effort |
|------|------|------|--------|
| **Mode 1 — Analyze Existing Assets** | Interview transcripts, support tickets, sales calls, reviews, survey responses, Intercom/Zendesk logs, NPS comments, cancellation reasons | Any time the business has customers. Always start here. | Low — data already exists |
| **Mode 2 — Digital Watering Hole** | Reddit, G2, App Store reviews, HN threads, LinkedIn posts, Indie Hackers, niche forums, Discord logs | No customers yet, new segment, new geo, or to validate Mode 1 findings | Medium — search + scrape + read |

**Rule**: if Mode 1 data exists, use it first. It is denser, more honest, and already bought (or churned from) you. Mode 2 is for breadth and validation — never skip it, never lead with it.

---

## 2. Extraction Framework — 6 Dimensions

Extract these from every source. Always capture the verbatim quote in addition to the tag.

| Dimension | What to extract | Why it matters |
|-----------|-----------------|----------------|
| **JTBD** | Functional ("get X done"), Emotional ("feel Y"), Social ("be seen as Z") | Headline + hero copy |
| **Pains** | Problem + severity (Critical / High / Medium / Low) | Pain-agitate-solve; objection handling |
| **Triggers** | The event/moment that prompted the search for a solution | Ad copy, intro hooks, intent keywords |
| **Desired Outcomes** | What success looks like *to them* (not you) | Feature benefits, social proof framing |
| **Language** | Verbatim phrases, analogies, slang, curse words | Title tags, H1s, meta descriptions — the gold |
| **Alternatives** | Current tool, workaround, spreadsheet, competitor, "doing nothing" | Comparison pages, differentiation angles |

**Severity labels for Pains**:
- **Critical** = they would pay today to solve it; losing money/sleep/customers over it
- **High** = actively searching, comparing solutions
- **Medium** = aware of pain, not yet shopping
- **Low** = nice-to-have, "would be cool if"

---

## 3. Source Guide by ICP Type

| ICP | Primary Sources | Secondary | Notes |
|-----|-----------------|-----------|-------|
| **B2B SaaS** | G2 reviews (pros/cons), Reddit (r/SaaS, niche subs), HN comments on competitor launches, Capterra | LinkedIn posts + comments, Twitter replies | G2 "what do you dislike" is the richest pain mine |
| **SMB / Solopreneur** | Reddit (r/smallbusiness, r/Entrepreneur), Indie Hackers, G2 SMB tier | Facebook groups, niche Discord | IH is honest — founders post raw struggles |
| **DevOps / Technical** | r/devops, r/sysadmin, r/kubernetes, HN, Stack Overflow, GitHub issues on competitor repos | Changelog comments, Discord channels | Search GH issues labeled `feature-request` on competitors |
| **B2C** | App Store + Play Store reviews (1-3 star especially), hobby subreddits, TikTok comments, Amazon Q&A | YouTube comments on review videos | 1-star = Critical pains; 3-star = High pains |
| **Enterprise** | Gartner Peer Insights, G2 Enterprise tier, TrustRadius, Forrester Wave, LinkedIn thought-leader comment threads | Industry subreddits, RFP templates on SlideShare | Enterprise buyers rarely post on Reddit — LinkedIn threads are their watering hole |
| **E-commerce / DTC** | Amazon reviews (verified-purchase filter), Trustpilot, Reddit hobby subs, niche Facebook groups | TikTok comments on haul/review videos | Sort Amazon by "most critical" for pains |

### Concrete search queries

```
site:reddit.com "{product category}" "wish it could" OR "biggest problem" OR "hate that"
site:reddit.com "{competitor}" "switched from" OR "alternative to"
site:g2.com "{competitor}" "dislike"
site:news.ycombinator.com "{product category}" "why is" OR "anyone else"
"{competitor}" "cancel" OR "refund" site:trustpilot.com
site:github.com "{competitor}" "feature request" OR "would be nice"
```

---

## 4. Confidence Labeling

Tag every finding with a confidence level. Never ship findings without one.

| Label | Bar | Example |
|-------|-----|---------|
| **High** | 5+ independent sources in similar words, across ≥2 source types | "Users call onboarding 'confusing'" — 7 G2 reviews + 3 Reddit threads |
| **Medium** | 2-4 sources, OR 1 strong source (transcript) + logical inference | "Users pick us over X for API quality" — 3 sales calls mention it |
| **Low** | 1 anecdote, 1 review, or pure assumption | "Might be a billing issue" — 1 support ticket |

**Only High-confidence findings belong on the homepage.** Medium goes in blog / category pages. Low stays in the research doc as hypothesis to validate.

---

## 5. Synthesis Steps

After extraction, always run this pipeline:

1. **Cluster by theme** — group raw quotes into buckets (onboarding, pricing, integrations, reliability, support). 5-10 clusters max per source set.
2. **Frequency score** — count mentions per cluster. Rank. The top 3 clusters are messaging priorities.
3. **Segment by profile** — re-slice clusters by persona (role, company size, use case). Same pain reads differently for solo dev vs enterprise architect.
4. **Extract money quotes** — pull 2-3 verbatim quotes per cluster. These go into copy and H2s. Do not paraphrase.
5. **Flag contradictions** — different personas want opposite things (more features vs simpler UI). These signal positioning choices, not bugs in the data.
6. **Convert to messaging input** — each top cluster becomes:
   - One JTBD statement
   - One pain + trigger pair
   - One desired outcome
   - One money quote
   - One alternative being displaced

---

## 6. Output Template

Format findings like this — readable by a writer, editor, or future-you:

```markdown
## Finding: Onboarding Friction
- Confidence: HIGH (7 G2 reviews, 3 Reddit threads, 2 support tickets)
- Persona: First-time admin, company size 10-50
- JTBD (functional): "Get my team invited and using the tool by end of week"
- JTBD (emotional): "Not feel stupid asking basic questions"
- Pain: Setup requires connecting 4 tools before any value — Severity: High
- Trigger: Manager mandates rollout with a deadline
- Desired outcome: "Working demo to show my boss by Friday"
- Language (verbatim):
  - "took me 3 hours just to get past the connection step"
  - "why do I need to set up SSO before I can even see the dashboard"
  - "the tutorial assumes I already know what a workspace is"
- Alternatives: Notion (docs), Airtable (tracking), spreadsheet
- Messaging implication: Lead with time-to-first-value (<10 min). Show the dashboard in the hero, not the setup flow.
```

One block per cluster. Stack them into a single research doc. That doc is the brief for every page, ad, email, and post downstream.

---

## 7. Quick Gotchas

- **Survey bias**: self-reported importance inflates. Weight behavior (tickets, cancellations, feature usage) over survey data.
- **Recency bias**: sort sources by date; a 2022 review of a 2024 product is noise.
- **Vocal minority**: 1-star reviews skew extreme. Cross-check against 3-star reviews (nuanced) and 5-star reviews with a "but..." (honest).
- **Competitor contamination**: when mining G2 for competitor X, you find what X's users dislike — not necessarily what your users want. Useful, but label it.
- **Sales-call bias**: reps hear objections from losses more than wins. Balance with customer-success calls for renewal/expansion language.
- **Translation loss**: never paraphrase verbatim language into marketing-speak. "Saves time" kills; "I got my Saturdays back" sells.
