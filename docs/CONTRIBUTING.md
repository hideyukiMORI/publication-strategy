# Contributing

This repository is built through small, Issue-driven changes. This document is the shared entry point for humans and AI agents.

## Required Reading

| Topic | Document |
| --- | --- |
| Workflow | `docs/workflow.md` |
| Commit messages | `docs/development/commit-conventions.md` |
| Agent guide | `AGENTS.md` |
| Portfolio direction | `docs/roadmap.md` |
| Current work | `docs/todo/current.md` |
| Positioning | `docs/positioning-matrix.md` |
| Channels | `docs/channel-playbook.md` |

## Collaboration Policy

- Start work from a GitHub Issue in **this repository**.
- Do not commit directly to `main`. Use a branch named like `type/issue-number-summary`.
- Use one branch and one PR per focused work unit.
- Keep `docs/roadmap.md`, `docs/milestones/`, and `docs/todo/current.md` updated when direction or active work changes.
- Explain intent, impact, verification, and remaining risk in PRs.
- Prefer documentation that helps the next developer or AI agent decide what to do without rereading chat history.

## Scope Split

| Work type | Where it happens |
| --- | --- |
| Cross-project strategy, experiments, metrics, decisions | This repo (Issue → PR here) |
| Product README, articles, code, framework docs | NeNe / NENE2 / nene2-python (Issue → PR there) |

When a promotion task spans both layers, open an Issue here for strategy/logging and link to the product Issue that carries the actual asset change.

## Secrets

Do not commit API tokens, private analytics exports with identifying data, or credentials. Metrics snapshots should use aggregate public-safe numbers.

## Documentation Language

All Markdown in this repository is written in **English**. See `AGENTS.md`. Issue and PR bodies may use Japanese for maintainer workflow.
