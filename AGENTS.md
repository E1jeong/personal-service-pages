# Personal Service Pages AI Guide

## Context

This is a code-navigation and safety guide, not project history. Product context, service requirements, roadmap, and history live in the vault-relative `Dev/Project/Personal/personal-service-pages` wiki; resolve it through `_meta/routing-tables.md` or `obsidian-wiki-sync`, then follow the vault root `AGENTS.md`.

Report plans and results in Korean.

## Code Map

| Module | Responsibility | Orient first | Local guide |
| --- | --- | --- | --- |
| Root | Public portal index and shared stylesheet | `index.html`, `site.css` | None |
| `calendar-reminder/` | Calendar reminder landing page and privacy policy | `calendar-reminder/index.html`, `calendar-reminder/privacy.html` | None |

## Change Gates

### Privacy & Compliance
- Public pages only: never commit API tokens, client secrets, credentials, or private calendar data.
- Ensure privacy policy statements strictly match backend operational reality documented in `AI-Ops/device/sub/operations.md`.
- Each new service/tool must maintain its own dedicated subdirectory with `index.html` and, if requesting external OAuth/user data, `privacy.html`.

### Static Architecture
- Keep documents as dependency-free, valid static HTML5 and minimal CSS (`site.css`).
- Do not introduce runtime build systems, bundlers, or package managers unless requested.
- Maintain UTF-8 encoding without BOM and LF line endings.

## Verify

Run the narrowest relevant check:

```bash
# Verify GitHub Pages deployment status
gh api repos/E1jeong/personal-service-pages/pages --jq '{status,html_url}'

# Verify git diff and line endings
git diff --check
```
