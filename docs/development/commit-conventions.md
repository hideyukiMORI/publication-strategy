# Commit Message Conventions

This repository uses Conventional Commits, aligned with NeNe and NENE2.

## Format

```text
<type>(<optional scope>): <description> (#<issue>)

[optional body]

[optional footer]
```

## Language

- Keep `type`, `scope`, `BREAKING CHANGE`, and other Conventional Commits keywords in **English**.
- Write the **description and body in Japanese**.
- Include the related GitHub Issue number in the subject when practical.

Example:

```text
docs(experiments): NeNe Qiita 実験ログ EXP-002 を追加する (#12)
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
