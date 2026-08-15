# Changelog Convention

The canonical spec for how repos keep a changelog — text and visual, one file, one trigger. Meant to be pointed to from any repo's `AGENTS.md`/`CLAUDE.md`, not copied in full or auto-loaded every session — an AI only fetches it when a changelog task actually comes up.

## Bootstrap prompt — paste this into an AI session in the target repo

This is the thing to actually copy-paste — into Claude Code, Codex, whatever — and let it do the file edit, rather than hand-editing AGENTS.md yourself:

```
Add a changelog convention to this repo. Fetch
https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md
and read it, then add a "## Changelog" section to this repo's AGENTS.md
(create AGENTS.md if it doesn't exist) that: states this repo keeps a
CHANGELOG.md with dated entries, newest first; says entries get drafted at
the end of a work session, but only when something worth recording actually
shipped — skip trivial sessions; notes screenshots go in changelog/images/
and get embedded inline; and links to the CONVENTION.md URL above for the
full format rather than repeating it. Keep the section to a handful of
lines — the URL is the source of truth.
```

If you'd rather hand-edit AGENTS.md yourself, the section it produces looks roughly like this:

```markdown
## Changelog

This repo keeps a `CHANGELOG.md` (dated entries, newest first; screenshots
in `changelog/images/`, embedded inline when something visual shipped). At
the end of a work session where something worth recording actually shipped
— skip trivial sessions — draft a dated entry. Full format:
https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md
```

Either way it's the raw file URL, not the GitHub web page — plain markdown in one fetch, no HTML wrapper, works the same from a local session, a cloud session, or Codex, no checkout or auth needed since this repo is public.

## Spec

[CONVENTION.md](CONVENTION.md)

## Why not published elsewhere

Considered Flowershow / a public website for this, but the actual consumer is an AI agent fetching one plain-text file, not a human browsing a site — the raw GitHub URL already does that, is already public, and needed zero extra setup. Revisit only if this doc needs to be human-browsable or search-discoverable as content in its own right, not as a pointer target.

## Source docs

Motivation and decisions: `~/src/me/planning/projects/2026-central-visual-changelog.md` and `~/src/me/planning/projects/2026-central-visual-changelog/scqh.md`, and the parent `~/src/me/planning/initiatives/changelog-for-me/scqh.md`.

## History

This repo started as a proposed central image archive (one repo per org, subfolder per project). That was reconsidered — it solved a repo-bloat problem that hadn't actually shown up yet, at the cost of a cross-repo hop for every entry. Visual entries were folded back into each project's own repo instead, and this repo was repurposed to hold the convention doc rather than the images themselves.
