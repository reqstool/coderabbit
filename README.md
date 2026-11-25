# coderabbit

Central [CodeRabbit](https://coderabbit.ai) configuration for the reqstool
organization
([central configuration](https://docs.coderabbit.ai/configuration/central-configuration)).

`.coderabbit.yaml` at the root of this repository applies to every repository
in the organization that has no `.coderabbit.yaml` of its own.

## Per-repository rules

A repository that needs its own rules adds a small `.coderabbit.yaml` with
`inheritance: true` and only those settings. Without `inheritance: true` the
repository file replaces this one entirely. With it, scalars in the repository
file win, objects merge key by key, lists combine, and `path_instructions`
match by path
([inheritance and merging](https://docs.coderabbit.ai/configuration/inheritance-and-merging)).

## Behaviour

- Advisory only: CodeRabbit never requests changes, and a bot approval does not
  count as the required approving review.
- Draft PRs are reviewed. Renovate, Dependabot and GitHub Actions PRs are not;
  `@coderabbitai review` on one of those forces a review.
- The summary goes in the walkthrough comment, not the PR description.
- `protect-main` requires every review thread to be resolved, so a CodeRabbit
  comment blocks merge until it is resolved. Reply in the thread when it is
  wrong.
- `AGENTS.md` and `CLAUDE.md` in the repository under review are read as
  review guidelines.

A change here changes code review for every repository in the organization.
