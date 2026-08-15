# Changelog Convention

The canonical spec for how repos keep a changelog — text and visual, one file, one trigger. Meant to be pointed to from any repo's `AGENTS.md`/`CLAUDE.md`, not copied in full or auto-loaded every session — an AI only fetches it when a changelog task actually comes up.

## Bootstrap prompt — paste this into an AI session in the target repo

```
Read https://raw.githubusercontent.com/life-itself/changelog/main/CONVENTION.md
and copy the block from its "Copy this into AGENTS.md" section into this
repo's AGENTS.md verbatim (create AGENTS.md if it doesn't exist). Don't
paraphrase or summarise it — copy it exactly as written.
```

No composing required — the agent fetches one file, finds one clearly marked block, pastes it in unchanged. That's deliberate: every repo ends up with byte-identical instructions instead of each session's own interpretation, and installing the pointer never requires actually reading/understanding the rest of the spec — only the block itself, which is short by design.

Prefer to do it yourself by hand? Open [CONVENTION.md](CONVENTION.md#copy-this-into-agentsmd) and copy the same block — there's only the one copy of it, in that file, so nothing here duplicates or can drift from it.

It's the raw file URL, not the GitHub web page — plain markdown in one fetch, no HTML wrapper, works the same from a local session, a cloud session, or Codex, no checkout or auth needed since this repo is public.

## Spec

[CONVENTION.md](CONVENTION.md)

## Why not published elsewhere

Considered Flowershow / a public website for this, but the actual consumer is an AI agent fetching one plain-text file, not a human browsing a site — the raw GitHub URL already does that, is already public, and needed zero extra setup. Revisit only if this doc needs to be human-browsable or search-discoverable as content in its own right, not as a pointer target.

## Source docs

Motivation and decisions: `~/src/me/planning/projects/2026-central-visual-changelog.md` and `~/src/me/planning/projects/2026-central-visual-changelog/scqh.md`, and the parent `~/src/me/planning/initiatives/changelog-for-me/scqh.md`.

## History

This repo started as a proposed central image archive (one repo per org, subfolder per project). That was reconsidered — it solved a repo-bloat problem that hadn't actually shown up yet, at the cost of a cross-repo hop for every entry. Visual entries were folded back into each project's own repo instead, and this repo was repurposed to hold the convention doc rather than the images themselves.
