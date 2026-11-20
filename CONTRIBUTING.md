# Contributing to GitHub Security Alert

We want to make contributing to this project as easy as possible.

## Pull Requests

We actively welcome your pull requests and forks.

Before submitting a pull request, please verify that any modified GitHub Actions workflow or embedded script is syntactically valid and tested (for example using `workflow_dispatch` with `dry_run: true`).

## Enhancements

Propose your contribution by:

1. [Submitting a proposal via GitHub Issues](https://github.com/fugerit79/github-security-alert/issues/new)

Any contribution is accepted (automation, security rules, testing, documentation, etc.).

## Bug Fixes

You can use [GitHub Issues](https://github.com/fugerit79/github-security-alert/issues/new) to report bugs or false positives/negatives in the alerting workflows.

## Commit Conventions

This repository follows [Conventional Commits](https://www.conventionalcommits.org/):

```text
<type>(<scope>): <summary>

[Optional concise description of the change]
```

Common types include `feat`, `fix`, `ci`, `docs`, `refactor`, `test`, and `chore` (for example `ci: configure high impact cve watchdog` or `docs: add contributing and changelog guidelines`).

## Generative AI Policy

Contributions assisted by Generative AI tools are welcome, provided that the committer reviews, tests, and takes full responsibility for the submitted changes (including code quality, correctness, security, and license compliance).

When submitting AI-assisted changes, please add a brief attribution note to the commit message body (or pull request description) using one of the following templates:

```text
Generated with the support of AI (<Agent/Tool>)
```

or, following the [fugerit-org/fj-doc](https://github.com/fugerit-org/fj-doc/blob/main/CONTRIBUTING.md) convention:

```text
Note: Generative AI [VENDOR] assistance was used [to DETAIL ON THE CONTRIBUTION].
```

For example:

```text
ci(watchdog): refine CISA KEV alert deduplication

Added issue deduplication and EPSS score enrichment to the daily watchdog workflow.

Generated with the support of AI (Antigravity Agent)
```

## License

By contributing to [github-security-alert](https://github.com/fugerit79/github-security-alert), you agree that your contributions will be licensed under the repository's license terms.
