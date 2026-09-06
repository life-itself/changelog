# Changelog Convention

How any repo keeps a changelog — text and visual, same folder, same trigger. Quick-and-dirty v1: meant to be trialed and revised, not final.

The short version that goes into a repo's `AGENTS.md` lives in its own file, [add-to-agents.md](add-to-agents.md) — copy its whole content in, don't paraphrase this longer doc. This file is the full spec that snippet points to once an entry's actually being drafted.

**Scope:** this file is only about writing the per-project changelog entry itself — the thing every project-repo agent needs. What happens to entries *after* that (rolling them up into a weekly review, promoting one to social/newsletter) is a separate, much-less-frequent concern with its own audience (whoever's doing the weekly review, not a project-repo session drafting one entry) — see [PUBLISHING.md](PUBLISHING.md). Deliberately not folded in here: a project-repo agent drafting one entry has no reason to load roll-up/promote instructions into context.

## File

A `changelog/` folder at the repo root, one file per entry — not a single growing file, not version-numbered releases (most of these repos ship continuously rather than cutting formal releases). Filename: `YYYY-MM-DD-slug.md`. The date is in the filename even though it's also in frontmatter — filename sort order gives free chronological skimming (`ls`, GitHub's file browser) with no need to open files, and same-day entries (this happens — three in one day isn't rare) need the slug to disambiguate regardless.

```markdown
---
date: 2026-08-15
title: Short title
promote: false
---

One or two sentences, written for a reader, not a raw commit-message dump.
See it live: [the feature](https://example.com/the-feature).

Optional image, if something visual shipped this session:

![Caption describing the moment](images/2026-08-15-short-title.png)
```

Frontmatter fields:
- `date` — the frontmatter copy is what Flowershow (or any generator building a list/index page) actually reads for sorting; the filename copy is for humans and git.
- `title` — plain text, **never a link**. The title is reserved for a future listing page to link *to* this entry — don't spend it on a link to something else.
- `promote` — boolean, `false` by default. See [PUBLISHING.md](PUBLISHING.md) — set at drafting time when the entry looks like a strong candidate for social/newsletter, so that judgment (made with full session context) isn't lost by the time of the weekly review.

If a repo does versioned releases, note the version in the body/title as needed — the folder/frontmatter mechanics don't change.

## Images

`changelog/images/YYYY-MM-DD-slug.png` (or `.mp4`/`.mov` for a short video) inside the project's **own** repo — not a separate changelog repo. Plain git commit; no external hosting for v1. Referenced inline from the entry file via a relative path, as above.

No mandatory before/after pairing — just grab whatever's compelling in the moment (usually the "after"/current state). If a reader wants the comparison, the previous entry's image is one file over in the same folder.

**Check for it, don't skip past it.** If the session touched UI or anything visual, that's a deliberate point to consider a screenshot before deciding the entry doesn't need one — not something that only happens to come up. Still judgment, not mandatory: a prototype or visible UI change is a strong candidate; a backend-only change isn't.

## Link to the live feature

An entry that describes something a reader can actually go look at should link to it — a page, a specific feature, wherever the change is visible. This is easy to skip and shouldn't be: "the concept wiki grows to seventeen pages" without a link to the concept wiki gives the reader nothing to do with that sentence.

- Link inline, early in the entry text, or in a trailing `See: [...]` line — whichever reads better for that entry. Judgment call, not a fixed placement.
- An entry covering multiple things (more likely at the bigger tier below — a feature plus a couple of fixes) can have more than one link, one per thing, rather than forcing everything into a single link.
- Don't turn the title into a link (see Frontmatter fields above) and don't cram so many links into the lead sentence that it reads like a reference list — spread them across the entry instead.
- No link if there's genuinely nothing public to point to yet (e.g. a feature not linked from navigation) — say so rather than linking to something misleading.

## Trigger

At session-checkpoint time (end of a work session / handoff point) — the same moment a `NEXT.md` update happens in repos that use one.

**Skip the entry if the session was trivial** — a typo fix, a failed experiment, pure research/reading, config fiddling with no visible outcome. Planning, research, or design alone do not qualify unless they are themselves a significant public deliverable. Drafting ahead of a ship is fine. Write one only when something a reader would actually care about shipped: a feature, a fix, a meaningful piece of content, a visible change. When genuinely unsure, err toward skipping rather than logging noise — a changelog that's mostly filler stops getting read.

1. Did something changelog-worthy ship this session? (See threshold above — not every commit, not every session.)
2. If yes: draft a new file, `changelog/YYYY-MM-DD-slug.md`.
3. If something visual shipped: grab a screenshot/short video at the same moment, commit it to `changelog/images/`, embed it in the entry.

AI drafts the entry from what actually happened in the session; a human skims/edits before it's committed — light curation, not writing from scratch.

## Calibrating detail

The failure mode in practice isn't "logged something trivial" (the Trigger threshold above catches that) — it's **logging something real at the wrong weight**. A repo-gardening session (rebrand, tidy the README, reorganize a folder) genuinely shipped something, so it clears the skip threshold, but it's not a feature — it doesn't deserve a title plus five bullets walking through every file touched. Match the entry's weight to what a reader outside the session would actually care about, not to how much work it took or how many files changed:

- **Something bigger** (a substantial feature, a milestone, a piece of work with real depth — the kind of thing linear.app's changelog gives a full writeup): multiple paragraphs and/or bullets, more than one link if more than one thing is covered, image(s) where relevant. Judgment call on when a session clears this bar — most sessions won't. Don't pad an ordinary entry up to this tier for the sake of variety; reserve it for entries that genuinely have this much to say.
- **A real feature, fix, or piece of content** (something a user or reader would notice): title, one or two sentences written for a reader, screenshot/video if something visual shipped, link to the live feature (see above). This is the default tier for anything that clears the skip threshold and isn't small stuff.
- **Small but real stuff** (internal cleanup, rename, reorg, tidying, small fixes with no user-visible behavior change): one plain sentence, no title needed, no bullets, no screenshot. If several small things happened in one session, that's still one sentence combining them — not a bullet per thing.
- **Nothing worth a reader's attention:** skip it, per Trigger above.

Don't let the entry mirror the session's internal structure — the reader doesn't care that branding, the README, and a folder reorg were three separate steps; they care that the site got tidied up. Describe the outcome, not the implementation. If you're drafting bullets that name specific files, config keys, or "moved X into Y" — stop and ask whether that's release-note material or just commit-message detail that belongs in `git log`, not `changelog.md`.

**Before/after, from a real session:**

```markdown
<!-- Before: implementation-log style, five bullets naming files and internal moves -->
<!-- changelog/2026-08-16-repo-gardening.md -->
---
date: 2026-08-16
title: Repo gardening — Reason Commons branding, clean landing page, tidy explainers
promote: false
---

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
<!-- changelog/2026-08-16-repo-gardening.md -->
---
date: 2026-08-16
title: Repo gardening
promote: false
---

Rebranded to Reason Commons, turned the README into a real landing page, and tidied
the explainers folder and docs — no new content, but the site now reads as a
finished project rather than a workspace.
```

## Publishing

Committing the entry to the project's own repo is the automatic, no-decision floor — it always happens, no destination choice required. Anything beyond that (a personal/org site, a weekly review, social media, a newsletter) is always a **manual promote**, never automatic, and lives in [PUBLISHING.md](PUBLISHING.md), not here.

## Not doing yet

- No image hosting (R2 or otherwise) — plain git until volume makes that painful.
- No roll-up/promote automation of any kind at the per-entry level — see `PUBLISHING.md` for what v1 of that looks like.
