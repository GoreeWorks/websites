# GoreeWorks Websites

Public website source for GoreeWorks, built as a static Astro site and intended for deployment through Cloudflare Pages.

## Project metadata

- Repository: `GoreeWorks/websites`
- Internal version: `0.2.0-dev.1`
- Public version: `0.1.0`
- Version name: `Foundation`
- Production branch: `main`
- Node.js: `24.21.0`

## Technology

- Astro 7
- Tailwind CSS 4 through the official Vite plugin
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

The repository pins Node.js through `.nvmrc`, which Cloudflare Pages reads during builds. No Cloudflare runtime adapter is required for the current site because it is statically generated. If server-side rendering, Pages Functions, or Cloudflare bindings are introduced later, the deployment configuration should be reviewed at that time.

Static Pages responses also use `public/_headers` for additional browser hardening.

## Structure

```text
src/
  components/   Shared site UI
  layouts/      Shared page layout and metadata
  pages/        Route entry points
  styles/       Global styling and design tokens
public/
  _headers      Cloudflare Pages response headers
```

## Content direction

The site reflects GoreeWorks' company identity: creative, modern, independent, premium, innovative, human, thoughtful, and reliable. Public copy should remain consistent with the authoritative GoreeWorks company documentation.

## Version control

Source changes are tracked through Git history. Public release numbers and internal development versions are maintained separately in this README and the package metadata.

A GitHub Actions build check runs on pushes to `main` and on pull requests.
