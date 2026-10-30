# Publication contract

This consumer uses one GitOps publication with native language paths. English is the default at `/`, Brazilian Portuguese uses `/pt-br/`, and Spanish uses `/es/`.

Each translated page has its own canonical URL, HTML language and JSON-LD `inLanguage`. Equivalent source paths produce self/reciprocal hreflang links. `x-default` names the English equivalent when present; no default equivalent is invented. The responsive language menu keeps the current article when its translation exists.

Lists, tag archives, RSS and series stay within their locale. The sitemap includes all indexable canonical pages exactly once. Missing translations, drafts and future posts contribute neither equivalent links nor assets. The default-language 404 retains native noindex metadata and stays out of sitemap and llms.txt. Alias routes retain their canonical destinations rather than separate sitemap identities.

The organization is an `Organization` author. Its localized institutional pages are `AboutPage`, with the same visible organization identity. No Person profile or portrait is fabricated. The official social fallback does not become a `BlogPosting.image`.

The repository keeps the starter's independent fixtures and extends them with successive three-language organization identities. These fixtures remain useful after removing the starter's sample content. Engine regressions also cover private translations, missing default translations, locale-scoped series, corrupt hreflang and verification of a served multilingual artifact.

Before launch:

1. Run `npm ci` and `GOWORK=off make check dry-run` with published dependencies and no local replacements.
2. Review final rendered English, pt-BR and Spanish articles at narrow and desktop widths in light/dark. Check desktop and mobile language menus.
3. Set the real publication timestamp, approve the content and configure the account/zone-scoped production credential. Enable only the Actions publisher.
4. Deploy the validated artifact through the existing workflow and preserve its verification receipt. Do not rebuild it in the deployment job.
5. Use Google's Rich Results Test on an article in each language and the institutional page. Treat crawl/schema eligibility separately from indexing.

A local preview can use an isolated copy with a synthetic publication timestamp to render drafts. That timestamp is a test fixture, not an editorial publication date. No preview is a live publication.

References checked for the implementation:

- [Google localized versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Article structured data](https://developers.google.com/search/docs/appearance/structured-data/article)
- [Organization structured data](https://developers.google.com/search/docs/appearance/structured-data/organization)
