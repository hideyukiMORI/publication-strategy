# publication-strategy

Cross-project publication and GitHub recognition strategy for the OSS portfolio maintained by [hideyukiMORI](https://github.com/hideyukiMORI).

## North Star

**Goal:** Increase GitHub recognition (stars, traffic, discoverability, inbound interest) for the portfolio.

**Weapons (products):**

| Repository | Role |
|---|---|
| [NeNe](https://github.com/hideyukiMORI/NeNe) | Renovated legacy-style PHP framework — story-driven entry |
| [NENE2](https://github.com/hideyukiMORI/NENE2) | Modern PHP 8.4 API-first framework — technical entry |
| [nene2-python](https://github.com/hideyukiMORI/nene2-python) | Python reference implementation of NENE2 design philosophy |

Product-specific publication notes stay in each repository. This repository holds **cross-project strategy, experiments, metrics, and decision history**.

## What Lives Here vs Product Repos

| Here | Product repos (NeNe / NENE2 / nene2-python) |
|---|---|
| Portfolio positioning and priority | README, About, Releases |
| Channel strategy and experiment logs | Article drafts tied to one product |
| Decision log (why we chose X over Y) | ADRs for framework architecture |
| Weekly metrics snapshots | Implementation Issues and PRs |

## Start Here

- `docs/CONTRIBUTING.md` — collaboration policy
- `docs/workflow.md` — Issue-driven workflow
- `docs/development/commit-conventions.md` — commit message rules
- `docs/roadmap.md` — portfolio direction
- `docs/todo/current.md` — cross-project active work
- `docs/positioning-matrix.md` — how the three weapons differ and which to push when
- `docs/channel-playbook.md` — Zenn / Qiita / DEV / Reddit / HN rules
- `docs/decisions/` — decision records (context, decision, alternatives)
- `docs/experiments/` — channel experiments with hypotheses and metrics
- `AGENTS.md` — AI agent entry point

## Related Product Docs

- NeNe: `docs/publication-strategy.md` in [NeNe](https://github.com/hideyukiMORI/NeNe) (single-product case study)
- NeNe Zenn article source: `docs/articles/zenn-renovating-legacy-php-framework.md`

## Language Policy

All text in this repository is written in **English**: Markdown docs, GitHub Issues, pull requests, and commit messages. See `AGENTS.md` and `docs/decisions/0002-english-collaboration-language.md`.

Outward-facing articles (Zenn, Qiita, and so on) live in product repos and may use Japanese or English per channel; this repo only logs strategy and experiments in English.

## Workflow

Issue-driven, aligned with NeNe and NENE2. See `docs/workflow.md`.

- Create or reuse a GitHub Issue before changing strategy docs.
- Branch as `type/issue-number-summary`; do not commit directly to `main`.
- Product code, README, and article drafts stay in product repos; link them from Issues here.
- Record decisions and experiment results before changing portfolio priority.
