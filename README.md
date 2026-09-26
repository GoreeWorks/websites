# GoreeWorks Websites

Public website source for GoreeWorks, built as a static Astro site for deployment through Cloudflare Pages.

## Project metadata

- Repository: `GoreeWorks/websites`
- Internal version: `0.3.0-dev.2`
- Public version: `0.1.0`
- Version name: `Material One Integration`
- Production branch: `main`
- Node.js: `24.21.0`

## Authoritative dependencies

### Material One

All interface work follows the GoreeWorks Material One standard.

- Authoritative repository: `GoreeWorks/material-one`
- Validated source commit: `f826dd6c09c55fd17eddaf213609b781c64e2c55`
- Website usage: semantic color tokens, responsive components, accessible typography, adaptive layout behavior, interaction states, density and reduced-motion behavior
- Deployment model: controlled vendoring of the exact CSS primitives used by the website

Vendored Material One files live under `src/styles/material-one/`. Each vendored file records its authoritative source path, source commit, and source blob SHA. Material One remains authoritative; the copies in this repository exist only because the Material One monorepo currently contains unpublished workspace dependencies and cannot be installed as a production Git dependency.

Current source blobs:

- `tokens/css/material-one.css`: `2842d981890cdf5ada7cce971fb87cac3bd164d6`
- `packages/components/css/material-one-components.css`: `d209b7c0a48cbbef333229fd7446ccb9201fc24f`
- `packages/typography/css/material-one-typography.css`: `6672de5757b682ff15b6684acf463cc4fdfd1358`

Update these copies deliberately when adopting a newer validated Material One revision.

### Brand assets

The deployed GoreeWorks mark at `public/brand/goreeworks-mark.svg` is an operational copy of:

- Authoritative repository: `GoreeWorks/brand-assets`
- Authoritative path: `logos/goreeworks-mark.svg`
- Source blob SHA: `152f793661b2e4fc31402ccc52776e3e4aba3fb8`

Brand assets remain authoritative in `GoreeWorks/brand-assets`; copies in this repository exist only when required for website deployment.

## Technology

- Astro 7
- Material One
- Static output for Cloudflare Pages

## Development

```bash
npm install
npm run dev
```

Create a production build with:

```bash
npm run build
```

The generated site is written to `dist/`.

## Cloudflare Pages

Connect this repository to Cloudflare Pages with:

- Production branch: `main`
- Build command: `npm run build`
- Build output directory: `dist`

The repository pins Node.js through `.nvmrc`. No Cloudflare runtime adapter is required for the current site because it is statically generated. If server-side rendering, Pages Functions, or Cloudflare bindings are introduced later, deployment configuration must be reviewed at that time.

Static Pages responses use `public/_headers` for browser hardening.

## Structure

```text
src/
  components/   Shared site UI
  layouts/      Shared page layout and metadata
  pages/        Route entry points
  styles/
    material-one/  Controlled deployment copies of authoritative Material One CSS
    global.css     GoreeWorks product layer using Material One semantics
public/
  brand/        Deployment copies of authoritative brand assets
  _headers      Cloudflare Pages response headers
```

## Content direction

Public copy should remain consistent with authoritative GoreeWorks company documentation. The current experience applies the Material One design system while preserving GoreeWorks' individual product identity.

## Version control

Source changes are tracked through Git history. Public release numbers and internal development versions are maintained separately in this README and package metadata.

A GitHub Actions build check runs on pushes to `main` and on pull requests.
