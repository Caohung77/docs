# SkillDiscs Public Docs (Mintlify)

Public API documentation site for the SkillDiscs API. Powered by [Mintlify](https://mintlify.com).

## Local preview

```bash
npm install -g mint
cd docs-site
mint dev
```

Opens at http://localhost:3000.

## Deploy

1. Sign in to https://dashboard.mintlify.com with the project's GitHub account.
2. Click **Add deployment** → connect this repo.
3. Set the docs root to `docs-site/`.
4. Add a custom domain (e.g. `docs.skilldiscs.com`) and the CNAME Mintlify provides at the DNS host.
5. Push to `main` → docs auto-rebuild.

## Structure

```
docs-site/
├── docs.json              # Mintlify config (theme, nav, navbar)
├── index.mdx              # Landing
├── quickstart.mdx
├── authentication.mdx
├── api-reference/
│   ├── introduction.mdx
│   ├── search.mdx         # POST /api/v1/search
│   ├── list-disks.mdx     # GET  /api/v1/disks
│   ├── get-disk.mdx       # GET  /api/v1/disks/{id}
│   └── batch.mdx          # POST /api/v1/disks/batch
├── guides/
│   ├── llm-agents.mdx
│   ├── rate-limits.mdx
│   └── errors.mdx
├── logo/
│   ├── light.svg
│   └── dark.svg
└── favicon.svg
```

## Updating

Edit MDX files, push to `main`. Mintlify rebuilds in ~30s.

When `api/v1/*` endpoints change in the main app, mirror the change in `api-reference/*.mdx`. Schema is hand-maintained (no OpenAPI source of truth yet — add `openapi.json` later if churn justifies it).
