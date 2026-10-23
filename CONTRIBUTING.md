# Contributing

Thanks for your interest in a pflege-de-labs project. This is the default contribution guide for
the organization. Many repositories have their own `CONTRIBUTING.md` or `AGENTS.md` with build
instructions and conventions; where they say more, they apply in addition to this guide.

## Before you start

- **Bugs and feature requests** go into the repository's issues. Search first; one topic per
  issue.
- **Security problems are not issues.** Report them privately, see the
  [security policy](https://github.com/pflege-de-labs/.github/blob/main/SECURITY.md).
- For anything bigger than a small fix, open an issue first and describe what you plan to do. It
  saves both of us from a pull request that does not fit.

## Pull requests

- Work on a branch and open a pull request against `main`. Nobody pushes to `main` directly,
  maintainers included.
- Keep a pull request to one topic. Small pull requests are reviewed faster.
- Commit messages follow [Conventional Commits](https://www.conventionalcommits.org):
  `feat:`, `fix:`, `docs:`, `refactor:`, `test:`, `chore:`, `build:`, `ci:`.
- Meet the repository's definition of done, usually listed in its pull request template: tests,
  lint, documentation and changelog.
- CI must pass, and a maintainer other than the author approves the pull request before it is
  merged.
- Describe **what** changed and **why** in the description. Link the issue if there is one.

## Pull requests from forks

Workflows on a first contribution from a fork run only after a maintainer has looked at the
change. Changes to `.github/`, build and release configuration get a particularly close review.

## AI coding agents

You may use AI coding agents. You remain the author of the change and responsible for it, and
the process above applies unchanged. Read the
[policy on agent-assisted development](https://github.com/pflege-de-labs/.github/blob/main/agent-assisted-development.md)
before you open a pull request written with one.

## Licence

By contributing you agree that your contribution is licensed under the repository's licence, and
you confirm that you have the right to contribute it.
