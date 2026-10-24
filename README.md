# MW4 / DMZ Guide

An Astro static site with 17 guide page shells, plus a home page. HTML is generated at build time; only the four lookup tables load lightweight column-filter JavaScript. No game data, codes, costs, effects, release times or source claims are supplied.

## Local use

Requires Node.js 20.19+ (or a supported newer LTS) and npm.

```sh
npm install
npm run build
npm run preview
```

For development, run `npm run dev`. Open the local URL printed by Astro. The build generates directory-style routes in `dist/`, for example `dist/dmz-mw4/index.html`.

## Content structure

- `src/pages/`: home and the 17 individual file-based guide routes.
- `src/layouts/GuideLayout.astro`: shared navigation, four ordered sections, metadata and footer.
- `src/components/`: status legend, empty tables and lightweight column filtering.
- `src/styles/global.css`: shared responsive styles.

Every guide has Definition, How to use, Main body, and Sources sections. The hub links all guide pages; related pages cross-link according to the supplied skeleton. Tables have headers and empty bodies. Sources use the columns `# | Source | Date | Notes`.

`Last verified: 2026-10-24 (Asia/Shanghai)` is a scaffold placeholder, not a claim that game information was verified. `confirmed` means verified against a primary source; `reported` means an unverified community or secondary claim. Add sourced rows only after verification. Unverified codes must be marked `reported` or omitted. The early access content-boundary table remains empty across confirmed, reported and unverified columns.

The site uses static output, no SPA framework or deployment configuration. Generated output, dependency directories and Astro caches are ignored by Git.
