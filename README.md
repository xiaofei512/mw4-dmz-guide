# MW4 / DMZ Guide

An Astro static site with 17 guide page shells, plus a home page. A1–A7 and B1–B4 contain the supplied draft structure, placeholder copy and source tables, pending verification. B5–B10 retain their scaffolds. HTML is generated at build time; only the four lookup tables load lightweight column-filter JavaScript. No game values, code strings, costs, effects, exact release times or prices have been added.

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

Every guide has Definition, How to use, Main body, and Sources sections. The hub links all guide pages; related pages cross-link according to the supplied skeleton. Draft lookup tables contain only “待核” template rows with `reported` status and blank row-level Sources. Source tables retain the draft’s official links and “待补” entries; these do not verify the template rows.

`Last verified: 2026-10-24 (Asia/Shanghai; 草稿，待核)` marks the draft date, not a claim that game information was verified in this paste. Status labels are copied from the draft: `confirmed` refers to official or reproducible primary sources or independently checked on-site scope; `reported` means an unverified community or secondary claim. Add game-data rows only after verification. Unverified codes must be marked `reported` or omitted. The early access content-boundary table retains the draft’s confirmed structure, reported claims and explicitly unverified categories without adding playable-content promises.

The site uses static output, no SPA framework or deployment configuration. Generated output, dependency directories and Astro caches are ignored by Git.
