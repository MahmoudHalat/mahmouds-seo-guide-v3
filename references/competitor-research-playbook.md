# Competitor Research Playbook

Load when: "competitor research", "competitor profile", "profile this competitor", "competitive intelligence", "analyze competitor", "who are my competitors", "competitor dossier", "research competitors", "battle card", "competitor teardown", "comp analysis".

Systematic methodology for turning a list of competitor URLs into structured, reusable profile documents. Three phases: surface scrape, SEO/traffic data, review sentiment. Persist raw data so you can re-distill with new lenses later without re-scraping.

---

## 1. Phase 1 — Surface Scrape

Tool: Firecrawl, WebFetch, or ScrapingBee. Pull full-page markdown for these pages minimum:

| Page | Extract |
|------|---------|
| **Homepage** | Headline, subhead, hero CTA copy, value prop, social proof logos, first 3 sections |
| **Pricing** | Tier names, prices, billing cadence, feature gates per tier, free tier existence, annual discount %, custom/enterprise tier presence |
| **Features / Product** | Feature categories, named capabilities, integration list, feature-tier mapping |
| **About** | Founding year, founders/team size, funding raised, investors, HQ location, mission/story |
| **Customers / Case studies** | Named customers, logos, industries, company sizes, quoted results |
| **Blog** | Posting cadence (posts/month), top 3 content categories, author bylines, last-updated date of homepage |
| **Docs / Help center** | Size of docs (rough page count), presence of API docs, community forum, changelog URL |
| **Integrations page** | Count + named categories (CRM, analytics, comms, etc.) |

**Output of Phase 1**: one raw markdown file per page type, stored under `competitor-profiles/raw/{slug}/{YYYY-MM-DD}/scrapes/`.

---

## 2. Phase 2 — SEO & Traffic Data

Tools: DataForSEO, Ahrefs, SEMrush, SimilarWeb, SpyFu, BuiltWith.

| Signal | Query | Why |
|--------|-------|-----|
| Domain rating / authority | Ahrefs DR, Moz DA | Baseline competitive difficulty |
| Referring domains | Ahrefs → Top referring domains | Where to source backlinks yourself |
| Top organic pages | Ahrefs → Top pages by traffic | Which pages earn most of their rankings |
| Top keywords | Ahrefs → Top keywords, filter ≥KD 0, ≥10 vol | Their intent/commercial keyword base |
| Traffic estimate | SimilarWeb / Ahrefs traffic est. | Scale context |
| Paid keywords | SpyFu / Ahrefs paid | What they'll buy clicks for — strong commercial-intent signal |
| Ad creative history | SpyFu / Meta Ad Library / Google Ads Transparency Center | Value props they test |
| Tech stack | BuiltWith / Wappalyzer | CMS, analytics, CRM, ad platforms — signals sophistication and budget |
| Historical pricing | Wayback Machine on /pricing | Price bumps reveal confidence; discount spam reveals desperation |

**Output of Phase 2**: JSON/CSV dumps under `competitor-profiles/raw/{slug}/{YYYY-MM-DD}/seo/`.

---

## 3. Phase 3 — Review & Sentiment Scrape

Sources: G2, Capterra, TrustRadius, Trustpilot, Reddit, App Store / Play Store, Gartner Peer Insights.

For each review site, extract:

- **Overall rating** + review count
- **Top 3 praise themes** — with 3-5 verbatim quotes per theme
- **Top 3 complaint themes** — with 3-5 verbatim quotes per theme
- **Alternatives mentioned** — what users say they switched from or are considering switching to
- **Common use-cases** — what jobs are users hiring this for
- **Deal-breakers** — what caused 1-star reviews specifically

**Reddit extraction**:
```
site:reddit.com "{competitor}" ("alternative" OR "switched" OR "worth it")
site:reddit.com "{competitor}" "vs"
```
Pull threads with >10 comments. Save the top 5 comments (not the post).

**Output of Phase 3**: raw exports under `competitor-profiles/raw/{slug}/{YYYY-MM-DD}/reviews/`.

---

## 4. Data Persistence Structure

```
competitor-profiles/
  raw/{slug}/{YYYY-MM-DD}/
    scrapes/        # Firecrawl markdown — homepage.md, pricing.md, features.md, etc.
    seo/            # DataForSEO/Ahrefs JSON dumps
    reviews/        # G2/Capterra/Trustpilot/Reddit extracts
  profiles/{slug}.md   # the distilled profile document
```

**Why raw storage matters**: you will re-distill with new lenses (e.g., "how do they handle enterprise pricing", "what's their SOC 2 posture", "are they building AI features") without re-running scrapes. Raw data is cheap to keep and expensive to reacquire.

**Timestamp dir names**: always date-prefixed. A profile from 6 months ago is stale; you want to see the delta over time.

---

## 5. Profile Output Template

Format `profiles/{slug}.md` like this — one profile per competitor, re-generatable from the raw:

```markdown
# {Competitor Name} — Competitive Profile
*Last updated: YYYY-MM-DD*

## Snapshot
- Category: {positioning / shelf}
- Founded: {year}, {location}
- Funding: {stage, total raised, lead investor}
- Est. traffic: {monthly organic visits}
- Domain rating: {DR}
- Review rating: {G2 avg, N reviews}

## Positioning
- Headline: "{exact homepage H1}"
- Value prop in their words: "{hero subhead}"
- Target ICP: {inferred from copy + customer logos}
- Category framing: {where they place themselves}

## Pricing
- Tiers: {list with $/mo and key gates}
- Free tier: Yes/No ({if yes, limits})
- Annual discount: {%}
- Enterprise: {contact sales / published}
- Price history: {significant changes from Wayback}

## Feature Parity Matrix
| Capability | They have | We have | Gap/Advantage |
| ... | ✓/✗/Partial | ✓/✗/Partial | Who wins |

## Customer Themes (from reviews)
### What they love
- Theme 1: "verbatim quote" (×N mentions)
- ...
### What they hate
- Theme 1: "verbatim quote" (×N mentions)
- ...
### Why they switched to/from
- {alternative} → {competitor}: "quote"
- {competitor} → {alternative}: "quote"

## SEO Posture
- Top 5 pages by traffic: {url — est. visits/mo}
- Top 5 keywords by value: {keyword — KD — est. traffic}
- Content cadence: {posts/mo}
- Notable backlink sources: {3-5 high-authority referrers}

## Content Strategy
- Top categories: {3-5 themes}
- Format mix: {% listicles / guides / comparison / tools}
- Unique angles: {what they do that others don't}

## Ad Posture
- Active channels: {Google, Meta, LinkedIn, etc.}
- Top ad creative themes: {hooks they repeat}
- Estimated monthly spend: {SpyFu est.}

## Gaps / Weaknesses
- {specific complaint clusters you could exploit in positioning}

## Opportunity Signals
- {keywords they rank poorly for but should}
- {review themes showing unmet need}
- {integrations they don't have}
```

One section per profile. Stack profiles into a single comparative view (a matrix across competitors) for strategy sessions.

---

## 6. Quick Tactical Tips

- **Check Wayback Machine on /pricing first** — price history reveals market confidence. Bumps = demand strong. Discounts = desperation.
- **Sort G2 reviews by "Most helpful" AND "Most critical"** separately. Most-helpful = buying criteria; most-critical = deal-breakers you can exploit.
- **Read 1-star reviews before anything else** — they reveal the real friction, not marketing spin.
- **Check GitHub issues on competitor repos** (if open source): labels like `feature-request`, `bug`, `wontfix` are a goldmine.
- **Read competitor changelogs end-to-end** — what they ship reveals strategy; what they *haven't* shipped reveals gaps.
- **Search "leaving {competitor}" on Reddit / HN** — honest switching stories are ICP-language gold.
- **Look at who follows them on LinkedIn** — real ICP, real companies. Better than guessing.
- **Meta Ad Library / Google Ads Transparency Center** — free, shows current live creative for any advertiser. Use to track value-prop iterations.
- **BuiltWith for tech stack + tech changes over time** — dropping Intercom for Zendesk tells you something about support strategy.
- **Trustpilot for B2C DTC** — harder to fake than G2, complaint themes are concrete and recurrent.
- **Don't profile more than 5 competitors at a time** — beyond that, signal drowns in noise. Ruthlessly narrow to direct + aspirational.

---

## 7. Common Mistakes

- **Profiling too shallow**: homepage + pricing only misses the real strategy, which lives in the blog, docs, and reviews.
- **Over-trusting review aggregates**: 4.5-star average with 2000 reviews can hide a systemic 1-star failure. Read the distribution, not the average.
- **Stale data**: a profile from last year is misleading; treat >90 days old as "needs refresh."
- **No persisted raw**: re-scraping every time wastes hours. Always keep raw.
- **Ignoring free-tier behavior**: competitors with generous free tiers are aggressively acquiring; those without are monetizing aggressively. Both require different counter-strategies.
- **Copying their positioning**: competitor research should *differentiate* you, not homogenize you. Anti-pattern: blog posts that are restatements of their blog posts.
