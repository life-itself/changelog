# Changelog Convention

Copy this into your coding agent:

```
Go to https://raw.githubusercontent.com/life-itself/changelog/main/add-to-agents.md and add its content to this repo's AGENTS.md (create AGENTS.md if it doesn't exist).
```

That's it — the whole file at that URL is exactly what gets added, nothing to find or extract inside a bigger doc, nothing to paraphrase. It's the raw file URL, not the GitHub web page, so it's plain markdown in one fetch: works the same from a local session, a cloud session, or Codex, no checkout or auth needed since this repo is public.

## Files

- **[add-to-agents.md](add-to-agents.md)** — the short snippet, verbatim content for a repo's `AGENTS.md`. States what a changelog entry is and when to write one (skip trivial sessions), and only points to `CONVENTION.md` for the actual first entry or when the format's unclear — so a session never has to fetch the full spec just to decide whether to bother.
- **[CONVENTION.md](CONVENTION.md)** — the full per-entry spec: file format, image handling, the skip/weight judgment calls. This is what a project-repo agent reads. Deliberately doesn't cover what happens to entries afterward.
- **[PUBLISHING.md](PUBLISHING.md)** — the separate, much-less-frequent concern of aggregating entries across projects: weekly roll-up and manual promote (social/newsletter/site). Read by the planning repo's `changelog-rollup` skill, not by a project-repo session — kept out of `CONVENTION.md` on purpose so drafting one entry never pulls this in.
- **[MOTIVATION.md](MOTIVATION.md)** — the full situation/complication/question/hypothesis behind why this repo and this spec exist, self-contained (no need to check out the planning repo to follow the reasoning).
- **[NEXT.md](NEXT.md)** — current checkpoint and backlog; links the open GitHub issues.

## Why not published elsewhere

Considered Flowershow / a public website for this, but the actual consumer is an AI agent fetching a plain-text file, not a human browsing a site — the raw GitHub URL already does that, is already public, and needed zero extra setup. Revisit only if this doc needs to be human-browsable or search-discoverable as content in its own right, not as a pointer target.

## Source docs

The planning repo (`~/src/me/planning`) keeps its own copy of the motivation docs too — `projects/2026-central-visual-changelog.md` / `scqh.md`, and `initiatives/changelog-for-me/scqh.md`. `MOTIVATION.md` here is the same content, consolidated so this repo doesn't depend on that one being checked out.

## History

This repo started as a proposed central image archive (one repo per org, subfolder per project). That was reconsidered — it solved a repo-bloat problem that hadn't actually shown up yet, at the cost of a cross-repo hop for every entry. Visual entries were folded back into each project's own repo instead, and this repo was repurposed to hold the convention doc rather than the images themselves.
