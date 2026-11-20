# Contributing to H0m3Lab projects

Thanks for helping. This guide applies to every repository in the H0m3Lab organization unless the
repository has its own `CONTRIBUTING.md`.

## Before you start

- **Bugs:** open an issue with the bug template. Include the version, how you run it, and logs with
  your private values removed.
- **Features:** open a feature request first, so we can agree on the approach before you write code.
- **Security problems:** do **not** open a public issue. See [SECURITY.md](SECURITY.md).

## Pull requests

1. Fork the repository and branch from `main`.
2. Keep the change focused: one fix or feature per pull request.
3. Follow the project's `CLAUDE.md`. It describes the structure, the commands, and the rules
   (it is written for AI coding agents, but it is the developer guide for humans too).
4. Run the project's build and tests locally. CI runs the same checks.
5. Add a line under `## [Unreleased]` in `CHANGELOG.md`.
6. Update the README if you change settings, commands, or behavior users can see.
7. Fill in the pull request template.

## Rules every project shares

- **Never commit private values.** No real IP addresses, host names, domains, API keys, tokens,
  passwords, or personal names in code, comments, tests, docs, or commit messages. Use placeholders
  such as `example.com`, `192.0.2.10`, or `my-server`, and keep real values in git-ignored files
  (`.env`, `docker-compose.yml`, `*.local`) next to their `*.example` twins.
- **Never break existing data.** Database changes are new migrations; existing user data and
  settings must keep working after an upgrade.
- **No breaking changes without discussion.** If a change breaks configuration, data, or an API,
  say so in the pull request and the changelog, with upgrade steps.
- **Keep dependencies few.** Add one only when it clearly earns its place.
- **Semantic versioning:** `MAJOR.MINOR.PATCH`. Maintainers pick the version at release time.

## License

By contributing you agree that your contribution is licensed under the repository's license (MIT).
