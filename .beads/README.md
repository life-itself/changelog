# Beads in this repository

Issues use the `changelog` prefix and embedded Dolt. The sync remote is
`git+ssh://git@github.com/life-itself/changelog.git` (`refs/dolt/data`).
Tracked config, hooks, and JSONL support portability; the local database,
locks, logs, and runtime state stay ignored. JSONL is for viewers and
interchange, **not** database backup or cross-machine sync.

## Normal workflow

```sh
git pull
bd dolt pull
bd ready
bd show <id>
bd update <id> --claim
bd close <id> --reason "Completed"
bd export -o .beads/issues.jsonl
# Review and commit changed files, then:
git push
```

The pre-push hook runs `bd dolt push`; post-merge and branch-checkout hooks
run `bd dolt pull`. Guards prevent recursion. Failures warn without blocking
Git; retry the indicated command manually. For Beads-only work, run
`bd dolt push` directly. Auto-export is enabled but throttled, so explicit
export refreshes the tracked viewer snapshot before committing.

## Fresh clone

```sh
git config core.hooksPath .beads/hooks
bd bootstrap  # only if the local database is not initialized
bd dolt pull
bd status
```

Do not reinitialize an existing database. If sync fails, inspect `bd context`,
`bd dolt remote list`, `bd dolt status`, and `git status` before retrying.
Preserve local work; do not delete the database or force-push as a first remedy.
Offline work can continue locally and sync later.

Setup follows the personal
[Beads playbook](https://github.com/rufuspollock/agent-skills/blob/main/beads-sync-playbook.md).
With the installed bd 1.3.0, use context/status/remote checks for embedded
mode; federation-only config validation is not a check of this GitHub remote.

`NEXT.md` actions were migrated on 2026-09-26. Speculative improvements remain
deferred; the live roll-up trial depends on frontmatter compatibility checks.
