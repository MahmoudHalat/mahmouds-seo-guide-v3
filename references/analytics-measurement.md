# Analytics and Measurement Reference

## 1. AI SEO KPIs (4 Key Metrics)

1. **AI Citation Rate** -- how often your brand/content appears in AI-generated responses (scrape the actual interface, not API)
2. **Grounding Query Coverage** -- what queries AI systems use to surface your content (visible in Bing Webmaster Tools AI Performance tab)
3. **Brand Mention Frequency** -- how often your brand is named vs described generically ("a popular tool") in AI responses
4. **Source Inclusion Rate** -- how often your URLs appear as cited sources in AI answers

## 2. CTR Benchmarks by Position

| Position | Approximate Organic CTR | Notes |
|----------|------------------------|-------|
| 1 | 25-35% | Reduced by ~34.5% when AI Overview present |
| 2 | 12-18% | |
| 3 | 8-12% | |
| 4-5 | 4-8% | Threshold for meaningful CTR optimization |
| 6-10 | 1-4% | Below this, CTR optimization is pointless |
| 11-20 | <1% | Nearly invisible to searchers |
| AI Overview present | Top position loses ~34.5% CTR | But AI Overviews are 99% triggered by informational keywords, not transactional |

- You can only meaningfully improve CTR if you are in positions 1-5 (sometimes up to ~19 for very high volume keywords)
- If not in top positions, focus on getting there first -- meta description tweaks are irrelevant on page 3

## 3. CTR Gap Analysis Method

1. Go to GSC > Performance > Search Results > Compare last 28 days to previous period
2. Click Pages, sort by negative clicks difference
3. Find pages that lost clicks but still have strong impressions
4. Click into the page, turn on Average Position
5. Sort for keywords where you lost clicks AND lost ranking positions
6. These are your priority refresh targets -- update content to better match the search intent
7. A competitor likely improved their page or Google shifted intent expectations

## 4. API vs Real Data Problem

A 2,000-prompt study revealed critical differences between AI tool APIs and their web interfaces:

### ChatGPT (1,000 prompts tested)
| Metric | API Result | Web Interface (Scraped) |
|--------|-----------|------------------------|
| Average response length | 406 words | 743 words |
| Web search triggered | 77% | 100% |
| Sources included | 75% (avg 7 sources) | 100% (avg 16 sources) |
| Brand detection | 92% | 100% |
| **Brand overlap** | **24%** | -- |
| **Source overlap** | **4%** | -- |

### Perplexity (1,000 prompts tested)
| Metric | API Result | Web Interface (Scraped) |
|--------|-----------|------------------------|
| Average response length | 332 words | 433 words |
| Sources per response | ~7 | ~10 |
| **Source overlap** | **8%** | -- |

**Bottom line**: 96% of sources in real ChatGPT answers do NOT appear in API data. If your AI visibility tool uses API data, you are optimizing for a parallel universe your customers never visit.

### Fix
- Manual AI audit: open incognito windows, test real prompts, study actual results (not scalable)
- Use tools that scrape actual web interfaces, not API proxies
- Clean data is NOT accurate data -- API responses are structured but wrong

## 5. Prompt Monitoring Efficiency

- GSC now shows AI prompts: filter queries starting with "I am" to see actual AI-mode prompts surfacing your content
- GSC AI button: type natural language queries like "show me informational searches" or "show me how /articles perform this week vs last year"
- Bing Webmaster Tools > AI Performance tab shows grounding queries AI uses to cite your content
- Take grounding query language and use it high up on your pages, or create new sections/pages for uncovered queries
- Compare branded search volume over time (GSC regex filter) to measure if offsite marketing is driving brand awareness

## 6. Revenue Attribution in Zero-Click Era

- AI Overviews act as a lead qualification filter: tire-kickers get surface answers, serious prospects click through
- Track Google Analytics events and on-page behavior, not just GSC clicks
- Hypothesis: while traffic dips from AI Overviews, conversions stay roughly the same
- Focus on winning clicks that matter -- don't chase every impression
- For affiliate/ad-revenue sites: the traffic loss is real and revenue-impacting (no click = no ad impression = no affiliate click)
- Diversify revenue: digital products, email lists, community memberships survive traffic drops better than pure ad/affiliate models

### Branded Search as Marketing KPI
1. Ask an AI assistant: "My brand is X, my URL is Y. Give me regex for GSC to filter branded searches including variations."
2. Paste regex into GSC > Performance > Query filter
3. Compare last 3 months to previous 3 months
4. Rising branded searches = offsite marketing (social, PR, video) is working

## 7. GSC Best Practices

### Setup
- Submit all URL variations: HTTPS, HTTP, WWW, non-WWW
- Submit homepage and important pages manually via URL Inspection
- Find your sitemap at /sitemap.xml or /sitemap_index.xml, submit it

### Regular Monitoring
- Crawl Stats report: paste into AI assistant for instant technical diagnosis
- Check Pages Indexing report: understand crawled-not-indexed vs discovered-not-indexed
- Manual URL submission is limited to 20-25/day -- reserve for urgent updates (e.g., removing a departed employee from About page)
- 500 error notices may indicate hosting instability, not site bugs
- Impressions data was inflated by rank-tracking bot activity -- after Google capped SERPs at 10 results, impressions dropped up to 50% in some profiles but clicks stayed stable. Your GSC data is now more accurate

### Google Removing num=100
- Google capped search results pages to 10 results, breaking most rank trackers
- Rankings beyond top 10 now show inconsistencies in third-party tools
- GSC remains the most reliable source for position data (especially positions 1-20)
- Strategy shift: focus on "am I in the top 10?" as the primary success metric
- For positions 20-100, rely on GSC data rather than third-party rank trackers

### Commercial Investigation Filter
- GSC regex: `best|top|vs|review|comparison|alternative` to find commercial-intent queries
- These searches show people actively comparing options -- high conversion potential
- Use these terms in H2 headers or create dedicated pages for valuable ones

---

## 8. GA4 & Event Tracking Implementation (v3)

Sections 1-7 cover measurement (KPIs, GSC, AI citation). This section covers *implementation* — how to name events, how to fire them, how to structure UTMs. If you're setting up tracking from scratch or fixing a broken plan, start here.

### Event naming conventions

Rule: `{object}_{action}` in lowercase with underscores. No caps, no versions in names, no vagueness.

| Bad | Good | Why |
|-----|------|-----|
| `SIGNUP_COMPLETED` | `signup_completed` | Case-sensitive tools break on caps |
| `click_signup_button_v2_final` | `signup_submit` | Stop versioning in name — use properties |
| `btn_click` | `demo_request_click` | Meaningless without object |
| `user_did_thing` | `trial_started` | Be specific; avoid "user" prefix (redundant) |
| `pricing_page_click` | `pricing_cta_click` (with `cta_location` property) | What was clicked matters more than where |

### Standard event library (SaaS)

**Marketing site:**
`page_view`, `cta_click`, `pricing_view`, `signup_start`, `signup_complete`, `demo_request`, `blog_read_complete` (fires at 90% scroll), `nav_click`

**Onboarding / activation:**
`onboarding_start`, `onboarding_step_completed` (with `step_number`, `step_name` properties), `activation_milestone` (with `milestone_name`), `first_value_moment`

**Core product:**
`feature_used` (with `feature_name`), `document_created`, `invitation_sent`, `integration_connected`, `report_exported`, `search_performed`

**Commercial:**
`plan_upgraded`, `plan_downgraded`, `subscription_cancelled`, `payment_failed`, `billing_viewed`, `seat_added`

### GA4 gtag syntax

```javascript
gtag('event', 'demo_request_click', {
  page_location: window.location.href,
  cta_location: 'hero',
  plan_interest: 'enterprise'
});
```

With user-scoped properties (for logged-in users):

```javascript
gtag('event', 'trial_started', {
  plan: 'pro',
  trial_length_days: 14,
  user_id: 'u_12345',
  signup_source: 'organic_search'
});
```

Set user properties once at session start:

```javascript
gtag('set', 'user_properties', {
  account_plan: 'pro',
  company_size: '51-200',
  signup_date: '2026-04-23'
});
```

### GTM dataLayer pattern

Alternative to direct gtag — lets marketing manage events without a code deploy.

```javascript
window.dataLayer = window.dataLayer || [];
window.dataLayer.push({
  event: 'trial_started',
  plan: 'pro',
  trial_length_days: 14,
  user_id: 'u_12345'
});
```

**When to use which:**
- **gtag direct**: devs own analytics, events tied to product code, want version control of the tracking plan
- **GTM dataLayer**: marketing owns analytics, events change frequently (campaigns, hero tests), want to add tags without deploys

Don't mix both on the same event — you'll get double-firing. Pick one per event; document which.

### UTM naming conventions

Rule: lowercase, dashes not underscores, consistent values across campaigns.

| Parameter | Purpose | Example values |
|-----------|---------|----------------|
| `utm_source` | The platform | `google`, `linkedin`, `reddit`, `newsletter`, `github` |
| `utm_medium` | Channel type | `cpc`, `organic`, `social`, `email`, `referral`, `display` |
| `utm_campaign` | Specific campaign | `2026-q2-launch`, `black-friday-2025`, `blog-post-title-slug` |
| `utm_content` | Variant/placement | `hero-cta`, `footer-banner`, `subject-a`, `author-bio` |
| `utm_term` | Paid keyword (paid ads only) | `project-management-software` |

Common mistakes:
- Inconsistent casing (`Google` vs `google` splits reporting)
- Spaces in values → encode as `%20` and look ugly; use dashes
- Confusing source and medium (`utm_source=paid` is wrong — `paid` is the medium; source is the platform)
- No `utm_campaign` (everything shows as `(not set)` in reports)
- Using UTMs on internal links (wipes the original attribution; huge bug)

### Validation routine

- Use GA4 **DebugView** in real-time to confirm events fire correctly on staging
- Check that event parameters are captured (not just event name — properties are where the value is)
- Verify UTM capture on landing pages with multiple sources (test from Google, from LinkedIn, from a direct email link)
- Test on both desktop and mobile — mobile often fires differently due to touch vs click handlers
- Confirm events don't double-fire (common bug with GTM + direct gtag; check Network tab for duplicate collect requests)
- Use Tag Assistant (Chrome extension) to confirm GA4 and GTM are both loading and firing
- For conversion events, verify attribution path in GA4's Explorations > Path Exploration
