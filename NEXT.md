---
updated: 2026-09-26
---

## Current checkpoint

The convention uses one file per entry in `changelog/`, with frontmatter,
live links, and screenshots where useful. Standalone entries require a new
feature or significant reader-facing change. Small changes may only support a
larger announcement that qualifies on its own; the old one-liner tier is removed.
The `AGENTS.md` snippet is now 110 words.

## Next

- Re-sync the revised [snippet](add-to-agents.md) into repos that already use it;
  see [README.md](README.md#updating-a-repo-that-already-has-it).
- When next working on `reasoncommons`'s changelog, check whether its old single
  `changelog.md` still needs migrating to the folder format.
- Re-check the roll-up skill at `~/src/me/planning/skills/changelog-rollup/SKILL.md`
  against frontmatter-based `promote` flags. Previous fixture tests used the old
  HTML-comment marker; a real weekly review and manual-promote trial remain untested.

## References

- [CONVENTION.md](CONVENTION.md): current per-entry rules.
- [PUBLISHING.md](PUBLISHING.md): weekly roll-up and manual promotion.
- [MOTIVATION.md](MOTIVATION.md): rationale.
- [v2 design](docs/plans/2026-08-23-changelog-v2-design.md): historical design;
  its small-work tier is superseded by the current convention.

Deferred until the manual workflow proves useful: external image hosting,
roll-up automation, social auto-posting, and remote fetching for roll-ups.
