# Decision 0002: English for All Collaboration Text

Date: 2026-05-22

## Status

Accepted

## Context

Decision 0001 and Issue #1 established English for durable Markdown documentation in this repository. Issue and PR bodies, plus commit descriptions, were still allowed in Japanese to mirror NeNe and NENE2 maintainer workflow.

The maintainer decided that **this repository** should use English for all collaboration text going forward: docs, Issues, PRs, and commit messages. Reasons:

- The repo is public and portfolio-facing.
- English keeps one language for humans and AI agents reading GitHub history.
- Product repos may keep their own language rules for code and articles.

## Decision

Write the following in **English**:

- All Markdown under this repository
- GitHub Issue titles and bodies
- Pull request titles and bodies
- Commit message descriptions and bodies (Conventional Commit `type` and `scope` remain English as before)

## Exceptions

- **Quoted titles or short excerpts** of outward article assets may stay in the original language inside English experiment logs. Full Japanese article body copy does not belong in this repo. See decision 0003.
- **URLs, repo paths, and product-repo Issue references** stay as-is.
- **Product repositories** (NeNe, NENE2, nene2-python) keep their own language policies; this decision applies only to `publication-strategy`.

## Alternatives Considered

| Option | Rejected because |
|---|---|
| Docs English only, Issues/PRs/commits Japanese | Split language makes public GitHub history harder to read |
| Match NENE2 commit convention (Japanese descriptions) | This repo is English-first by design |

## Consequences

- New Issues and PRs in this repo should be opened in English from Issue #5 onward.
- Past Japanese Issues/PRs/commits are not rewritten.

## Review

No scheduled review unless the maintainer adds a localized workflow later via a new decision record.
