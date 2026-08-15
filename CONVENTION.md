# Changelog Convention

How any repo keeps a changelog — text and visual, same file, same trigger. Quick-and-dirty v1: meant to be trialed and revised, not final.

## Copy this into AGENTS.md

This exact block, verbatim, no paraphrasing — the point is every repo ends up with identical instructions, not each agent's own summary of this doc. It's short enough that a session never needs to fetch the rest of this file just to decide *whether* to write an entry — only when it's actually about to write one, or the format is unclear.

```markdown
## Changelog

This repo keeps a `CHANGELOG.md` (dated entries, newest first). At the end
of a work session, if something worth recording actually shipped — skip
trivial sessions (typo fixes, dead ends, no visible outcome) — draft a
dated entry. Screenshots go in `changelog/images/`, embedded inline, if
something visual shipped. First time writing an entry in this repo, or if
the format is unclear: fetch and follow
https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md
```

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

No mandatory before/after pairing — just grab whatever's compelling in the moment (usually the "after"/current state). If a reader wants the comparison, the previous entry's image is already sitting right above the new one in the same file.

## Trigger

At session-checkpoint time (end of a work session / handoff point) — the same moment a `NEXT.md` update happens in repos that use one.

**Skip the entry if the session was trivial** — a typo fix, a failed experiment, pure research/reading, config fiddling with no visible outcome. Write one only when something a reader would actually care about shipped: a feature, a fix, a meaningful piece of content, a visible change. When genuinely unsure, err toward skipping rather than logging noise — a changelog that's mostly filler stops getting read.

1. Did something changelog-worthy ship this session? (See threshold above — not every commit, not every session.)
2. If yes: draft a dated entry, prepend it to `CHANGELOG.md`.
3. If something visual shipped: grab a screenshot/short video at the same moment, commit it to `changelog/images/`, embed it in the entry.

AI drafts the entry from what actually happened in the session; a human skims/edits before it's committed — light curation, not writing from scratch.

## Publishing

Committing the entry to the project's own repo is the automatic, no-decision floor — it always happens, no destination choice required. Anything beyond that (a personal/org site, a weekly review, social media, a newsletter) is always a **manual promote**, never automatic — see `~/src/me/planning/initiatives/changelog-for-me/scqh.md` for the fuller reasoning.

## Not doing yet

- No image hosting (R2 or otherwise) — plain git until volume makes that painful.
- No automated weekly-roll-up script pulling from every project's `CHANGELOG.md` — do that by hand first.
- No auto-posting to social media — promotion is always a manual step.
