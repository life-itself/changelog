---
updated: 2026-08-16
---

## Current checkpoint

- **Project:** Changelog Convention
- **State:** v1 design complete (per-entry convention + weekly roll-up + manual promote), split into separate files by audience/frequency; all three original issues resolved
- **Next:** Live with it. Watch the next real entries for whether the calibration fix holds, and whether the weekly roll-up/promote design survives contact with an actual weekly review (nothing there has been run yet — it's designed, not tried).
- **Context:** [MOTIVATION.md](MOTIVATION.md) for the full situation/complication/question/hypothesis; [CONVENTION.md](CONVENTION.md) (per-entry spec, what a project-repo agent reads) and [PUBLISHING.md](PUBLISHING.md) (roll-up + promote, what the planning-repo weekly review reads) are the current specs; [add-to-agents.md](add-to-agents.md) is the short snippet copied into project `AGENTS.md` files.
- **Trial finding (2026-08-16):** the real entries produced in `reasoncommons` were too verbose for what they reported — a repo-gardening session (rebrand, README tidy, folder reorg) got a full title plus five bullets naming individual files, when the actual reader-facing news was one sentence. Added a "Calibrating detail" section to `CONVENTION.md` (skip / one-liner / full-feature tiers, before/after example), folded a shorter version into `add-to-agents.md`, retrofitted the reasoncommons AGENTS.md copy and condensed its entry as the worked example.
- **Design added, then split out (2026-08-16):** weekly roll-up and manual-promote design (answering issues #2/#3) first landed inside `CONVENTION.md`, then got pulled into its own `PUBLISHING.md` — different audience (planning-repo weekly review, not a project-repo session drafting one entry) and different frequency (weekly, not per-session), so it shouldn't bloat the file every project-repo agent reads. The actual roll-up/promote steps now live as a skill, `~/src/me/planning/skills/changelog-rollup/SKILL.md`, which points back to `PUBLISHING.md` as the canonical spec — same pattern as `add-to-agents.md` → `CONVENTION.md`. Untested — first real weekly review will tell if this holds.

## Backlog

- Nothing open right now — issues #1, #2, #3 closed 2026-08-16 once the trial + design work landed. Next backlog items will come from actually running the weekly roll-up and promote flow once, the same way the per-entry convention only got fixed after a real run surfaced the verbosity problem.

Deliberately deferred (see CONVENTION.md "Not doing yet" — don't file issues for these until the manual version proves the pattern): R2/image hosting, GitHub Action automation for the roll-up, auto-posting to social media, remote-fetch (non-local-checkout) reading for the roll-up.
