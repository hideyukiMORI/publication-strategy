# Commit Message Conventions

This repository uses Conventional Commits. All commit text is **English**.

## Format

```text
<type>(<optional scope>): <description> (#<issue>)

[optional body]

[optional footer]
```

## Language

- Write `type`, `scope`, description, body, and footers in **English**.
- Include the related GitHub Issue number in the subject when practical.

Example:

```text
docs(experiments): add NeNe Qiita experiment log EXP-002 (#12)
```

## Common Types

| Type | Use in this repo |
| --- | --- |
| `docs` | Strategy docs, experiments, decisions, TODO, roadmap |
| `chore` | Repo maintenance without doc meaning change |
| `fix` | Correct wrong metrics, links, or policy text |
| `ci` | GitHub Actions or automation (if added later) |

`feat`, `refactor`, and `test` are reserved if tooling or scripts are added later.

## Body

Use the body when the reason is not obvious from the subject. Explain why the change exists, what trade-off was chosen, and whether follow-up work remains.

## Breaking Changes

Use `!` or a `BREAKING CHANGE:` footer when documented policy, experiment ID scheme, or folder conventions change incompatibly.

## Note on Product Repos

NeNe and NENE2 may use Japanese commit descriptions in their own repositories. That convention does **not** apply here.
