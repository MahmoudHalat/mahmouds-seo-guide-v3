# AEO, GEO & AI Search Optimization Reference

Distilled from 50+ expert transcripts. Numbers cited where available.

---

## 1. How AI Search Works

### Query Fanout Mechanism
- When a user enters a prompt, the AI does NOT answer from a single search. It splits the prompt into 2-5 sub-queries (median), then searches each one independently and stitches results together into a unified answer.
- 66% of fan-out keywords appear only once across repeated runs; less than 1% (0.6%) appear consistently. Individual fan-out terms are unpredictable, but 84% share common URLs in Google results (semantic neighbors).
- Fan-out queries follow predictable patterns: "best X for Y," "X vs Y," "is X worth it," "alternatives to X," "X pricing [year]." Target these patterns rather than chasing specific volatile terms.
- AI assistants that trigger web search (ChatGPT, Perplexity) query Google and/or Bing indexes in real time. They are NOT independent search engines -- they are wrappers around existing indexes with AI logic layered on top.
- Confirmed: ChatGPT uses Google's index. Claude uses Brave Search. Perplexity searches Google and may be building its own index. Ranking in traditional search is a prerequisite for AI visibility.

### RAG Retrieval & Citation Mechanics
- RAG (Retrieval Augmented Generation) is the component that fetches live web data. If the model already knows the answer from training data, it may skip web search entirely.
- ChatGPT web interface triggers web search 100% of the time on tested prompts; the API only triggers it ~77% of the time.
- Scraped ChatGPT responses average 16 sources and 743 words; API responses average 7 sources and 406 words. Brand overlap between API and scraped results is only 24%. Source overlap is only 4%.
- Perplexity API vs. web interface source overlap: just 8%. Track visibility using scraped web-interface data, not API data.
- AI overviews cite an average of 5 sources per query; 90% of the time, 8 or fewer sources are listed.
- Over 45% of citations change when AI overviews refresh. AI overviews refresh on average every 2 days.

### Grounding Queries (Bing Data)
- Bing Webmaster Tools now exposes "AI Performance" data showing grounding queries -- the actual sub-queries LLMs use to validate and cite content.
- Grounding queries often use language humans would not type (e.g., "evaluate," "monitor," "performance"). These represent a new universe of keywords not found in traditional keyword planners.
- A site with only 75 organic clicks in 90 days accumulated 33,000+ AI citations in the same period by ranking for grounding-query language.

---

## 2. Top GEO Ranking Factors (Data-Backed)

1. **Brand associations/dimensions** -- strongest correlation with AI overview visibility, stronger than backlinks, referring domains, or domain rating. The more an AI sees your brand tied to a topic, the more confidently it recommends you.
2. **YouTube mentions** -- strongest correlating factor with AI visibility; YouTube is the most cited domain in AI overviews and AI mode. YouTube mention impressions correlate with AI mentions.
3. **Content freshness** -- AI-cited content is 25.7% fresher than content ranking in regular Google results. ChatGPT and Perplexity list citations newest-to-oldest.
4. **Topical authority** -- sites are 161% more likely to get cited in AI overviews if they also rank for fan-out queries. Build clusters, not isolated pages.
5. **Blog post mentions** -- blogs make up ~29% of cited sources, but mentions in blog posts (own and third-party) have the strongest correlation with how highly AI recommends a brand.
6. **Listicle/comparison presence** -- listicle and comparison content makes up 32%+ of all AI citations. Self-promotional listicles still drive citations; landing pages cited 15.2% of the time, product pages 14%.
7. **Third-party brand mentions** -- off-site mentions on credible sites act as training examples for LLMs. Target high-traffic pages for ChatGPT/Perplexity visibility; target highly-linked pages for AI overview visibility.
8. **Structured content** -- Google AI reads content using a tree-walking algorithm following semantic HTML top-to-bottom. Clear H2/H3 hierarchy, bullet points, tables, and FAQ sections make extraction efficient.
9. **Expert quotes** -- including expert quotes with attribution boosted page visibility by 40% in one 10,000-query analysis. Link to the expert's profile.
10. **Semantic HTML & clean structure** -- tables, lists, and short Q&A blocks are easiest for AI to parse and cite. Start pages with clear definitions and statements of fact.
11. **Diversification** -- 86% of top-cited sources are unique to each AI platform. You must optimize across platforms, not just one.

---

## 3. Google AI Overviews

### How to Get Cited
- AI overviews for commercial queries almost always cite listicles. Get your brand into as many relevant "best X" lists as possible.
- AI overviews appear far more frequently on longer, niche queries than on short head terms.
- Google started linking product names in commercial AI overviews (Nov 2024), creating direct product demand from search.
- Top cited domains in AI overviews: YouTube, Reddit, Quora. Google AI mode also heavily cites Reddit.
- **Updated Mar 2026:** Only **38% of Google AI Overview citations** come from pages that rank in the top 10 for the original query — down from 76% in July 2025 (Ahrefs, https://ahrefs.com/blog/ai-overview-citations-top-10/, n=863K SERPs). The drop reflects Google's increased fan-out subquery reliance, not that organic ranking stopped mattering. For non-Google LLMs (ChatGPT/Gemini/Copilot), ~80% of citations come from pages that don't rank in Google's top 100 for the *original* prompt; Perplexity is the exception (28.6% in top 10) (Ahrefs, https://ahrefs.com/blog/ai-search-overlap/, Aug 2025, n=15K queries). The earlier "70% from top 10" figure is no longer supportable. Ranking still matters — but the bar is fan-out coverage + topical authority, not single-keyword top-10 placement.

### Content Format Requirements
- Use clear semantic HTML: H1 > H2 > H3 hierarchy, bullet lists, tables for comparison data.
- Group related thoughts; keep each section focused on a single takeaway. AI chunks content paragraph-by-paragraph and decides which parts to keep.
- Open with the answer. Do not bury key information deep in the page.
- FAQ schema with clear Q&A pairs is one of the easiest formats for AI to extract and cite.
- Schema markup is NOT parsed by LLMs in its intended structured-data sense. LLMs read schema as plain text. It will not help LLM citations specifically, though it still helps Google search features.

### Click Impact Data
- When an AI overview appears, the #1 organic page loses ~58% of its clicks (up from 35% in earlier studies).
- Search impressions grew ~49% with AI overviews, but click-through rates dropped ~30%.
- Informational queries most affected -- clicks to informational pages dropping 30%+ in some cases.
- Action-oriented queries (calculators, checkers, tools) and transactional queries still drive direct clicks -- no AI overview competes here.

---

## 4. ChatGPT Optimization

### Source Preferences
- ChatGPT prefers publishers and news outlets (Reuters, AP-style sources).
- Reddit is currently the most cited domain in ChatGPT.
- Wikipedia accounts for ~8% of ChatGPT citations (climbed to 14% in some periods).
- ChatGPT cited Reddit in 81% of answers in one 187-query technical study. Cited posts are NOT the most upvoted -- AI prefers definitive, specific answers. Median age of cited Reddit posts is 1.5+ years.

### Money Pages Strategy
- Pre-ChatGPT: 2-3 money pages sufficed. Now: brands performing well have 5-6x as many money pages.
- Build dedicated pages for every feature, every use case, every industry segment, every integration, every comparison.
- ChatGPT triggers brand mentions on mid/bottom-funnel queries, almost never on purely informational queries.
- When someone asks "best X for Y," the follow-up is often "compare these 3." If you lack comparison pages, competitors shape the story.
- Start with bottom-of-funnel content (money pages) FIRST, then expand to top-of-funnel. This is a reversal of the classic SEO snowball method.

### Deal-Breaker Questions
- Can AI fully satisfy the user for this query? If NO, target it with traditional SEO (tools, calculators, transactional pages).
- Does your brand deserve to show up? If your product wouldn't be expected in a recommendation, tactics alone won't sustain visibility.
- Are you refusing to mention competitors? Comparison/listicle content that includes competitors is a requirement for AI brand mentions, not optional.

---

## 5. Perplexity Optimization

### How It Differs
- Perplexity is an answer engine, not a chatbot. Designed for quick fact-finding with heavy source citation. Users expect and want to click through to sources.
- Almost always uses live web search (could not be forced to use training data alone in testing). Far less reliance on static training data than ChatGPT or Claude.
- 780M+ monthly queries (tripled from 230M in mid-2024).
- Perplexity gives significant weight to video content, especially YouTube. Video surfaces prominently in responses, unlike ChatGPT/Claude.
- Perplexity frequently cites Reddit, YouTube, niche forums, industry sites, and even LinkedIn posts.

### Specific Tactics
- Content freshness is critical -- Perplexity pulls the most recent information by default. Refresh important content every 6 months minimum.
- Data-driven, fact-rich content with expert quotes performs best. Expert quotes boosted visibility by 40% in one analysis.
- Comparison-heavy formats perform exceptionally well (32%+ of all AI citations are listicle/comparison content).
- Top-of-funnel content remains relevant on Perplexity because users click through to sources (unlike ChatGPT where top-of-funnel triggers zero brand mentions).
- Check robots.txt to ensure Perplexity's crawler is not blocked.

---

## 6. Multi-Platform Visibility

### Platform Source Preferences
| Platform | Preferred Sources |
|---|---|
| Google AI Overviews | YouTube, Reddit, Quora; listicles; pages ranking in top 10 organic |
| Google AI Mode | YouTube, Reddit; similar to AI overviews |
| ChatGPT | Publishers, news outlets, Reddit, Wikipedia, niche blogs |
| Perplexity | Niche/regional sites, Reddit, YouTube, LinkedIn, forums |
| Claude | Sources from Brave Search index |

- Only 7 of the top 50 most-mentioned domains appeared across all three platforms (Google AIO, ChatGPT, Perplexity). 86% of sources are unique to each.
- Your strategy must be platform-diverse: get listed on YouTube, Reddit, niche publishers, LinkedIn, industry directories, review sites, and your own blog.
- Wikidata entries (lower bar than Wikipedia) help AI systems understand what your brand is even if you don't qualify for a full Wikipedia article.

---

## 7. Content Freshness for AI

- AI-cited content is 25.7% fresher than what ranks in regular Google results.
- ChatGPT and Perplexity tend to order citations newest to oldest.
- One case study: updating a "small business ideas" article triggered 1,100+ new AI mentions within days across AI overviews and ChatGPT.
- Refresh cadence: every 6 months for high-priority pages; no longer than 12 months for any page receiving organic traffic.
- Update facts, add new quotes/stats, remove outdated information, and redate the post when substantive changes are made.
- Fresh guest-post listicles on third-party sites outperform getting added to old listicles -- both in cost efficiency and LLM citation performance.
- Perplexity's real-time search model makes freshness even more important there than on ChatGPT.

---

## 8. Quick Wins Checklist

1. **Unblock AI crawlers** -- check robots.txt for GPTBot, PerplexityBot, ClaudeBot, Bingbot. ~5.9% of sites block GPTBot alone.
2. **Audit your money pages** -- create dedicated pages for every feature, use case, industry, and integration. Aim for 5-6x more money pages than you currently have.
3. **Publish comparison content** -- "your brand vs. competitor" and "best X for Y" listicles are a cheat code for brand mentions. Include competitors honestly.
4. **Add expert quotes** -- include attributed quotes from recognized authorities in your content. Link to their profiles. This boosted visibility by 40% in testing.
5. **Refresh your top pages** -- update stats, add current-year data, redate. One update can trigger 1,000+ new AI citations.
6. **Get on third-party lists** -- identify listicles citing competitors but not you. Reach out to authors for inclusion. Prioritize pages ranking for fan-out query patterns (best, top, vs, review, alternative).
7. **Build content clusters** -- cover your topic from every angle. Sites ranking for fan-out queries are 161% more likely to get cited in AI overviews. Think in semantic clusters, not individual keywords.
8. **Structure for extraction** -- open with the answer, use H2/H3 hierarchy, add tables and FAQ sections. Start pages with clear factual definitions.
9. **Engage on Reddit and YouTube** -- Reddit is the most cited domain in ChatGPT; YouTube is the most cited in AI overviews. Participate genuinely in subreddits; get products reviewed on YouTube.
10. **Diversify across platforms** -- be present on Google Business Profile, LinkedIn, Crunchbase, Wikidata, industry directories. Consistent brand information across 30-40 profiles helps entity validation.
11. **Track with scraped data** -- API-based tracking has only 4% source overlap with what users actually see. Use web-scraped tracking or manual incognito audits.
12. **Target action-oriented queries** -- free tools, calculators, checkers have no AI overview competition and still drive direct clicks. Filter keywords for modifiers like "calculator," "checker," "generator."
13. **Use grounding query language** -- check Bing Webmaster Tools AI Performance for grounding queries. Create H2 sections or new pages targeting the actual language LLMs use in fan-outs (e.g., "evaluate," "monitor," comparison phrases).
14. **Maintain traditional SEO** -- AI visibility is a lens on top of SEO, not a replacement. Google still handles 8.5B searches/day vs. ChatGPT's 2.5B queries. As of Q1 2026, ~38% of AI Overview citations come from the top 10 (Ahrefs Mar 2026) -- down from 76% in mid-2025 -- so traditional SEO is necessary but no longer sufficient.

---

## 9. Machine-Readable Files for AI Agents (v3)

AI agents and LLM-based search are starting to parse structured files at known paths for product info. This is emerging practice (2025-2026) — distinct from classic SEO and distinct from schema markup. Low cost, potential upside; worth publishing.

### `/llms.txt` — root-level product brief

Publish at `https://example.com/llms.txt`. Keep under 10KB. Update whenever positioning changes.

```markdown
# Acme Analytics

One-line: Product analytics for B2B SaaS teams that hate sampling.

## What it does
Acme Analytics ingests product events in real-time and gives PMs, data teams, and support reps a shared view of user behavior. Unlike Mixpanel and Amplitude, we never sample data, even on enterprise volume.

## Who it's for
- B2B SaaS product teams, 10-500 engineers
- Data teams tired of "approximate" answers from sampled analytics
- Support teams that need to replay individual user sessions

## Key pages
- Pricing: https://acme.com/pricing
- Docs: https://acme.com/docs
- API reference: https://acme.com/docs/api
- Changelog: https://acme.com/changelog
- Security / SOC 2: https://acme.com/security
- Customer stories: https://acme.com/customers

## Pricing summary
Free tier up to 10K events/mo. Paid plans from $299/mo (100M events) to custom enterprise. No per-seat charges.

## Contact
- Sales: sales@acme.com
- Support: support@acme.com
- Status page: https://status.acme.com
```

### `/pricing.md` — machine-readable pricing

Publish at `https://example.com/pricing.md`. Mirror the human-facing pricing page.

```markdown
# Acme Analytics — Pricing

## Free
- $0 / month
- Up to 10,000 events/month
- 1 project, 3 team members
- 30 days data retention
- Community support
- Who it's for: side projects, evaluating before upgrading
- Sign up: https://acme.com/signup

## Pro
- $299 / month (annual: $249/mo billed yearly)
- Up to 100 million events/month
- Unlimited projects, unlimited team members
- 12 months data retention
- Email support, 24h SLA
- Who it's for: SaaS companies with 10k+ MAU
- Sign up: https://acme.com/signup?plan=pro

## Enterprise
- Custom pricing, volume discounts
- Unlimited events
- SSO, SOC 2 report, custom data retention
- Dedicated CSM, 4h SLA
- Who it's for: companies with compliance requirements or >500M events/mo
- Contact: https://acme.com/contact-sales
```

### Platform-selection table

| Platform | Favors | Notes |
|---|---|---|
| ChatGPT | Publishers + Reddit + diverse sources | Broad citation spread; ~16 sources/response on web |
| Perplexity | Fresh + niche + YouTube + LinkedIn | Live search default; freshness weighted highest |
| Claude | Brave Search index | Publisher-leaning; structured + E-E-A-T favored |
| Google AI Overviews | Top-10 organic + YouTube + Reddit + Quora | 70% of sources from top-10 organic |
| Gemini | Google ecosystem + YouTube + Knowledge Graph | Favors brands with strong Google entity |

### Citation-boost metrics (Princeton GEO study)

- Adding citations → **+40% AI visibility**
- Adding statistics → **+37% AI visibility**
- Adding direct quotations → **+30% AI visibility**
- Content fresher than 90 days → **25.7% more likely to be cited**

### Implementation checklist

- [ ] Publish `/llms.txt` at root, under 10KB
- [ ] Publish `/pricing.md` at root, mirroring human pricing page
- [ ] Link from HTML head: `<link rel="llms" href="/llms.txt">` and `<link rel="pricing" href="/pricing.md">`
- [ ] Update both whenever product positioning or pricing changes (even small tier changes)
- [ ] Verify with `curl https://yoursite.com/llms.txt` — must serve as plain text/markdown, not HTML
- [ ] Check server logs for AI-agent User-Agents (GPTBot, PerplexityBot, ClaudeBot, Googlebot-Extended, ChatGPT-User, Applebot-Extended) to confirm they're fetching these files
- [ ] Do NOT gate behind auth; do NOT serve different content to AI crawlers than humans (cloaking risk)
