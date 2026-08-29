# AGENTS.md — iceddon.github.io (ODI's Personal Site)

Instructions for any coding agent (Codex, Cursor, Claude Code via CLAUDE.md import, Gemini CLI, Aider) working in this repository.

**What this is.** A small, public, hand-authored personal website — "ODI's Personal Site" — served from the `iceddon` GitHub org's `iceddon.github.io` repo. Primary language is HTML. There is no build system, no package manager, no framework, and no test suite. The entire site is a handful of files at the repo root:

- `index.html` — main page
- `page2.html` — secondary page
- `socials.html` — social links page
- Images: `A Young ODI.HEIC`, `CSS-Logo.png`, `Instagram_icon.png`, `Snapchat-Logo-2013.png`, `X_logo_2023_original.svg`, `Youtube_logo.png`, `html5.png`

## Verified stack

- Plain HTML pages. Primary language: HTML. No JavaScript files in the tree.
- Deployment target: GitHub Pages from the `main` branch (the repo is named for the GitHub Pages user/org site convention). There is no other verified deploy pipeline — no Actions workflow files, no `package.json`, no `requirements.txt` in the tree.
- Repo size ~1.6 MB, mostly image assets. Last substantive update recorded by the GitHub API: 2024-08-08.

## Repo layout

Flat root directory. No subdirectories, no `src/`, no `build/`. Everything is served from root paths (`/index.html`, `/socials.html`, etc.). Note the HEIC file (`A Young ODI.HEIC`) — that format does not render in most desktop browsers; it is in the tree but may be dead weight or unused `[VERIFY: whether any page references the HEIC]`.

## How to run / verify

There is no build step and no server config in the repo. To preview locally, open the HTML file directly in a browser or serve the directory:

```bash
python3 -m http.server 8000     # then open http://localhost:8000
```

**Tests:** none exist. The repo has no `package.json` and no test scripts. Verification is manual: load each of the three HTML pages, confirm links resolve, confirm image paths are correct (all images are root-relative, so serving from the repo root works). Broken-link and broken-image checks are the only meaningful automated pass.

**Deploy:** pushing to `main` publishes to the Pages site. Treat a push to `main` as a deploy — ask before committing unless the operator explicitly wants the change live.

## Conventions

- Keep it flat and hand-authored. Do not introduce a framework, bundler, Node tooling, or a restructure into subdirectories — the repo's simplicity is its state.
- Markdown/HTML edits only where the operator asks. This is a personal site; content choices are Daniel's, not the agent's.
- Repo is **public**. Anything committed is world-visible: no secrets, no personal contact details that Daniel hasn't already published himself, no client/business material from other AI Factory work.
- Large binaries: reuse the existing root-level image assets rather than adding duplicates.

## What NOT to do

- Do not commit secrets, API keys, or personal data to this public repo.
- Do not invent or add external URLs/scripts (analytics, CDNs, trackers) — none exist in the tree now; adding third-party code to a personal Pages site requires explicit operator approval.
- Do not delete or "clean up" image assets without confirming they are unreferenced — verify against all three HTML files first.
- Do not convert HEIC/PNG assets without operator approval; images may be referenced by pages you haven't inspected.
- No long-running background work without a durable contract (cron / fleet job); this repo rarely needs one anyway.

## Fleet context

- This repo is part of a private multi-project workspace, but it is the ONLY **public** repo in it.
  Never reference internal hostnames, private IPs, local filesystem paths, or other projects in
  anything committed here.
- Treat every commit as a publication.

## Unknowns to verify

- Whether any of the three HTML pages actually reference `A Young ODI.HEIC` (likely unsupported format in browsers).
- Whether GitHub Pages is enabled for the repo and serving from `main` root vs. a branch-specific config — not visible from the file tree alone `[VERIFY: repo Pages settings]`.
- Whether the site has a custom domain configured `[VERIFY]` — nothing in the tree (no CNAME file) confirms or denies one.
- Content/copy intent for `page2.html` and `socials.html` — read them before editing; the profile gives filenames only.

---
*Source: GitHub API repo profile (tree, README, package.json, metadata — README and package.json are empty/absent; all claims above come from that profile). Kit built 2026-08-28. Unknowns tagged [VERIFY].*
