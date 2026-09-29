# AGENTS.md - reprise-site

## Repo Role

`reprise-site` is the Vite/React microsite for the `Reprise` project page at
danmercede.com/works/reprise/. It owns presentation, metadata, static assets,
and cache config for the site surface.

## Boundaries

- Owns site copy, layout, Open Graph metadata, Vercel config, and static assets.
- Does not own the Reprise gateway: the Python service, Genblaze pipeline
  integration, Object-Lock ledger, evaluation, or tests
  (github.com/OrionArchitekton/reprise).
- Keep product claims grounded in the source project README, `eval/report.md`,
  and verified behavior. Routing counts come from `eval/report.md`; never
  hand-edit them. No hackathon placement is claimed; never state one.
- `constants.ts` (`PRODUCT_DATA`) feeds both the React app and the build-time
  body-bake; edit copy there. Keep `base` in `vite.config.ts` equal to
  `/works/reprise/` so it matches the hub rewrite.

## Authority Order

1. `/home/orion/src/orion-estate/platform/orion-estate-audit/AGENTS.md`
2. Source project: the `reprise` repo README.md, docs/, and eval/report.md
3. This repo's `README.md`, `constants.ts`, `index.html`, and `vercel.json`
4. Vite build output and package scripts

## Validation

```bash
npm install
npm run build
```

For docs-only changes, run `git diff --check` at minimum.
