# Working in this repo

Use Beads (`bd`) for all actions and follow-ups; do not recreate `NEXT.md`.
Start with `bd ready`; inspect tasks with `bd show <id>`, claim with
`bd update <id> --claim`, and finish with `bd close <id> --reason "..."`.
Keep speculative work deferred until its stated prerequisite is met.

Git hooks sync Beads through Dolt: `git push` also runs `bd dolt push`;
merge and branch-checkout hooks pull. Sync failures warn without blocking Git.
Run `bd dolt pull` at session start (including after a fast/no-op Git pull),
and `bd dolt push` as the manual fallback or for Beads-only changes.
Setup and recovery: [.beads/README.md](.beads/README.md).

`add-to-agents.md` is the concise snippet copied into other projects;
`CONVENTION.md` is the full spec. Keep them consistent and avoid increasing
always-loaded instructions unnecessarily.
