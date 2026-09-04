# AMBL

Single-page static site for AMBL (Season 31) — a fantasy-football-style league:
schedule, rosters, box scores, standings. Everything lives in `index.html`
(HTML/CSS/JS, no build step, no backend).

## Repo memory system

This repo keeps a running memory of decisions, progress, and open tasks in
`memory/`, so any session (human or Claude) can pick up context fast:

- `memory/PROGRESS.md` — dated log of what was done each session, newest entry on top.
- `memory/DECISIONS.md` — durable decisions and their rationale (design direction, data conventions, naming, etc).
- `memory/TASKS.md` — open/in-progress/done task list.

**Maintenance expectations (for Claude):**
- At the start of a session, skim `memory/PROGRESS.md` (latest few entries) and `memory/TASKS.md` before making changes.
- At the end of a session that changed the site or repo, append a `PROGRESS.md` entry (date, summary, files touched).
- When a non-obvious choice is made (visual direction, data structure, naming convention, tradeoff), record it in `DECISIONS.md` — don't just leave it implicit in a commit.
- Keep `TASKS.md` in sync: move items across Open/In Progress/Done as work happens; add new tasks the user mentions even if not immediately actioned.
- Keep entries short and skimmable. This is a memory aid, not documentation of the product itself.

## Notes for future sessions

- No package.json / build tooling — just edit `index.html` directly and open it in a browser to check changes.
- Team color tokens, section structure, etc. are defined in the `<style>` block at the top of `index.html`.
