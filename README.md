# Arai Hû blog

The organization's English, Brazilian Portuguese and Spanish engineering journal, built from [gazeta-template](https://github.com/araihu/gazeta-template) with the published Gazeta tool and native Margo rendering.

Canonical origin: `https://blog.araihu.com`. English uses `/`; Brazilian Portuguese uses `/pt-br/`; Spanish uses `/es/`. Each page has its own canonical URL, HTML language and JSON-LD language. Translation controls preserve the corresponding article when it exists. `x-default` names its English equivalent, when available. There is no browser-language redirect.

## Editorial state

The introductory `meet-araihu` article exists in all three languages. All versions are drafts without a publication timestamp. Review the prose and assign a real RFC 3339 `publishedAt` before setting `draft = false`. Drafts and their assets remain absent from the publication.

Authorship is institutional `Arai Hû`, represented as `Organization`. Localized `/about/` pages use `AboutPage`. Source claims and editorial positioning are recorded in [editorial sources](docs/editorial-sources.md).

## Development

Requires Go 1.27.3+, Node 24+ and Make.

```sh
npm ci
make check dry-run
make run
```

The preview defaults to port 1313. Check for an existing listener before starting it. `make check` builds and tests the final publication, including independent identity and multilingual fixtures. `make dry-run` packages it with the lockfile's Wrangler version without deploying.

- `site.yaml` owns the origin, brand assets, native language configuration and localized navigation.
- `blog.yaml` owns authors, page types and translated editorial labels.
- `content/` holds English content. `content/pt-br/` and `content/es/` hold matching translated paths.
- `assets/theme.css` uses public Margo/Goshtoso tokens and Gazeta editorial classes.
- `assets/brand/provenance.json` records official artwork sources and checksums. Marks remain unmodified. Keep their NOTICE and license notices.
- `assets/flags/` contains unchanged MIT-licensed SVGs from [flag-icons v7.6.0](https://github.com/lipis/flag-icons/tree/v7.6.0), with license and checksums. `site.yaml` explicitly maps English to the United States, Brazilian Portuguese to Brazil and Spanish to Spain.

The native `locales.selector` setting controls the language menu. Set `enabled: false` to hide it without changing canonical URLs or `hreflang` links. Omit `flags` to keep text-only language choices. Configured flags use a plain compact button beside the theme and search controls, with full language names inside the menu.

Each locale has its own article lists, tags, series and RSS feed. The single sitemap covers all indexable canonical pages. The default-language error document uses native `noindex, follow`, stays out of discovery and must return HTTP 404 for missing routes.

## Deployment

GitHub Actions is the only production publisher. Deployment remains disabled until the launch is approved and the destination is configured. No production credential is stored in this repository.

Configure repository variables `CLOUDFLARE_ACCOUNT_ID`, `CLOUDFLARE_WORKER_NAME=araihu-blog` and the `CLOUDFLARE_API_TOKEN` secret for this account and zone. Set `CLOUDFLARE_DEPLOY_ENABLED=true` only when ready to launch. The domain comes exclusively from `site.base_url`.

The workflow builds and validates a publication, transfers its exact artifact to a separate job, rechecks it without rebuilding, checks current `main`, deploys and verifies the origin against that same artifact. Preserve the `production-verification-<commit>` receipt. Keep `dry_run=true` for a manual pipeline rehearsal. Do not add a competing Workers Builds production deployment.

After a real deployment, run Google's Rich Results Test on one article in each language and the institutional page. A passed test does not establish indexing. No live deployment, Google validation or Search Console registration is implied by a local preview.
