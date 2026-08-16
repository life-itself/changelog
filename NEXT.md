---
updated: 2026-08-16
---

## Current checkpoint

- **Project:** Changelog Convention
- **State:** v1 design complete (per-entry convention + weekly roll-up + manual promote), split into separate files by audience/frequency; all three original issues resolved
- **Next:** Live with it for real. The per-entry convention still only has one real-world data point (`reasoncommons`); the roll-up/promote skill has been fixture-tested but never run against a real weekly review — that's the next actual test.
- **Context:** [MOTIVATION.md](MOTIVATION.md) for the full situation/complication/question/hypothesis; [CONVENTION.md](CONVENTION.md) (per-entry spec, what a project-repo agent reads) and [PUBLISHING.md](PUBLISHING.md) (roll-up + promote, what the planning-repo weekly review reads) are the current specs; [add-to-agents.md](add-to-agents.md) is the short snippet copied into project `AGENTS.md` files.
- **Trial finding (2026-08-16):** the real entries produced in `reasoncommons` were too verbose for what they reported — a repo-gardening session (rebrand, README tidy, folder reorg) got a full title plus five bullets naming individual files, when the actual reader-facing news was one sentence. Added a "Calibrating detail" section to `CONVENTION.md` (skip / one-liner / full-feature tiers, before/after example), folded a shorter version into `add-to-agents.md`, retrofitted the reasoncommons AGENTS.md copy and condensed its entry as the worked example.
- **Design added, then split out (2026-08-16):** weekly roll-up and manual-promote design (answering issues #2/#3) first landed inside `CONVENTION.md`, then got pulled into its own `PUBLISHING.md` — different audience (planning-repo weekly review, not a project-repo session drafting one entry) and different frequency (weekly, not per-session), so it shouldn't bloat the file every project-repo agent reads. The actual roll-up/promote steps now live as a skill, `~/src/me/planning/skills/changelog-rollup/SKILL.md`, which points back to `PUBLISHING.md` as the canonical spec — same pattern as `add-to-agents.md` → `CONVENTION.md`. Symlinked into `~/src/me/planning/.claude/skills/` and committed there.
- **Fixture-tested (2026-08-16):** ran `changelog-rollup`'s SKILL.md against a mock fixture (fake `projects/*.md`, fake project changelogs, one project with no local checkout, one entry flagged `<!-- promote -->`) via two fresh test-agent passes, since a skill that's never been exercised is just a claim. First pass found five real gaps (no week-date derivation rule, cross-repo image references via relative path that don't resolve, no "condense to weight" spec, no promote-caption spec, unclear append-vs-create behavior) — fixed all five. Second pass, specifically exercising the append path, found two more (ambiguity over whether a promoted entry gets both a list bullet and a sub-heading, no stated location for the skip-note) — fixed those too. Still not run against a real weekly review with real project repos.

## Backlog

- Nothing open right now — issues #1, #2, #3 closed 2026-08-16 once the trial + design work landed. Next backlog item is running the weekly roll-up for real (not just against the fixture) during an actual weekly review, and separately trying the manual-promote flow on a real flagged entry.

Deliberately deferred (see CONVENTION.md "Not doing yet" — don't file issues for these until the manual version proves the pattern): R2/image hosting, GitHub Action automation for the roll-up, auto-posting to social media, remote-fetch (non-local-checkout) reading for the roll-up.
