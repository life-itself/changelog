---
updated: 2026-08-16
---

## Current checkpoint

- **Project:** Changelog Convention
- **State:** trialed, one revision made
- **Next:** Watch the next few real entries (in `reasoncommons` or elsewhere) to see if the calibration fix below actually holds, or if the spec needs another pass.
- **Context:** [MOTIVATION.md](MOTIVATION.md) for the full situation/complication/question/hypothesis; [CONVENTION.md](CONVENTION.md) and [add-to-agents.md](add-to-agents.md) are the current spec. Bootstrap confirmed working 2026-08-16: `life-itself/reasoncommons` AGENTS.md carries the snippet verbatim (commit `ea7bc2e`).
- **Trial finding (2026-08-16):** the real entries produced in `reasoncommons` were too verbose for what they reported — a repo-gardening session (rebrand, README tidy, folder reorg) got a full title plus five bullets naming individual files, when the actual reader-facing news was one sentence. The spec had a skip/don't-skip threshold but no guidance on *weight* once something clears that bar. Added a "Calibrating detail" section to `CONVENTION.md` (three tiers: skip / one-liner / full feature entry, with a before/after example) and folded a shorter version into `add-to-agents.md`. Retrofitted the reasoncommons AGENTS.md copy and condensed its 2026-08-16 changelog entry as the worked example.
- **Issue:** [#1 Trial the convention end-to-end on a real repo](https://github.com/life-itself/changelog/issues/1) — entries now exist; worth a comment/close, left for a human since it's a shared GitHub issue.
- **Updated:** 2026-08-16

## Backlog

Design tasks, not build tasks yet — per CONVENTION.md's "not doing yet" list, don't build automation before the manual version has actually been tried:

- [#2 Design the weekly aggregation / roll-up mechanism](https://github.com/life-itself/changelog/issues/2) — still an open gap: no way yet to roll per-project `changelog.md` entries up into a personal/Life Itself weekly review or newsletter.
- [#3 Design the manual-promote workflow](https://github.com/life-itself/changelog/issues/3) — "promotion is always manual" is a stated rule with no actual workflow behind it yet.

Deliberately deferred beyond that (see CONVENTION.md "Not doing yet" — don't file issues for these until the above prove the pattern first): R2/image hosting, GitHub Action automation for the roll-up, auto-posting to social media.
