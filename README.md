# Changelog Convention

The canonical spec for how repos keep a changelog — text and visual — meant to be pointed to from any repo's `AGENTS.md`/`CLAUDE.md`, not copied in or auto-loaded every session.

**Spec:** [CONVENTION.md](CONVENTION.md)

**Pointer line to add in a repo's `AGENTS.md`:**

```markdown
## Changelog

At the end of a work session, draft a CHANGELOG.md entry (and grab a screenshot if something visual shipped) — see https://github.com/life-itself/changelog/blob/main/CONVENTION.md for the format.
```

Public, so any agent — including one in an unrelated public repo, or a credential-less cloud session — can fetch the spec by URL without needing local access to `~/src/me/planning`.

Source docs (motivation, decisions): `~/src/me/planning/projects/2026-central-visual-changelog.md` and `~/src/me/planning/projects/2026-central-visual-changelog/scqh.md`, and the parent `~/src/me/planning/initiatives/changelog-for-me/scqh.md`.

History: this repo started as a proposed central image archive (one repo per org, subfolder per project). That was reconsidered — it solved a repo-bloat problem that hadn't actually shown up yet, at the cost of a cross-repo hop for every entry. Visual entries were folded back into each project's own repo instead, and this repo was repurposed to hold the convention doc rather than the images themselves.
