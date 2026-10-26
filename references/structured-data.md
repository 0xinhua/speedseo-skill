# Structured data

- Use valid JSON-LD with `https://schema.org`. Reuse existing components and stable entity IDs; avoid duplicate or conflicting output.
- Use `BlogPosting` or the project's appropriate `Article` subtype. Recommended fields: `@id` (canonical + `#article`), `headline`, `description`, `image`, `datePublished`, `dateModified`, `author`, `publisher`, `mainEntityOfPage`, `inLanguage`. These are editorial recommendations, not universal required fields.
- Match visible content, actual author/publisher, real crawlable images, canonical, and real dates. Never fabricate missing values or freshness.
- Use `BreadcrumbList` for actual navigation, with `position`, `name`, and absolute URLs.
- Add `HowTo` only for a complete visible procedure. Add `FAQPage` only for appropriate visible questions and site-authored answers under applicable rules; neither type is automatic.
- FAQ markup: one entity with `@id` canonical + `#faq`; `mainEntity` contains `Question.name` and `acceptedAnswer` (`Answer.text`). Preserve full visible answers and relevant restrictions; keep them synchronized with body edits.
- Verify current official documentation before claiming search-feature eligibility. Validate rendered JSON-LD, entity references, URLs, and agreement with visible content. Valid markup guarantees neither rich results nor AI citations.
