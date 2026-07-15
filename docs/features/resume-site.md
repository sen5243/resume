# Feature: Resume Site

**Status**: Shipped
**Last updated**: 2026-07-15

## What was built

A personal resume for Teoh Yong Sen, published as a GitHub repo and a static site on Vercel.

- **`README.md`** — markdown resume rendered on the GitHub repo page: About, Skills, Experience (Kasagi Labo, Vintedge), Education.
- **`index.html`** — single self-contained HTML page with the same content, deployed to Vercel.

## Live URLs

- Production: https://resume-lime-mu.vercel.app
- Aliases: https://resume-sen5243s-projects.vercel.app
- Repo: https://github.com/sen5243/resume
- Vercel project: `sen5243s-projects/resume`

## Design decisions

- Fonts (Google Fonts): Zen Kaku Gothic New (headings), IBM Plex Sans (body), IBM Plex Mono (dates, labels).
- Palette: paper `#fafaf7`, ink `#17171d`, gray `#5d6069`, indigo accent `#2b4a9b`.
- Layout: single column, max-width 46rem; two-column grid rows (mono date rail + content) for skills, experience, and education; stacks to one column under 34rem.
- Includes a print stylesheet (Cmd+P produces a clean PDF), `prefers-reduced-motion` support, and visible focus outlines.

## Content constraints (user requirements)

- No Japanese text anywhere.
- No mention of "anime" (say "interactive content and community platform" instead).
- Do not label work as "frontend" (use "web", "user-facing", "client-side" instead).
- No em dashes (—) in any text; hyphens and markdown `---` rules are fine.
- About section: first-person, human tone, ATS-friendly (plain text, standard headings, all technology keywords spelled out, no emoji).

## ATS assessment (2026-07-15)

Content meets ATS standards: standard headings, reverse-chronological roles with title/company/location/dates, plain-text keywords, no emoji or graphics. Known gaps if the printed PDF is used for real applications:

All gaps fixed on 2026-07-15 with user approval:

1. Contact row now includes tys5243@gmail.com and 016-450 8189 (both page and README).
2. Print stylesheet collapses the two-column date-rail grid to a single column with inline dates, so the printed PDF parses in document order.
3. "About" heading renamed to "Summary"; "Present" capitalized.

## Deployment

One-off CLI deploys: `npx vercel deploy --prod --yes` from the repo root (logged in as `sen5243`). The repo is **not** Git-connected to Vercel, so pushes to GitHub do not auto-deploy; redeploy manually after changes.
