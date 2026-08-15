# Changelog Convention

How any repo keeps a changelog — text and visual, same file, same trigger. Quick-and-dirty v1: meant to be trialed and revised, not final.

The short version that goes into a repo's `AGENTS.md` lives in its own file, [add-to-agents.md](add-to-agents.md) — copy its whole content in, don't paraphrase this longer doc. This file is the full spec that snippet points to once an entry's actually being drafted.

## File

One `changelog.md` at the repo root. Dated entries, newest first — not version-numbered releases, since most of these repos ship continuously rather than cutting formal releases. If a repo *does* do versioned releases, use `## [1.2.0] - 2026-08-15` instead of a bare date; otherwise use the date alone.

```markdown
## 2026-08-15 — Short title

Optional image, if something visual shipped this session:

![Caption describing the moment](changelog/images/2026-08-15-short-title.png)

One or two sentences, written for a reader, not a raw commit-message dump.

## 2026-08-08 — Previous entry
...
```

## Images

`changelog/images/YYYY-MM-DD-slug.png` (or `.mp4`/`.mov` for a short video) inside the project's **own** repo — not a separate changelog repo. Plain git commit; no external hosting for v1. Referenced inline from the `changelog.md` entry via a relative path, as above.

No mandatory before/after pairing — just grab whatever's compelling in the moment (usually the "after"/current state). If a reader wants the comparison, the previous entry's image is already sitting right above the new one in the same file.

## Trigger

At session-checkpoint time (end of a work session / handoff point) — the same moment a `NEXT.md` update happens in repos that use one.

**Skip the entry if the session was trivial** — a typo fix, a failed experiment, pure research/reading, config fiddling with no visible outcome. Write one only when something a reader would actually care about shipped: a feature, a fix, a meaningful piece of content, a visible change. When genuinely unsure, err toward skipping rather than logging noise — a changelog that's mostly filler stops getting read.

1. Did something changelog-worthy ship this session? (See threshold above — not every commit, not every session.)
2. If yes: draft a dated entry, prepend it to `changelog.md`.
3. If something visual shipped: grab a screenshot/short video at the same moment, commit it to `changelog/images/`, embed it in the entry.

AI drafts the entry from what actually happened in the session; a human skims/edits before it's committed — light curation, not writing from scratch.

## Calibrating detail

The failure mode in practice isn't "logged something trivial" (the Trigger threshold above catches that) — it's **logging something real at the wrong weight**. A repo-gardening session (rebrand, tidy the README, reorganize a folder) genuinely shipped something, so it clears the skip threshold, but it's not a feature — it doesn't deserve a title plus five bullets walking through every file touched. Match the entry's weight to what a reader outside the session would actually care about, not to how much work it took or how many files changed:

- **A real feature, fix, or piece of content** (something a user or reader would notice): title, one or two sentences written for a reader, screenshot/video if something visual shipped. This is the only tier that gets an image.
- **Small but real stuff** (internal cleanup, rename, reorg, tidying, small fixes with no user-visible behavior change): one plain sentence, no title needed, no bullets, no screenshot. If several small things happened in one session, that's still one sentence combining them — not a bullet per thing.
- **Nothing worth a reader's attention:** skip it, per Trigger above.

Don't let the entry mirror the session's internal structure — the reader doesn't care that branding, the README, and a folder reorg were three separate steps; they care that the site got tidied up. Describe the outcome, not the implementation. If you're drafting bullets that name specific files, config keys, or "moved X into Y" — stop and ask whether that's release-note material or just commit-message detail that belongs in `git log`, not `changelog.md`.

**Before/after, from a real session:**

```markdown
<!-- Before: implementation-log style, five bullets naming files and internal moves -->
## 2026-08-16 — Repo gardening: Reason Commons branding, clean landing page, tidy explainers

A housekeeping session with no new content, but the site now looks like a project
rather than a workspace...

- **Rebranded to Reason Commons.** Site title and README header still said "Issue
  Trees & Logical Thinking Process"; both now match the naming decision recorded in
  `docs/brand-and-domain-naming.md`. Stale links to the old repo name were fixed
  across `config.json`, the dashboard manifest and the skill docs.
- **README is a landing page now.** ...
- **`explainers/` reorganised.** ...
- **Root docs lowercased** ...
- **Two working conventions recorded in `AGENTS.md`** ...
```

```markdown
<!-- After: one sentence, reader's-eye view of what changed -->
## 2026-08-16 — Repo gardening

Rebranded to Reason Commons, turned the README into a real landing page, and tidied
the explainers folder and docs — no new content, but the site now reads as a
finished project rather than a workspace.
```

## Publishing

Committing the entry to the project's own repo is the automatic, no-decision floor — it always happens, no destination choice required. Anything beyond that (a personal/org site, a weekly review, social media, a newsletter) is always a **manual promote**, never automatic — see `~/src/me/planning/initiatives/changelog-for-me/scqh.md` for the fuller reasoning.

## Not doing yet

- No image hosting (R2 or otherwise) — plain git until volume makes that painful.
- No automated weekly-roll-up script pulling from every project's `changelog.md` — do that by hand first.
- No auto-posting to social media — promotion is always a manual step.
