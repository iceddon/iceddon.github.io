# CLAUDE.md — iceddon.github.io (Claude Code bridge)

@AGENTS.md

Claude-specific extras only; shared rules live in AGENTS.md.

- **Scope:** tiny flat static site (3 HTML pages + root images). No build, no tests — verification is loading pages in a browser and checking links/images.
- **Git discipline:** pushing `main` publishes to GitHub Pages. Commit only when asked; never push. Prefer single small edits per commit.
- **Hooks (`.claude/settings.json`):** allow Read/Grep/Glob and `python3 -m http.server` for preview; deny `git push`, `gh` repo-admin commands, and writes outside the repo root. No permissions for network fetch beyond the local preview server.
- **Evidence:** before claiming a change works, actually render the edited page (local server + browser tool) and confirm images/links resolve; there is no test suite to lean on.
- **Gotchas:** repo is PUBLIC — never echo or commit secrets or personal data; HEIC images won't render in most browsers; root-asset paths break if pages are opened outside the repo root.
