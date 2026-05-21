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

- `docs/positioning-matrix.md` — how the three weapons differ and which to push when
- `docs/channel-playbook.md` — Zenn / Qiita / DEV / Reddit / HN rules
- `docs/todo/current.md` — cross-project active work
- `docs/decisions/` — decision records (context, decision, alternatives)
- `docs/experiments/` — channel experiments with hypotheses and metrics

## Related Product Docs

- NeNe: `docs/publication-strategy.md` in [NeNe](https://github.com/hideyukiMORI/NeNe) (single-product case study)
- NeNe Zenn article source: `docs/articles/zenn-renovating-legacy-php-framework.md`

## Documentation Language

All documentation in this repository is written in **English**. See `AGENTS.md` for the full language policy.

Outward-facing articles (Zenn, Qiita, and so on) live in product repos and may use Japanese or English per channel; this repo only logs strategy and experiments in English.

## Workflow

- GitHub Issues in this repo track cross-project promotion tasks.
- Product code or product README changes stay in product repos; link them from Issues here.
- Record decisions and experiment results before changing portfolio priority.
