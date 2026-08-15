# Changelog Convention

The canonical spec for how repos keep a changelog — text and visual, one file, one trigger. Meant to be pointed to from any repo's `AGENTS.md`/`CLAUDE.md`, not copied in full or auto-loaded every session — an AI only fetches it when a changelog task actually comes up.

## Add this to a repo's AGENTS.md

Copy-paste, one line, done:

```markdown
Changelog: read https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md and follow it at the end of a work session.
```

That's the raw file URL, not the GitHub web page — it returns plain markdown directly, no HTML around it, so any fetch tool (or a straight `curl`) gets the spec in one shot: `curl -s https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md`. Works the same from a local session, a cloud session, or Codex — no local checkout of any repo required, and no GitHub auth needed since this repo is public.

## Spec

[CONVENTION.md](CONVENTION.md)

## Why not published elsewhere

Considered Flowershow / a public website for this, but the actual consumer is an AI agent fetching one plain-text file, not a human browsing a site — the raw GitHub URL already does that, is already public, and needed zero extra setup. Revisit only if this doc needs to be human-browsable or search-discoverable as content in its own right, not as a pointer target.

## Source docs

Motivation and decisions: `~/src/me/planning/projects/2026-central-visual-changelog.md` and `~/src/me/planning/projects/2026-central-visual-changelog/scqh.md`, and the parent `~/src/me/planning/initiatives/changelog-for-me/scqh.md`.

## History

This repo started as a proposed central image archive (one repo per org, subfolder per project). That was reconsidered — it solved a repo-bloat problem that hadn't actually shown up yet, at the cost of a cross-repo hop for every entry. Visual entries were folded back into each project's own repo instead, and this repo was repurposed to hold the convention doc rather than the images themselves.
