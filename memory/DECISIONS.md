# Decisions Log

Durable decisions worth remembering, with brief rationale. Newest on top.
Not a full changelog — just the "why" that isn't obvious from the diff.

---

## 2026-09-04 — Memory system lives in `memory/` + `CLAUDE.md`, not an external tool
- Chose plain markdown files in-repo (versioned, diffable, no dependencies) over a database or external note tool.
- `CLAUDE.md` is the entry point every session reads automatically; it points to `memory/` for details.
- Rationale: repo is a small static site with a single maintainer workflow via Claude sessions — lowest-friction option that survives across sessions/branches via git.

## (prior) Visual system
- Site redesign adopted a "wondermakers.games-inspired" dark aesthetic (see commit `6716047`). Color tokens (--bg, --panel, --accent, per-team colors, etc.) are centralized in the `<style>` `:root` block in `index.html`. Team-colored text uses separate `*-text` token variants tuned for 4.5:1+ contrast on dark panels — keep using that pattern for any new team-colored text.
