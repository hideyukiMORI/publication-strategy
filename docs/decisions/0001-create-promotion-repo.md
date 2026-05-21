# Decision 0001: Create Cross-Project publication-strategy Repository

Date: 2026-05-22

## Status

Accepted

## Context

Three OSS products (NeNe, NENE2, nene2-python) share a maintainer and field-trial methodology but serve different audiences. The immediate goal is **GitHub recognition**, not maximizing every social channel independently.

NeNe already has `docs/publication-strategy.md` as a public single-product case study. Cross-project priority, experiment metrics, and decision history do not belong inside one product repo without diluting that product's narrative.

## Decision

Create a **public** repository named `publication-strategy` at the same filesystem level as NeNe, NENE2, and nene2-python. Use it for:

- Portfolio positioning and weapon priority
- Channel playbook and experiment logs
- Decision records
- Cross-project TODO

Keep in each product repo:

- README and GitHub About metadata
- Product-specific article sources
- Framework ADRs and implementation Issues

## Alternatives Considered

| Option | Rejected because |
|---|---|
| Extend NeNe `publication-strategy.md` only | Becomes NeNe-centric; NENE2/Python strategy awkward |
| Issues-only, no repo | No durable decision/experiment log structure |
| Private repo | Loses case-study value; harder to link from public articles |
| Single mega-doc in profile gist | No Issue workflow, no version history for experiments |

## Consequences

- One more repository to maintain, but scope is documentation-only and small.
- Product repos stay focused; promotion learning accumulates visibly.
- Review portfolio weapon priority on a schedule (see positioning matrix review date).

## Review

2026-08-22 — Revisit primary weapon hypothesis after NeNe Qiita + metrics.
