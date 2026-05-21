# Decision 0003: Japanese Only for Outward Article Assets

Date: 2026-05-22

## Status

Accepted

## Context

Decision 0002 made all collaboration text in `publication-strategy` English. The maintainer further clarified that **Japanese is not a general alternate language** for this portfolio. Japanese exists only where an outward article for a Japanese channel (Zenn, Qiita, and similar) requires it.

This repository logs strategy and experiments in English. It does not store Japanese article drafts or body copy.

## Decision

### English everywhere in `publication-strategy`

- Markdown docs, Issues, PRs, commit messages, experiment logs, and decision records stay **English**.

### Japanese only in product repos, only for article assets

Japanese is allowed **only** for source files that will be published (or were published) on Japanese outward channels, stored in product repositories:

- Example: NeNe `docs/articles/zenn-renovating-legacy-php-framework.md` for Zenn
- Future Qiita tutorial drafts in NeNe (or linked product repo paths)

Those files are **article data**, not strategy logs. They follow channel language (Japanese for Zenn/Qiita), not this repo's language policy.

### Cross-reference from this repo

When logging an experiment here:

- Write the experiment log in English.
- Link to the article asset path in the product repo.
- You may **quote** the article title or a short excerpt in the original language for traceability.

Do not copy full Japanese article body text into `publication-strategy`.

## Alternatives Considered

| Option | Rejected because |
|---|---|
| Store JA article drafts under `publication-strategy/docs/articles/` | Mixes outward content with English strategy logs |
| Allow Japanese Issues/PRs in product repos for article work | Out of scope for this repo; product repos keep their own rules |

## Consequences

- Channel playbook treats Zenn/Qiita assets as product-repo files.
- Agents must not create Japanese Markdown in `publication-strategy` except minimal quoted titles in English experiment logs.

## Related

- Decision 0002 — English collaboration text in this repo
- NeNe article example: `docs/articles/zenn-renovating-legacy-php-framework.md`
