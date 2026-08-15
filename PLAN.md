# Plan

Concrete build plan from the Hypothesis in `~/src/me/planning/projects/2026-central-visual-changelog/scqh.md`. Quick-and-dirty v1, meant to be trialed and revised.

## Structure

```
<project-slug>/
  CHANGELOG.md          # running log, newest entry first
  images/
    2026-08-15-first-readme.png
```

One folder per project, matching its slug in `~/src/me/planning/projects/` or the project's own repo name. `CHANGELOG.md` entries look like:

```markdown
## 2026-08-15 — Repo scaffolded

![First README](images/2026-08-15-first-readme.png)

Scaffolded the wilber-wiki repo with a stub README pointing back to the planning docs.
```

## Workflow

1. At session-checkpoint time (end of a work session on a Life Itself project), if something visual shipped this session, grab a screenshot (or short video — same pattern, just a `.mp4`/`.mov` in `images/`).
2. Add it to `<project-slug>/images/`, prepend a dated entry to `<project-slug>/CHANGELOG.md`, commit, push. No separate repo to stand up per project — just a new subfolder here the first time a project gets an entry.
3. This is the always-on floor: committing here needs no publishing decision. Anything going further (Life Itself site, social media, the personal/Life Itself weekly review) is always a manual promote — see the parent SCQH for that rule.

## Not doing yet

Deliberately out of scope for v1 — revisit only once the basic pattern is actually in use:

- No image hosting (R2 or otherwise) — plain git commits until volume makes that painful.
- No automated weekly roll-up script pulling from every project's `CHANGELOG.md` — do that by hand first, automate once the manual version proves useful.
- No personal (non-Life-Itself) equivalent repo — only stand one up once there's real personal-project volume to justify it.
- No auto-posting to social media — promotion is always a manual step.
