# Changelog v2 design

Prompted by reviewing real entries from the Wilber Wiki changelog and finding four gaps: no way to signal a bigger/richer entry, screenshots not reliably taken for visual work, no links from an entry back to the live feature it describes, and a single `changelog.md` that won't scale gracefully as entries accumulate. Worked through via `superpowers:brainstorming`.

## 1. Three-tier length calibration

CONVENTION.md's "Calibrating detail" currently has two tiers (full-feature: title + 1-2 sentences + image; small stuff: one plain sentence) plus skip. Add a third, higher tier for entries that genuinely warrant more — multi-paragraph, bullets, more detail — triggered by AI judgment on the scope of what happened, same as the existing skip/small/full judgment call. No new mechanism, just one more rung on the ladder that already exists.

## 2. Dev-only exemplars file

Create `EXEMPLARS.md` at repo root (linear.app and other reference changelogs, with notes on what's good about each). This is for *our* use shaping the spec — not linked from CONVENTION.md or add-to-agents.md, not read by any project-repo agent drafting an entry. Keeps the per-entry spec lean for its actual audience.

## 3. Screenshot judgment, strengthened

Real miss: an "annotatable reading layer" prototype — clearly visual — shipped with no screenshot. Not a mandatory-screenshot rule (still judgment), but the drafting flow gets an explicit check: did this session touch UI/something visual? Consider a screenshot before deciding the entry doesn't need one, rather than screenshots only happening to come up implicitly.

## 4. Link to the live feature

Entries currently never link to what they describe. Fix: link the relevant text inline, early in the entry, or in a trailing "See:" line — AI's judgment on which reads better, especially for entries covering multiple things (a bigger entry might touch a feature and a couple of fixes, each with its own link). Hard rule: **never make the title itself a link** — the title is reserved for a future listing page to link *to* this entry, and a title that's already a link elsewhere would conflict with that.

## 5. Folder-of-entries instead of single file

Single `changelog.md`, prepended forever, breaks down at scale (unbounded file growth, noisy diffs, no stable per-entry link target, doesn't map to how Flowershow generates list pages from a folder). Replace with one file per entry:

```
changelog/
  2026-08-23-annotatable-reading-layer.md
  2026-08-23-people-index-23-thinkers.md
  images/
    2026-08-23-annotatable-reading-layer.png
```

Filename is `YYYY-MM-DD-slug.md` — date included even though it's also in frontmatter, because filename sort order gives free chronological skimming (`ls`, GitHub's file browser) without opening files, and same-day entries (already happened in the real example — three in one day) need the slug to disambiguate regardless.

Frontmatter:

```yaml
---
date: 2026-08-23
title: Annotatable reading layer: Phase 1 prototype
promote: false
---
```

- `date` — frontmatter copy is what Flowershow/any generator reads for sorting; filename copy is for humans/git.
- `title` — plain text, never a link (see point 4).
- `promote` — boolean, replaces the old trailing `<!-- promote -->` HTML-comment marker from PUBLISHING.md's v1 design. A per-file structure makes a frontmatter flag the natural equivalent of what was a mid-file comment marker. Kept (not dropped) after reconsidering whether it still earns its keep now that the weekly roll-up has to open every file anyway: the value isn't avoiding reads, it's capturing the drafting-time AI's judgment on promotion-worthiness while it still has full session context — a terse two-sentence entry read cold a week later doesn't carry that.
- No `tags`/`links` field — inline links in the body cover it; a structured field would be speculative ahead of any real need.

Migration of existing single-file changelogs (e.g. reasoncommons) into this shape is out of scope for this design — a separate, later step once a project's file actually needs it.

## What this changes downstream

- **CONVENTION.md**: "File" section (folder + frontmatter, not single-file `## date — title` headers), "Calibrating detail" (third tier), a link-to-the-feature subsection, screenshot-judgment note.
- **add-to-agents.md**: short-form snippet updated to match (folder + frontmatter shape, still points to CONVENTION.md for the full spec).
- **PUBLISHING.md**: roll-up discovery step reads every file in a project's `changelog/` folder instead of parsing one file; promote-scan checks `promote: true` frontmatter instead of grepping for the HTML comment.
- **README.md**: minor — file listing already links to CONVENTION.md/PUBLISHING.md; add EXEMPLARS.md is *not* listed there as part of the spec (dev-only), maybe a one-line note under a "for maintainers of this repo" aside if one exists, otherwise omit.

## Not doing yet

- Migrating existing project changelogs to the folder shape.
- Any structured tags/links frontmatter field.
- Any change to the weekly roll-up's cadence or the newsletter/social promote mechanics beyond the storage-format update above.
