# SEO Checklists

## 1. New Website Launch Checklist

- [ ] Connect site to Google Search Console (submit HTTPS, HTTP, WWW, non-WWW variations)
- [ ] Submit homepage and key pages via URL Inspection tool
- [ ] Find and submit sitemap (/sitemap.xml or /sitemap_index.xml)
- [ ] Verify no accidental geoblocking (check at geoblock.net)
- [ ] Check robots.txt: block junk URLs (add-to-cart, admin, feed, UTM parameters), ensure AI bots are NOT blocked unless intentional
- [ ] Confirm HTTPS is working on all pages (no mixed content)
- [ ] Set up Google Analytics with conversion events
- [ ] Ensure every page has a unique page title using formula: `Keyword | Benefit | Brand`
- [ ] Ensure every page has a unique H1 matching the target keyword
- [ ] Set up proper heading hierarchy (H1 > H2 > H3) on all page templates
- [ ] Add breadcrumb navigation (BreadcrumbList schema auto-generated is fine)
- [ ] Add Organization schema to homepage
- [ ] Create and link an HTML sitemap page in the footer
- [ ] Verify hosting IP is not in a bad neighborhood (check IP against blacklists via MX Toolbox)
- [ ] Set canonical URLs on all pages
- [ ] Create /about page with author credentials and E-E-A-T signals
- [ ] Connect to Bing Webmaster Tools (for AI grounding query data)

## 2. Content Publishing Checklist

- [ ] Target keyword at the beginning of: page title, URL slug, meta description, H1, first sentence
- [ ] Use keyword VARIATIONS throughout content (not exact-match repetition)
- [ ] Study the SERP: match the dominant format (listicle, guide, comparison, product page)
- [ ] Check Google's filters/features for the query -- they reveal searcher intent (price ranges, categories, etc.)
- [ ] Add the searcher benefit to the page title (not just the keyword)
- [ ] Include multiple options/links where applicable (Google product review guidelines recommend linking to multiple sellers)
- [ ] Add visual proof of expertise (photos, videos of testing, screenshots)
- [ ] Internal link from at least one existing page with traffic to the new page
- [ ] Internal link from the new page back to the relevant hub/cluster page
- [ ] Vary content format across sequential publications -- avoid publishing 5 identical "best X" posts in a row
- [ ] Remove AI writing giveaways (M-dashes, generic phrasing) if using AI assistance
- [ ] Check People Also Ask for the keyword -- add FAQ sections or create dedicated pages
- [ ] Ensure page adds distinct value vs what already ranks (unique angle, data, experience)

## 3. AI Visibility Checklist

- [ ] Verify AI crawlers are NOT blocked in robots.txt or CDN settings (GPTBot, ClaudeBot, PerplexityBot, Google-Extended)
- [ ] Check Bing Webmaster Tools AI Performance tab for grounding queries
- [ ] Use grounding query language high up on your pages
- [ ] Create dedicated pages for grounding queries you do not currently cover well
- [ ] Put brand reviews and expertise on YouTube (most cited source in AI search)
- [ ] Use brand name + "review" format in YouTube titles and descriptions
- [ ] Distribute content across YouTube, TikTok, Instagram, X (most clicked sites in Google, most cited in AI)
- [ ] Monitor actual AI interface results (not API data) -- 96% source mismatch between API and real results
- [ ] Check GSC queries starting with "I am" to see AI prompts surfacing your content
- [ ] Build topical authority: AI query fan-out breaks complex queries into sub-queries and finds the best source for each piece
- [ ] Defend your brand: if fake review videos target your brand on YouTube, create your own review content using the same keyword patterns
- [ ] Reply to comments on social media posts -- engagement algorithms boost visibility (up to 75x for replies vs likes)

## 4. Monthly SEO Maintenance Checklist

- [ ] GSC CTR gap analysis: compare last 28 days to previous period, find pages losing clicks + positions
- [ ] Check crawl stats report in GSC for server errors or anomalies
- [ ] Review "crawled, currently not indexed" pages -- add internal links from high-traffic pages
- [ ] Check for new commercial investigation queries (regex filter: `best|top|vs|review|comparison|alternative`)
- [ ] Update content on pages that have dropped -- refresh data, add new sections, improve formatting
- [ ] Review and respond to new People Also Ask questions in your niche
- [ ] Check Bing AI grounding queries for new terms to target
- [ ] Monitor branded search volume trend (GSC regex filter) -- is brand awareness growing?
- [ ] Verify no new accidental geoblocking or CDN configuration changes
- [ ] Check for broken internal links and redirect chains
- [ ] Review competitors: have any made significant content or UX improvements?
- [ ] Build at least 2-3 quality backlinks from pages that have actual traffic
- [ ] Publish or refresh at least 2-4 pieces of content per month
- [ ] Check YouTube for fake brand review videos -- counter with authentic review content if found

## 5. Algorithm Update Response Protocol

### Within 24 Hours
- [ ] Do NOT panic -- wait for dust to settle (updates take 1-14 days to complete)
- [ ] Check GSC: is the drop in clicks, impressions, or both?
- [ ] Verify it is not a tracking issue (third-party tools may be broken, especially after Google SERP changes)
- [ ] Cross-reference timing with known updates (Search Engine Roundtable, Google Search Status Dashboard)

### Within 1 Week
- [ ] Determine scope: site-wide or specific pages/sections?
- [ ] Check if the drop correlates with a technical change you made
- [ ] If technical: revert to last known healthy version
- [ ] If algorithmic: do NOT make drastic changes yet -- observe patterns across your industry

### Within 2-4 Weeks
- [ ] Run content audit: which pages lost the most visibility?
- [ ] Study what IS ranking now for your target keywords -- has intent shifted?
- [ ] Identify patterns: are you suffering from topical sprawl, thin content, or UX problems?
- [ ] Make targeted improvements to 3-5 priority pages (one change at a time)
- [ ] Do NOT hire an expensive agency in panic mode -- many HCU-hit sites spent heavily on agencies with no recovery

### Ongoing (Post-Update)
- [ ] Test one hypothesis at a time, measure results
- [ ] Monitor GSC weekly for signs of recovery
- [ ] Accelerate diversification: YouTube, email list, direct products
- [ ] Prepare mentally: recovery may be partial and slow -- plan finances assuming no recovery for 6-12 months
- [ ] Share findings with the SEO community -- collective testing produces better insights than Google's public statements
