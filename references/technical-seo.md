# Technical SEO Reference

## 1. Critical Technical Checks

### Speed and Performance
- Ad networks can tank site speed instantly -- removing slow ad scripts has caused immediate traffic recovery
- Core Web Vitals (time to first byte, CLS, LCP) are factored into rankings
- Run site through crawl stats in GSC, paste into an AI assistant with "do I look healthy?" for a quick technical audit
- Block add-to-cart URLs in robots.txt -- bots crawling these destabilize e-commerce sites with zero content value

### Mobile and Crawling
- All Google bots since 2016 are full Chromium browsers -- they can render client-side JavaScript
- Single-page apps do NOT strictly need server-side rendering, but Google only invests rendering resources on pages with sufficient authority/links
- Crawlers support 57 file types (HTML is just one) -- PDFs, text files, spreadsheets all get indexed
- Crawling does NOT equal indexing: more crawl does not mean more indexed pages
- Pages with no clicks stop getting re-crawled regularly

### Indexing
- "Crawled, currently not indexed" = Google fetched the page but declined to store it. The problem is almost always authority, NOT quality
- Identical content on a high-authority domain gets indexed; on a low-authority domain it does not -- proving it is an authority signal
- Fix: add an in-body contextual link from a page that already gets traffic
- Duplicate/generic page titles are a top cause of crawled-not-indexed -- differentiate with benefit + brand formula
- Page title formula: `Target Keyword | Benefit or Searcher Goal | Brand Name`

### Accidental Geoblocking
- Surprisingly common: CDN settings, security plugins, compliance filters can block entire countries
- Check at geoblock.net before doing aggressive SEO
- Common culprits: CDN misconfig, overzealous security plugins, server-level geo rules

## 2. Schema Markup Priority

Schema does NOT help you rank in organic search or LLMs for 99% of use cases. It can trigger rich snippets IF you already rank in top positions.

| Priority | Schema Types | When to Use |
|----------|-------------|-------------|
| P0 -- Always | Organization, BreadcrumbList, WebSite (SearchAction) | Foundation for all sites, breadcrumbs look good in SERPs |
| P1 -- Content | Article, HowTo | Only if you already rank and want rich result eligibility |
| P2 -- Commercial | Product, Offer, AggregateRating | E-commerce: helps with price/rating snippets + agentic browsing |
| P3 -- Authority | Person, SameAs, Speakable | Known entities only -- knowledge panel triggers |
| P4 -- Specialized | Flight, Hotel, Event, JobPosting | Niche verticals where Google needs structured data feeds |

### Content-to-Schema Mapping

| Your Content | Primary Schema | Rich Result |
|-------------|---------------|-------------|
| Blog post | Article/BlogPosting | Article carousel |
| Product page | Product + Offer | Price/rating snippet |
| How-to guide | HowTo | Step-by-step rich result |
| Local business | LocalBusiness | Local pack |
| Video content | VideoObject | Video carousel |
| Job listing | JobPosting | Google for Jobs |

### Schema Myths Debunked
- FAQ schema: since 2023, rich results limited to government and health sites only
- Review schema: if your business owns the review, Google will NOT show star ratings
- LLMs do NOT process schema -- they grab raw text from pages, not structured data
- Correlation studies (e.g., "X% of ranking pages have schema") confuse correlation with causation
- Schema is as corruptible as HTML -- it provides zero trust signal

## 3. Site Architecture

### Hub-and-Spoke Model
- Create hub pages for core topics, spoke pages for subtopics
- Internal link from hub to spokes and back -- authority flows through contextual links
- Each link in a page dilutes the others -- authority decays ~85% per link hop
- Pages 3+ clicks from an authority page receive near-zero authority transfer

### Page Hierarchy
- Subfolder membership matters more than navigation placement
- Google does not care about left-nav vs right-nav positioning
- Use HTML sitemaps (actual pages with contextual links) over XML sitemaps for small sites
- Programmatic SEO: ensure category pages (not individual listings) get indexed first

## 4. Robots.txt and AI Crawlers

- Some CDNs now block AI bots by default on new sites -- your content may never be cited by AI assistants
- Check your CDN/hosting settings: ensure AI crawlers (GPTBot, ClaudeBot, PerplexityBot) are not blocked if you want AI visibility
- Block junk URL patterns: add-to-cart, UTM parameters, feed URLs, admin pages
- robots.txt is NOT an instruction set -- it does not force indexing or removal
- Google will crawl everything including penalized sites; robots.txt controls access, not priority

## 5. CMS Considerations

- WordPress: still ~40%+ of the web, best plugin ecosystem for SEO
- One CMS recently launched native integration with a major e-commerce platform -- combining checkout power with SEO flexibility
- AI-powered CMS tools can bulk-optimize product listings but always keep a backup before running AI on your store
- Founders with no technical knowledge can prompt AI into breaking their CMS -- always back up first
- For satellite/EMD domains, use a simple CMS (WordPress, Webflow) even if parent uses something complex

## 6. Free Tools as SEO Assets

- Build free calculators, comparison tools, templates that naturally attract backlinks
- Example: a free tool page can accumulate dozens of organic backlinks from authority sites
- People Also Ask mining: search broad terms, click PAA questions to expand, create dedicated pages for each
- GSC regex filters for commercial investigation keywords: `best|top|vs|review|comparison|alternative`
- GSC AI button: type "show me bottom of funnel searches" to filter purchase-intent queries

## 7. AI Info Page and Footer Optimization

- Create an /ai or /about-ai page explaining your brand for AI crawlers
- Footer links to HTML sitemap help distribute authority on small sites
- Footer should include: sitemap page, key category pages, contact/about pages

## 8. Exact-Match Domains (EMD) as Technical SEO Assets

- EMDs still provide a ranking advantage -- not automatic, but significant when combined with authority
- Strategy: buy EMDs for your highest-value commercial keywords as satellite domains
- Keep EMD cost under 5% of parent domain investment
- Use simple CMS (WordPress) for EMDs even if parent uses something complex
- Link between parent and EMD domains thoughtfully: 50-100 contextual page-to-page links, not site-wide
- EMDs do not need to be connected to your GSC -- can operate anonymously
- Partial-match domains work fine (e.g., freeseoknowledge.com); you do not need exact .com
- Use EMDs defensively: control page 1 narrative, prevent competitors from owning generic keyword domains
- 301-redirect EMDs to relevant hub pages for memorable short URLs in video/social content

## 9. Hosting and Performance

### Bad Neighborhood Effect
- Shared hosting with spammy neighbors CAN negatively impact SEO -- this is NOT a myth
- Hosts to be cautious with: budget hosts that tolerate high spam rates, overcrowded shared servers
- Check your hosting IP: if 50,000+ sites share your IP, consider upgrading
- CDN IPs (e.g., behind a major CDN) are different from hosting IPs -- check the host IP, not the CDN IP

### Recommended Hosting Approach
- WordPress-optimized managed hosts outperform generic shared hosting
- VPS/cloud hosting gives dedicated IP but requires sysadmin skills
- Symptoms of bad hosting: random slowdowns, security incidents, unexplained GSC 500 errors
- If ranking fine with no issues, don't rush to switch -- but monitor for degradation over time

### Dedicated IP vs Dedicated Server
- Dedicated server = your own machine (own house)
- Dedicated IP = your own address on shared hardware (own apartment number)
- IPv4 addresses are scarce; dedicated IPs on shared hosting are increasingly rare

---

## 10. International SEO & Hreflang (v3)

When to implement hreflang:
- Multi-language sites (different translated content per language)
- Multi-region sites (same language, region-specific content — e.g., US vs UK English with different pricing, legal, delivery)
- **Not** needed if: single language, single region, or regional differences too minor to justify separate pages

### Hreflang checklist

- **Every locale self-references** — each page's hreflang set must include itself (`en-US` page must list `en-US` in its own hreflang block)
- **Bidirectional** — if A links to B via hreflang, B must link back to A. One-way hreflang is ignored by Google
- **Language vs language-region** — use `en` alone when content is truly the same for all English speakers; use `en-US` / `en-GB` when copy differs by region (pricing, terminology, legal)
- **X-default** — use for the language picker page or a geo-redirect landing; NOT for your primary-language default (that should self-reference its actual locale)
- **Canonical per locale** — each locale page's canonical points to ITSELF, never to the primary-language version. Common mistake: all `<link rel=canonical>` pointing at the English version — Google then drops all other locales
- **Equivalent content only** — hreflang is for the SAME page in different languages/regions, not for a "similar" page. If the content genuinely differs beyond translation, they're separate pages, not hreflang pairs
- **Multi-locale duplicates** — if `/us/` and `/ca/` serve identical English content, EITHER canonical to one AND don't have a separate locale page, OR keep both and hreflang-link them with region differentiation. Never have duplicates without hreflang

### Implementation options

- `<link rel="alternate" hreflang="...">` in HTML head — simplest, per-page
- HTTP Header `Link:` — for PDFs and non-HTML
- XML sitemap hreflang — scales best for large sites; use when you have 1000+ pages

### Common mistakes

- Using underscores (`en_US`) instead of dashes (`en-US`) — the spec requires dashes
- Invalid country codes (`en-UK` is wrong — the country code is `GB`)
- Missing return tags (one-way references)
- Self-canonical pointing to a different locale
- Hreflang on non-equivalent pages

---

## 11. AI Bot Crawling — Full Posture Reference (v3)

Expanded from Section 4. The full list of AI-relevant User-Agents and how to decide what to allow/block.

### AI crawlers by purpose

| User-Agent | Operator | Purpose |
|------------|----------|---------|
| `GPTBot` | OpenAI | Training data collection |
| `ChatGPT-User` | OpenAI | User-initiated browsing in ChatGPT |
| `OAI-SearchBot` | OpenAI | OpenAI's search index crawling |
| `PerplexityBot` | Perplexity | Training + live search |
| `Perplexity-User` | Perplexity | User-initiated browsing |
| `ClaudeBot` | Anthropic | Training data collection |
| `Claude-Web` | Anthropic | Claude.ai browsing |
| `Google-Extended` | Google | Gemini training (separate from Googlebot — Googlebot is search index) |
| `Applebot-Extended` | Apple | Apple Intelligence training |
| `Amazonbot` | Amazon | Alexa + Amazon AI training |
| `CCBot` | Common Crawl | Feeds many LLMs (training data aggregator) |
| `Bytespider` | ByteDance | TikTok / Doubao AI training |
| `Meta-ExternalAgent` | Meta | Meta AI training |

### Posture options

**A. Full-open (default for most):** allow all. Maximizes AI-visibility. Right for awareness-driven brands, SEO-first sites, and anyone who wants to be cited.

**B. Content-protect (common for publishers):** block training crawlers, allow search-time browsers. Preserves AI visibility in live-search responses while preventing content from being baked into model weights.

```
# robots.txt — content-protect posture
User-agent: GPTBot
Disallow: /

User-agent: Google-Extended
Disallow: /

User-agent: CCBot
Disallow: /

User-agent: Applebot-Extended
Disallow: /

User-agent: Bytespider
Disallow: /

User-agent: Meta-ExternalAgent
Disallow: /

# allow live-search browsers
User-agent: ChatGPT-User
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: ClaudeBot
Allow: /

# everything else default-allow
User-agent: *
Allow: /
```

**C. Lockdown:** block everything AI-related. Rarely the right call — you lose AI-search visibility entirely. Only defensible for paid/premium content that shouldn't be free-summarized.

### Caveats

- robots.txt compliance is **voluntary** — honest crawlers obey; bad actors ignore. For true blocking, use WAF / CDN rules (Cloudflare has AI-bot blocking built in)
- Blocking training crawlers does NOT remove your content from already-trained models. Only new content from that point forward is affected
- Monitor your server logs (or CDN analytics) for AI bot User-Agents to confirm blocks are working and to see who's fetching `/llms.txt` if you publish it
- Some CDNs (Cloudflare, Vercel) block AI bots by default on new sites. Check this first if AI citations are zero — your content may never have been seen by AI systems

---

## 12. URL Patterns & Site Architecture (v3)

Section 3 covers hub-and-spoke conceptually. This section covers URL patterns tactically — what URL shape to use for what page type.

### URL pattern table

| Page type | Good pattern | Bad pattern | Why |
|-----------|--------------|-------------|-----|
| Homepage | `example.com/` | — | — |
| Feature | `/features/{slug}` or `/product/{slug}` | `/f/{slug}` | Clarity > terseness |
| Pricing | `/pricing` | `/plans-2026`, `/pricing-v2` | No dates in URLs |
| Blog post | `/blog/{slug}` | `/blog/2026/04/{slug}` | Date-locked URLs break on evergreen updates |
| Blog category | `/blog/category/{slug}` or `/topics/{slug}` | `/blog?cat=5` | No content behind query params |
| Case study | `/customers/{slug}` | mix of `/customers/` and `/case-studies/` | Pick one pattern, stick with it |
| Docs | `/docs/{section}/{page}` | `/documentation/...` | Keep URLs short |
| Legal | `/legal/privacy`, `/legal/terms` | `/privacy-policy-v2` | No versions in URLs |
| Comparison | `/compare/{competitor}` or `/alternatives/{competitor}` | — | Either works; pick one |
| Integration | `/integrations/{tool}` | `/integration/{tool}` | Consistent plurals |
| Location | `/locations/{city}` | `/near/{city}`, `/city/{name}` | Match user mental model |
| Template/tool | `/templates/{slug}` or `/tools/{slug}` | — | Signals listable content |

### Common URL mistakes

- Dates in URLs (locks your URL to that date; every update needs a redirect)
- Over-nesting (`/products/category/subcategory/sub-sub/item` — 3 levels max is a good rule)
- IDs without slugs (`/posts/12345` — zero SEO value, impossible to remember)
- Query params for content (`?page=2` — use pagination URLs instead for indexable pagination)
- Inconsistent plurals (`/blog/` vs `/article/{slug}` on the same site)
- Trailing-slash inconsistency (pick one convention, 301 the other)
- Changing URLs without 301 redirects — kills accumulated authority instantly
- Uppercase in URLs (`/Products/ItemA`) — treat as case-insensitive but normalize to lowercase

### Navigation rules

- **Header nav**: 4-7 top-level items max; logo left, CTA rightmost, other items priority-ordered (highest-intent on the right, before CTA)
- **Dropdowns**: only when header would exceed 7 items; group by job-to-be-done, not internal org chart
- **Breadcrumbs**: mirror URL hierarchy; all segments clickable except current page; required for any deep content (docs, category trees, multi-step flows)
- **Footer**: organize by column — Product | Resources | Company | Legal (conventional and scannable)
- **Internal linking**: every important page reachable within 3 clicks from homepage. Check with Screaming Frog "click depth" report

### Sitemap format choices

- **ASCII tree** — good for simple visualization in docs or decks
- **Mermaid flowchart** — good when showing relationships, not just hierarchy
- **XML sitemap** — for crawlers; separate concern from visual sitemap (see Section 1)
- **HTML sitemap page** — a real page with links at `/sitemap`. Useful for small sites (<200 pages) with limited internal linking; passes small authority to deep pages
