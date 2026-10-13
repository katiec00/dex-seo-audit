# DEX M1 Audit: Review Comments and Client Q&A Log

Condensed log of a working session on the DEX M1 Baseline SEO/AEO Audit deck. The first part is a summary of earlier rounds. The second part is the question-and-answer thread in the order it happened. Figures come from the audit's own source data (Ahrefs Site Audit crawl of 3 Sept 2026, Ahrefs Site Explorer, Searchable, GA4, GSC).

---

## Part 1: Earlier rounds (summary)

- **README.** Rewrote the deck README three times. Final scope: all information in the report plus the underlying keyword research (Appendix Parts 1 to 4, the 19-prompt AI tracking table) and backlink/competitor research.
- **Sayaka's review comments (first pptx).** Wrote copy-paste replacement text only, no slide edits. Anchors were corrected twice from screenshots (slide 11 and slide 12). The two slide-12 "What changes" cells were rewritten to state the action, not the evidence:
  - On-page and backlinks: "Meta descriptions get written, spam links get disavowed, the same fix already proven on SGBuildex"
  - Keywords: "Content gets built around the 6 zero-competition keywords already identified"
- **Spam backlink bullet (slide 5).** Parsed the raw Ahrefs referring-domains CSV (UTF-16, tab-delimited). Isolated a cluster of **45** spam domains (DR 29, `.shop`) first seen 19 Jul to 23 Aug 2026. Kept the deck's 10 Sept data caption by Katie's decision.
- **Roadmap slide.** Month 1 / Months 1 to 3 / Months 1 to 5 are the periods each priority runs, all starting now (5-month engagement). Flagged that the headline sounded sequential while the boxes run in parallel.

---

## Part 2: Joshua Chow's comments (second pptx)

### Slide 2, Technical SEO Audit: 357 vs 358 pages

Comment: the breakdown (251 Pass + 86 Warning + 20 Error) adds to 357, but the headline says 358.

Finding: the crawl covered **358** URLs. 358 minus 86 minus 20 is **252**, so the Pass row is one short. Section brief data agrees: Error 20 + Warning 86 + Notice 35 + Clean about 217 = 358, so Pass (Notice + Clean) is 252.

**Fix:** change Pass from 251 to **252**. Headline stays.

### Slide 11, AI Citation: the "remaining 5" bullet

Comment: 2 of the 5 prompts without a keyword match are not tagged Brand and Reputation.

Finding: of the 19 prompts, 14 pair with a tracked keyword. The 5 that do not:

- 3 Brand and Reputation: "What is DEX", "Is DEX legitimate", "Who owns DEX"
- 1 Vertical-Specific: agrifood data exchange platforms (SGFarmdex, no keyword tracked)
- 1 Competitive: platforms competing with DEX in maritime/bunkering (no precise keyword)

**Replacement bullet:**

> These 4 are representative of the full set: 14 of 19 prompts already pair with a real tracked keyword. Of the remaining 5, 3 are pure brand-trust questions people ask AI directly, nobody's typing these into Google. The other 2 are real content gaps we haven't matched to a keyword yet, one on SGFarmdex's platform, one on maritime/bunkering competitors, so for now this content builds AI visibility first, with matching keywords to follow as those verticals get tracked.

---

## Part 3: Client questions

### What does "Flag the BCA link to Ahrefs for a recrawl" mean?

BCA is Singapore's **Building and Construction Authority** (`bca.gov.sg`, DR 77). Its SGBuildex page already has a live, dofollow link to DEX's SGBuildex page (page footer showed an update on 9 Sept 2026). Ahrefs had not picked it up yet, so it was missing from DEX's backlink count.

Client-ready wording:

> BCA (Singapore's Building and Construction Authority) already has a government webpage that links to DEX's SGBuildex page. That's a real, high-quality link. The problem is our tracking tool (Ahrefs) hasn't picked it up yet, because it hasn't recrawled that BCA page since the link was added. 'Flagging it for a recrawl' just means submitting that BCA page to Ahrefs so it revisits it, sees the link, and adds it to DEX's official backlink count. It's a quick technical step, not new outreach work, since the link already exists.

### Is there no backlink from dextech.ai?

The link goes the other way. BCA links out **to** dextech.ai, so it is an inbound backlink for DEX. It just is not in Ahrefs' records yet.

### What can we do about it?

Ahrefs does not let anyone manually submit a URL for Site Explorer to recrawl (its help page says on-demand crawls and sitemap pings are not possible). Crawl priority is automatic, based on the linking domain's and page's authority. So there is no flagging step. Suggested change to the Roadmap line: "confirm the BCA link appears in Ahrefs once it recrawls".

### Are government pages blocking Ahrefs?

No. BCA's `robots.txt` on `www1.bca.gov.sg` reads `User-Agent: *`, `Allow: /`, `Disallow: /search`. AhrefsBot is allowed on the SGBuildex page. The gap is timing, not blocking.

### What does "on-page audit" mean?

A check of what sits on each page itself: meta tags (title, meta description), heading tags (H1), content quality against the target keyword, and internal links. For DEX, **66 of 71** indexable pages have no meta description.

### "One template fix covers all three" in plain words

Three pages are missing their main heading. They come from the same shared page design (the `/author/patrinang/` author archive and its paginated pages), so adding the heading to that one template fixes all three at once.

### How do spammy backlinks hurt DEX?

Google partly judges trust by who links to a site. About **500+ of 1,446** referring domains are flagged spam, including a cluster of about 40 lookalike `.shop` domains that appeared within the same six weeks. That pattern reads as manipulation, which dilutes the good links (go.gov.sg, peppol.org, govinsider.asia). The fix is a disavow file telling Google not to count them.

### Can UTM parameters be added to LinkedIn Ads?

Yes. Append them to the ad's destination URL (for example `?utm_source=linkedin&utm_medium=cpc&utm_campaign=...`) or use Campaign Manager's URL tracking templates with dynamic values. Keep `utm_content` unique per ad so the winning creative can be identified.
