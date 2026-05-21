# Agent / AI Guide

Entry point for AI agents working on cross-project publication strategy.

## Read First

- `README.md` — north star and scope split
- `docs/CONTRIBUTING.md` — collaboration policy
- `docs/workflow.md` — Issue-driven workflow
- `docs/development/commit-conventions.md` — commit message rules
- `docs/roadmap.md` — portfolio direction
- `docs/todo/current.md` — current work
- `docs/positioning-matrix.md` — three products as weapons
- `docs/channel-playbook.md` — channel rules
- `docs/decisions/` — why past choices were made

## Issue-Driven Workflow

Work from GitHub Issues, same pattern as NeNe and NENE2:

1. Create or reuse an Issue in **this repository** before editing strategy docs.
2. Branch from `main` as `type/issue-number-summary`. Do not commit directly to `main`.
3. Update `docs/todo/current.md` (and roadmap/milestones when direction changes).
4. Commit with Conventional Commits in **English**; include `(#issue)` in the subject when practical.
5. Push, open PR with `Closes #number`, merge, sync `main`.

Product asset changes (articles, README, code) use Issues in NeNe / NENE2 / nene2-python. Link them from Issues here when logging experiments.

If the user explicitly limits scope (investigation only, no commit, no PR), follow that instruction.

## Language Policy

**Write all repository text in English.**

This applies to:

- Every Markdown file in this repository (`README.md`, `AGENTS.md`, and all of `docs/`)
- GitHub Issue titles and bodies
- Pull request titles and bodies
- Commit message descriptions and bodies (Conventional Commit `type` and `scope` stay in English)

Exceptions:

- **Quoted titles or short excerpts** from outward article assets (for example a Japanese Zenn title) may appear in English experiment logs for traceability.
- **URLs and repo paths** stay as-is.

**Japanese body copy does not belong in this repository.** Japanese is allowed only in **outward article source files** stored in product repos (Zenn, Qiita, and similar channels). See `docs/decisions/0003-japanese-outward-article-assets-only.md`.

Do not add Japanese notes, article drafts, parallel `docs/ja/` trees, or mixed-language strategy docs unless a future decision record changes this policy.

Product repos (NeNe, NENE2, nene2-python) hold article assets and keep their own rules for code and maintainer workflow.

## Operating Rules

- This repo is **documentation and strategy only**. No product code.
- Product changes (README, articles, code) happen in NeNe / NENE2 / nene2-python; link from Issues here.
- Log experiments in `docs/experiments/` before and after channel work.
- Record non-obvious portfolio decisions in `docs/decisions/`.
- Goal: GitHub recognition for the portfolio. Do not optimize for vanity metrics without repo follow-through.

## Product Repos (weapons)

- NeNe: `/home/xi/docker/NeNe`
- NENE2: `/home/xi/docker/NENE2`
- nene2-python: `/home/xi/docker/nene2-python`
