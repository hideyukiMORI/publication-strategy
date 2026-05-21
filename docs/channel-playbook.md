# Channel Playbook

Cross-project rules. Product-specific outlines and **outward article source files** remain in each product repo (e.g. NeNe `docs/publication-strategy.md`, NeNe `docs/articles/` for Zenn).

## Language and Asset Placement

| Content | Language | Repository |
| --- | --- | --- |
| Strategy, experiments, decisions, Issues, PRs | English | `publication-strategy` |
| Zenn / Qiita article source (body, frontmatter) | Japanese (JA channels) | Product repo (e.g. NeNe) |
| DEV / Reddit / HN article source | English | Product repo |
| Experiment log referencing a JA article | English (quote title only) | `publication-strategy` |

Do not copy Japanese article body text into `publication-strategy`. Link to the product-repo path instead.

## Channel Roles

| Channel | Best for | Article language | Article location | Products (initial) |
|---|---|---|---|---|
| **Zenn** | Philosophy, renovation story, maintainer voice | JA | Product repo | NeNe (done) |
| **Qiita** | Hands-on tutorial, clone → first feature | JA | Product repo | NeNe (#178 next) |
| **DEV Community** | English renovation/API story | EN | Product repo | NeNe (#179) or NENE2 later |
| **Hashnode / blog** | Long-form follow-up | EN | Product repo | Optional |
| **Reddit r/PHP** | Technical feedback, not launch hype | EN | Product repo | After README + one article (#180) |
| **Hacker News** | Show HN when entry is polished | EN | Product repo | Last (#180) |
| **GitHub Profile README** | Portfolio hub linking all three | EN (or bilingual hub text) | Profile / product README | All |

## Preparation Order (portfolio level)

1. GitHub repository face (About, topics, homepage, license) — per product
2. Profile README as portfolio entry
3. One strong article per product before broad outreach
4. Reference implementation or demo that article can point to
5. English channel only after Japanese feedback pass (for NeNe sequence)

## Messaging (consistent)

Use across channels:

- Renovation vs rewrite (NeNe) / API-first minimal framework (NENE2)
- Review-friendly, visible conventions, AI-readable without magic claims
- Not a Laravel/Symfony replacement

Avoid:

- Attacking other frameworks or patterns
- Overstating production readiness
- Mixing three products in one first-impression post

## CTA Pattern

Every outward asset should end with the same GitHub-first path:

1. Link to the **specific repo**
2. Link to **demo or Quick Start** if it exists
3. Link to **latest Release**
4. Optional: link to sibling products only in footer or profile

## Experiment Discipline

Before starting a new channel:

1. Copy `docs/experiments/_template.md` to `EXP-NNN-{slug}.md`
2. State hypothesis and metric to watch
3. After 2–4 weeks, record result and next action in the same file
