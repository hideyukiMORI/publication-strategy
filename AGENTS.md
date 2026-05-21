# Agent / AI Guide

Entry point for AI agents working on cross-project publication strategy.

## Read First

- `README.md` — north star and scope split
- `docs/positioning-matrix.md` — three products as weapons
- `docs/channel-playbook.md` — channel rules
- `docs/todo/current.md` — active cross-project work
- `docs/decisions/` — why past choices were made

## Language Policy

**Write all repository documentation in English.**

This applies to every Markdown file in this repository, including:

- `README.md` and `AGENTS.md`
- `docs/todo/`, `docs/decisions/`, `docs/experiments/`, and any future docs under `docs/`

Exceptions:

- **Quoted titles** of published or draft outward assets (for example a Japanese Zenn article title) may stay in the original language when the experiment log references them.
- **URLs and repo paths** stay as-is.

Do not add Japanese-local notes, parallel `docs/ja/` trees, or mixed-language versions of the same document unless a future decision record explicitly changes this policy.

GitHub Issue and PR bodies may use Japanese for maintainer workflow; the **durable docs in this repo stay English**.

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
