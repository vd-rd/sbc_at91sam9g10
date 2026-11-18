# AGENTS.md

Guidance for AI agents working in this board repository.

## Layout
- `hardware/` — KiCad project.
- `docs/` — documentation site sources (MkDocs); `docs/journal/` is the board journal.
- `resources/` — key reference documents; `resources/REFERENCES.md` is the manifest.
- `scripts/` — board-specific helpers (shared ones live in the central repo).
- `review/` — gitignored working folder for reviews.

## Design reviews
Follow the central process: https://github.com/vd-rd/glasnost.iot/tree/main/docs/review (house-rules.md first, then process.md and checklist.md).

## Rules
- Containers only; nothing installed on the host.
- Read-only during reviews; no design changes or commits unless asked.
- Evidence for every finding; say when a document wasn't opened.
- Findings go to `review/<rev>/FINDINGS.md`; GitHub issues only after the owner has gone through them and says so.
