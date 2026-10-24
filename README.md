# MW4 / DMZ Guide

An Astro static site with 17 topic guides, plus a home page. The initial content draft covers release and platform information, campaign and early access, DMZ tables and locations, and patch and map indexes. HTML is generated at build time; only the four lookup tables load lightweight column-filter JavaScript. Unverified data is left blank or omitted.

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
- `src/components/`: status legend, lookup tables and lightweight column filtering.
- `src/styles/global.css`: shared responsive styles.

Every guide has Definition, How to use, Main body, and Sources sections. The hub links all guide pages; related pages cross-link according to the supplied skeleton. Lookup tables now include documented entries alongside explicitly pending rows and `reported` community claims. Source tables retain official links and pending entries; these do not verify the pending rows.

`Last verified: 2026-10-24 (Asia/Shanghai; 草稿，待核)` marks the draft date, not a claim that every entry is verified. Status labels are copied from the draft: `confirmed` refers to official or reproducible primary sources or independently checked on-site scope; `reported` means an unverified community or secondary claim. Add game-data rows only after verification. Unverified codes are omitted. The early access content-boundary table retains the draft’s confirmed structure, reported claims and explicitly unverified categories without adding playable-content promises.

The site uses static output, no SPA framework or deployment configuration. Generated output, dependency directories and Astro caches are ignored by Git.

## Changelog / release notes

**Version: 0.1.0-draft (pending confirmation)** · October 24, 2026 (Asia/Shanghai) · Covers merged PRs #1–#7.

**Site status: not yet live (待上线).** Hosting and domain are undecided; no public site URL is available.

### Changelog

#### New features

- Added the static guide site structure: a home page and 17 topic routes covering release, platforms, modes and DMZ. Guides follow Definition → How to use → Main body/tables → Sources and update dates, with confidence labels and verification dates in the footer. ([PR #1](https://github.com/xiaofei512/mw4-dmz-guide/pull/1))
- Added initial content outlines for seven release/platform/mode guides and four priority DMZ guides, with filterable table templates for keys, FOB, traits and Stranded. Game values were left blank rather than invented. ([PR #2](https://github.com/xiaofei512/mw4-dmz-guide/pull/2))
- Added the verifiable FOB unlock table (14 rows), trait mechanics (9 rows) and Major Traits table (21 rows). Cost and point fields remain blank. ([PR #3](https://github.com/xiaofei512/mw4-dmz-guide/pull/3))
- Expanded the keys page's mechanics and appendix outlines, and clarified the boundary between Stranded and non-DMZ content. Unverified code strings remain omitted. ([PR #3](https://github.com/xiaofei512/mw4-dmz-guide/pull/3))
- Added verifiable FAQ facts for release/platform/mode guides, including release calendar dates, campaign mission count and the game's absence from Game Pass at release. Updated the guide hub to show the current DMZ table status. ([PR #4](https://github.com/xiaofei512/mw4-dmz-guide/pull/4))
- Expanded the keys table to 39 verifiable key-name entries, with mechanics/set entries first and other names ordered A–Z. Community summaries of what keys open remain `reported`, never promoted to `confirmed`. ([PR #6](https://github.com/xiaofei512/mw4-dmz-guide/pull/6))
- Added content for the remaining six DMZ guides: Police Station, Radio Tower, solo play, whether DMZ is free, the patch notes index and the map index. The map index is not a full-map tool. ([PR #7](https://github.com/xiaofei512/mw4-dmz-guide/pull/7))

#### Improvements

- Displayed both public dates on the release and Steam pages: the **official global release date, October 23, 2026**, and **Steam's store Release Date, Oct 22, 2026**. No explanation for the difference is inferred; no exact launch times, on-site prices or numeric AppID fields are provided. ([PR #5](https://github.com/xiaofei512/mw4-dmz-guide/pull/5))
- Kept Steam as an external-link entry point and updated verification dates in the related FAQs and source entries. ([PR #5](https://github.com/xiaofei512/mw4-dmz-guide/pull/5))
- Refined status wording in populated filterable tables to distinguish `confirmed` information from `reported` community claims. ([PR #3](https://github.com/xiaofei512/mw4-dmz-guide/pull/3))
- Replaced generic pending-table placeholders in the guide hub with each topic's current progress. ([PR #4](https://github.com/xiaofei512/mw4-dmz-guide/pull/4))

#### Fixes

No user-facing defect fixes in this batch: PRs #1–#7 establish the initial content draft. Any later copy or link corrections will be recorded in a subsequent changelog.

### Release notes

This is the first content draft of the MW4 (Black Ops 7) / DMZ player guide, version **0.1.0-draft (pending confirmation)**. It organizes release and platform information, campaign and early access, DMZ keys/FOB/traits, key locations, patch notes and map indexes into 17 topic pages plus a home page.

Pages aim to provide checkable public sources and distinguish `confirmed` information from `reported` community claims. Unverified location grids, prices, exact launch times and cost tiers are intentionally left blank to avoid presenting unverified claims as established facts.

The covered changes are merged into `main`, but the public site is **not yet live (待上线)**; hosting and domain remain undecided. Use `npm install`, `npm run build` and `npm run preview` as described above to preview locally.

### Hard rules

1. **Confidence:** `confirmed` means official information or primary-source scope that can be independently checked; `reported` means an unverified community or secondary claim. Never promote the latter to the former.
2. **No invented data:** Do not supply exact launch times, on-site price/discount fields, location Grid coordinates, cost tiers, unverified code strings or definitive “best” rankings.
3. **Both dates, no inferred explanation:** Present Steam's Oct 22, 2026 store date alongside the official October 23, 2026 global release date. Do not speculate about time zones, preloads or store-page errors to explain the difference.
4. **Site status:** Without a hosting URL, describe the site as **not yet live (待上线)**. Do not invent a domain.
5. **One topic per page:** Do not turn the home page into a full Hajin map. The map page is an index, not a complete map tool.
