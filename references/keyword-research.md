# Keyword Research Reference

## 1. BID Method (Business potential, Intent, Difficulty)

Every keyword must pass three tests before you commit resources:

**B -- Business Potential**
- Score 1-3: 3 = product is the solution; 2 = product helps but isn't critical; 1 = barely relevant
- Ask: "If I rank #1, does it move the business?" -- revenue, leads, signups
- High-volume keywords with score-1 business value are traps; low-volume score-3 keywords can outperform 10x
- Prioritize keywords where your product is indispensable to solving the searcher's problem

**I -- Intent Verification**
- Google the keyword and study the top 10 results -- the SERP is ground truth
- Check content format: if all results are e-commerce category pages, a blog post will never rank
- Match the dominant format (listicle, product page, tutorial, comparison, tool)
- Look for mixed intent: "best X for Y" = commercial primary + informational secondary

**D -- Difficulty Check**
- Use KD scores as a starting filter (aim KD <20 for new sites) but always dig deeper
- Check referring domains to top-ranking pages -- more domains = stronger page
- Check Domain Rating of competitors -- look for at least one low-DR site in the top 10
- Examine whether the keyword is actually in competitors' page titles and URL slugs
- If nobody targets the keyword properly in title + slug, difficulty drops dramatically regardless of KD score

---

## 2. Opportunity Scoring Formula

**Priority Score** = weighted sum across 5 factors (score each 1-5):

| Factor | Weight | Score 1 | Score 5 |
|--------|--------|---------|---------|
| Search Volume | 20% | <100/mo | >10,000/mo |
| Keyword Difficulty | 25% | KD >80 | KD <20 |
| Business Relevance | 30% | Tangential | Core offering |
| Intent Match | 15% | Informational only | Transactional/commercial |
| Trend Direction | 10% | Declining | Growing |

**Priority tiers**: P0 (4.0-5.0) = create now; P1 (3.0-3.9) = next sprint; P2 (2.0-2.9) = future calendar; P3 (<2.0) = monitor only

**Intent weight multipliers for final ranking**:
- Transactional: 1.5x (avg conversion 5-15%)
- Commercial investigation: 1.3x (avg conversion 2-5%)
- Informational: 1.0x (avg conversion 0.5-2%)

---

## 3. AI Overview Trap Check

- AI overviews appear on many informational queries and reduce clicks to top-ranking pages by ~35%
- Before committing: Google the keyword, read the AI overview, and ask "Am I satisfied or do I need to click?"
- If the AIO fully answers the query with no nuance needed, the keyword is a trap
- Surface-level factual queries (what-is, definitions, unit conversions) are most vulnerable
- Keywords AI has NOT touched yet: free tools (calculators, generators, checkers), comparison shopping, complex multi-step decisions, experience-based reviews
- Tool keywords are currently AI-proof: people need to actually use something, AI cannot replace interaction

---

## 4. Intent-to-Content Format Mapping

| Intent Type | Signal Words | Best Content Format | Conversion Rate |
|-------------|-------------|---------------------|-----------------|
| Educational | what is, meaning, basics, history | Definitive guide, explainer (1500-3000 words) | 0.5-2% |
| Instructional | how to, step by step, tutorial | Step-by-step tutorial, video walkthrough (2000-4000 words) | 0.5-2% |
| Exploratory | types of, methods, techniques | Listicle, roundup, comparison table (2000-3500 words) | 0.5-2% |
| Troubleshooting | why is, fix, error, not working | FAQ, debug guide (800-2000 words) | 0.5-2% |
| Comparison | vs, compared to, alternative | Side-by-side comparison, feature table (2500-4000 words) | 2-5% |
| Best-of | best, top, leading, review | Ranked listicle with mini-reviews (3000-5000 words) | 2-5% |
| Transactional | buy, price, hire, near me, signup | Product page, landing page, pricing page | 5-15% |
| Navigational | [brand], login, dashboard | Homepage, login page, feature page | N/A |

---

## 5. Niche Selection Framework

Four principles (all must be satisfied):

1. **Competition**: choose battles where you can win; avoid niches dominated by massive sites with full-time SEO teams; filter for KD <20 and look for low-DR results in SERPs
2. **Commercial Value**: must have keywords where searchers are comparing solutions, willing to pay; check for modifiers like "best," "vs," "review," "services"
3. **Breadth**: enough topics for 50+ pages over 12 months; avoid ultra-narrow (pulled pork sandwiches) and ultra-wide (food); find a middle layer like "smoking meats"
4. **Personal Interest**: SEO is a long game; choose something you'll sustain effort in for 12-24+ months

**Validation process**: put seed keywords into a research tool, filter KD <20, add commercial modifiers (best, review, vs), verify search volume exists, check that at least some SERPs have low-DR sites ranking

---

## 6. Keyword Expansion Patterns

**Seed + Modifier method**: use AI to generate 10 seed keywords (1-2 words) + 5+ modifiers; combine them in keyword tools to surface hundreds of real queries

**Modifier categories**:
- Format: calculator, checker, generator, template, tool, quiz
- Audience: for beginners, for small business, for enterprise, for [industry]
- High-leverage purchaser: for schools, for government, for hospitals, for agencies, for teams, for universities, for clinics, for startups, for nonprofits
- Commercial: best, top, vs, review, alternative, pricing, free, cheap
- Location: [city], [state], near me, in [region]
- Temporal: 2026, this month, updated, new, latest
- Problem: how to fix, troubleshoot, without [limitation]

**Bottom-of-funnel gold**: keywords with modifiers like "services," "agency," "software," "tool for [use case]" convert highest but have lowest volume -- most SEOs ignore them because tools show "zero volume"

**Competitor mining**: paste competitor domains into a keyword tool, export their rankings, filter for keywords relevant to you that they rank for accidentally (not in their page titles)

**Google Search Console expansion**: filter existing rankings, find keywords at position 4-20 that you're not deliberately targeting, add them to existing pages or create new ones

---

## 7. Topic Clustering / Hub-and-Spoke Architecture

**Structure**: one pillar/hub page (targets the broad keyword) + 10-30 supporting cluster pages (each targets a subtopic) + contextual internal links connecting everything

**How it builds authority**: when search engines see 20 pages covering different aspects of a topic, site trust for that topic increases dramatically vs. one isolated page

**Cluster prioritization**: start with the cluster that feeds your highest-value money page; if manufacturing is your strongest vertical, build that cluster first

**Money page types to build clusters around**:
- Feature/product pages (one per feature keyword)
- Use case/industry pages (one per vertical)
- Comparison pages (your product vs. each top competitor)
- Best-of pages (you write the list, you control the recommendation)

**URL architecture**: use hierarchical subfolders (/uses/email-client/privacy) not flat structures (/email-client-with-privacy) -- flat patterns trigger doorway-page spam flags; hierarchical structures signal topical depth

**Internal linking rules**:
- Every cluster page links to the pillar and to 2-3 sibling cluster pages
- Links must be contextual, woven into body text -- not blogrolls at the bottom
- Limit in-body links to ~5 per page for low-authority sites
- Monitor which pages rank and redirect link equity from those ranking pages toward pages that need a boost
- Reassess internal links monthly: if a page ranks, you can redirect its link equity to the next target

**Content velocity benchmark**: 1 bottom-of-funnel landing page/week + 1 blog post/month = 52 landing pages + 12 authority posts/year
