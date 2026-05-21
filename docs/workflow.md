# Workflow

This repository uses GitHub Issues for work tracking and local Markdown files for project memory.

## Standard Flow

1. Create or reuse a focused GitHub Issue.
2. Confirm related local context in `docs/roadmap.md`, `docs/milestones/`, and `docs/todo/current.md`.
3. Create a branch from `main` named like `type/issue-number-summary`.
4. Implement the smallest useful change.
5. Update docs, roadmap, milestone, or TODO files when the decision or state changes.
6. Run the narrowest meaningful verification available (link checks, proofread, experiment template completeness).
7. Commit with Conventional Commits and include the Issue number.
8. Push the branch and create a PR linked to the Issue.
9. Merge after review.
10. Return local `main` to the merged, clean state.

There is no application runtime or CI test suite in this repository. Verification means the docs change is accurate, linked, and consistent with the language and scope policies.

## Branch Names

Use Conventional Commit style as the prefix:

- `docs/1-initial-governance`
- `docs/12-log-nene-qiita-experiment`
- `chore/5-weekly-metrics-snapshot`

Examples for this repo:

- `docs/3-update-positioning-matrix`
- `docs/8-exp-002-nene-qiita`

## PR Requirements

Every PR should include:

- purpose
- change summary
- verification results (what was checked)
- related Issue, preferably `Closes #number`
- remaining risks or follow-up work

## Local Project Memory

| Path | Role |
| --- | --- |
| `docs/roadmap.md` | Long-lived portfolio promotion direction |
| `docs/milestones/` | Medium-sized goals and acceptance criteria |
| `docs/todo/current.md` | Current task board and handoff notes |
| `docs/decisions/` | Strategy and process decisions worth keeping traceable |
| `docs/experiments/` | Channel experiments with hypotheses and metrics |
| `docs/positioning-matrix.md` | Weapon roles and priority hypothesis |
| `docs/channel-playbook.md` | Cross-channel rules |

Do not leave important decisions only in chat. If it changes how promotion should run, record it under `docs/decisions/` or update the relevant strategy doc in a PR.

Use `docs/decisions/` when a change affects portfolio priority, channel policy, language policy, metrics discipline, or cross-product messaging. Product architecture belongs in product repos.

## TODO Management

`docs/todo/current.md` summarizes active and next work for humans and AI agents.

The TODO file does not replace GitHub Issues. It summarizes state and links to Issues where possible.

## Product Repo Issues

Work that changes NeNe, NENE2, or nene2-python (README, article draft, release notes, code) uses Issues and PRs in those repositories.

This repo tracks cross-project coordination: log the experiment here, link the product Issue, and update metrics when results are known.

## AI Agent Responsibilities

AI agents should manage the normal lifecycle when asked to complete work:

- create or reuse the Issue
- create the Issue branch
- edit only relevant files
- verify the change
- commit, push, open PR, merge, and sync `main`
- update local docs that describe project state

If a user explicitly says investigation only, no commit, no PR, or another narrower scope, follow that instruction.
