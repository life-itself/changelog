# Changelog Convention

How any repo keeps a changelog — text and visual, same file, same trigger. Quick-and-dirty v1: meant to be trialed and revised, not final.

## File

One `CHANGELOG.md` at the repo root. Dated entries, newest first — not version-numbered releases, since most of these repos ship continuously rather than cutting formal releases. If a repo *does* do versioned releases, use `## [1.2.0] - 2026-08-15` instead of a bare date; otherwise use the date alone.

```markdown
## 2026-08-15 — Short title

Optional image, if something visual shipped this session:

![Caption describing the moment](changelog/images/2026-08-15-short-title.png)

One or two sentences, written for a reader, not a raw commit-message dump.

## 2026-08-08 — Previous entry
...
```

## Images

`changelog/images/YYYY-MM-DD-slug.png` (or `.mp4`/`.mov` for a short video) inside the project's **own** repo — not a separate changelog repo. Plain git commit; no external hosting for v1. Referenced inline from the `CHANGELOG.md` entry via a relative path, as above.

## Trigger

At session-checkpoint time (end of a work session / handoff point) — the same moment a `NEXT.md` update happens in repos that use one. Draft the entry as a standard step then, not as a separate remembered task:

1. Did something changelog-worthy happen this session? (A shipped chunk of work, not every commit.)
2. If yes: draft a dated entry, prepend it to `CHANGELOG.md`.
3. If something visual shipped: grab a screenshot/short video at the same moment, commit it to `changelog/images/`, embed it in the entry.

AI drafts the entry from what actually happened in the session; a human skims/edits before it's committed — light curation, not writing from scratch.

## Publishing

Committing the entry to the project's own repo is the automatic, no-decision floor — it always happens, no destination choice required. Anything beyond that (a personal/org site, a weekly review, social media, a newsletter) is always a **manual promote**, never automatic — see `~/src/me/planning/initiatives/changelog-for-me/scqh.md` for the fuller reasoning.

## Not doing yet

- No image hosting (R2 or otherwise) — plain git until volume makes that painful.
- No automated weekly-roll-up script pulling from every project's `CHANGELOG.md` — do that by hand first.
- No auto-posting to social media — promotion is always a manual step.
