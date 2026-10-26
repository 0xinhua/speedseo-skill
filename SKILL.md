---
name: seo-geo-blog-writer
description: Research and write SEO/GEO blog articles using DataForSEO, verified facts, and existing-content checks.
---

# SEO / GEO Blog Writer

## Hard Rules

1. **Draft for review, never auto-publish.** Deliver on a feature branch, as a PR, or as a draft file. A human makes the publish call.
2. **Original content.** Never copy or rewrite existing published articles or other authors' content as a new article.
3. **Verify every fact.** Verify every factual claim. Never use speculative wording such as "possibly" or "probably" to fill gaps in evidence.
4. **Research first.** Deep research real user questions and online discussions; include accurate quotes and source links. For commercial keywords, provide clear conclusions, comparison tables, verified pricing, honest pros and cons, and FAQs answering real questions.

5. **Create valuable, non-commodity content.** Follow [Google's guidance](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide):

   - **Offer a unique perspective.** Use first-hand experience or expert analysis. Example: test subtitle tools on the same recording rather than summarize their marketing pages; never invent tests.
   - **Go beyond common knowledge.** Provide evidence that helps readers act or decide. Example: compare observed accuracy, editing time, export limits, and verified pricing.
   - **Organize for readers.** Use clear headings, sections, and paragraphs. Example: group a comparison by accuracy, cost, and suitable use cases.
   - **Use helpful visuals.** Add relevant, high-quality images or video when they clarify the content. Example: show a caption-editing screenshot or export walkthrough.
   - **Serve user needs without overproducing.** Avoid separate pages for minor keyword variations. Example: answer related subtitle-export questions in one useful guide.
   - **Apply the same standards to AI-assisted content.** Meet Google's [Search Essentials](https://developers.google.com/search/docs/essentials) and [spam policies](https://developers.google.com/search/docs/essentials/spam-policies#scaled-content). Example: verify an AI-generated comparison before review; do not mass-produce interchangeable articles.

   Before delivery, ask: does this page help the reader accomplish their goal and leave satisfied?

## Research

For Google AI Search optimization, read and apply [Google's official AI optimization guide](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide) before planning the article. Use it to guide content and technical decisions; do not assume its guidance applies to other AI platforms. If the page cannot be accessed, record the limitation rather than claiming it was reviewed.

1. Read project instructions and related articles. Confirm keyword, audience, language, region, and deliverable.
2. Use DataForSEO for the primary keyword, meaningful variants, available metrics, and Google SERP. Read saved raw data before making new requests. For connection setup, user-provided credentials, direct API requests, and response handling, read [DataForSEO usage](references/dataforseo.md).
3. Read relevant ranking pages, actual AI Overview references, and relevant PAA questions. Separate main-query and variant results; pending or empty responses are not retrieved evidence.
4. Compare existing articles by user task and expected output. Create a new page only if it provides independent value; changing names, titles, or FAQs is insufficient. Preserve existing content and URLs unless changes are requested.
5. Verify product operations, capabilities, login, quotas, payment, and other restrictions. Check changing facts against current official sources. Do not claim testing unless observed.
6. Determine the title, angle, outline, and product role from this evidence, then write.

Save raw responses and a [research record](references/research-record.md) at the project's research location, defaulting to `docs/research/seo-geo/<slug>.md`. Missing metrics are unavailable, not zero. If DataForSEO fails, record the blocker and stop drafting unless the user authorizes an alternative source.

## Write

- Answer immediately. Use concrete actions, short paragraphs, and natural keyword coverage; omit filler, repetition, sales copy, and arbitrary word counts.
- Use relevant researched questions as H2/H3 headings, followed by direct answers or steps. Do not pad the article with unrelated PAA questions or FAQs.
- Make key answers understandable independently, with their limitations beside them and sources near the claims.
- How-to: prerequisites → steps → expected output → relevant limitations. Comparisons: explicit criteria and verified tradeoffs. Explainers: definition and useful examples.
- Include the product and CTA only where they help the task. Never invent facts, features, quotes, data, or results, or promise rankings or AI citations.

## Implement when requested

- Follow existing routes and content components. Align title, H1, canonical, body, and metadata; ensure the body is crawlable.
- Follow [structured-data rules](references/structured-data.md); reuse site helpers and entity IDs.
- Update the blog index, sitemap, and existing `llms.txt` with consistent absolute canonical URLs and no duplicate entries. Use actual publication and substantive-modification dates.
- Check the rendered route, links, mobile layout, canonical, JSON-LD, and relevant build checks.

Deliver article/research paths, the create/refresh/defer decision, checks performed, and unresolved issues.
