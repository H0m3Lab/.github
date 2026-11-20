# H0m3Lab repository standard

How every H0m3Lab project is set up. The goal is projects that are easy to find, install, use,
maintain, and develop further with Claude Code, without process for its own sake.

## Files every repository has

| File | Notes |
|---|---|
| `README.md` | What it does, install, settings table, troubleshooting, license. Commands must match the code. |
| `CLAUDE.md` | Developer guide for AI agents and humans. Start from [templates/CLAUDE.md](templates/CLAUDE.md). |
| `CHANGELOG.md` | [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) format. Start from [templates/CHANGELOG.md](templates/CHANGELOG.md). |
| `LICENSE` | MIT for new projects. Never change an existing license. |
| `.gitignore` | Ignores `.env`, local compose files, data, build output. |
| `.env.example` | Every secret setting, empty. Real values only in the git-ignored `.env`. |
| `.gitattributes` | `* text=auto eol=lf` so scripts work when cloned on Windows. |
| `.github/workflows/ci.yml` | See CI below. Examples in [templates/ci/](templates/ci/). |
| `.github/project.json` | Metadata for a future project showcase. See [templates/project.json](templates/project.json). |

`CONTRIBUTING.md`, `SECURITY.md`, and the issue and pull request templates come from this
`.github` repository and apply to every repo automatically. Add a repo-level copy only when a
project needs something different.

## Development principles

1. Favor simple, maintainable architectures.
2. Avoid unnecessary dependencies.
3. Maintain backward compatibility where practical.
4. Never hardcode credentials, API keys, or private infrastructure details.
5. Document configuration changes (README settings table, `.env.example`, CHANGELOG).
6. Add automated tests for meaningful functionality.
7. Preserve existing user data and configuration: schema changes are new migrations.
8. Use semantic versioning.
9. No breaking changes without explicit approval.
10. Reliability and maintainability over cleverness.

## Private values

Public repositories never contain the maintainer's real IP addresses, host names, domains, keys,
tokens, tracker names, or personal names, in any commit. Real values live in git-ignored files next to
the code, with `*.example` twins that hold placeholders (`example.com`, `192.0.2.10`, `my-server`).
CI scans the full history with gitleaks on every push.

## CI

Small and fast. Least privilege: `permissions: contents: read` at the top of every workflow, and
`persist-credentials: false` on checkout. Typical jobs:

- **check:** install, lint, build, unit tests (whatever the stack has)
- **docker:** `docker build` of each image, without pushing
- **secrets:** gitleaks over the full history

No workflow publishes releases, images, or deploys anything until it has been run and checked by hand.
No Dependabot or other bots that open pull requests nobody reviews.

## Versions and releases

- `MAJOR.MINOR.PATCH`. While a project is `0.x`, a minor bump may contain breaking changes, but the
  changelog must say so.
- The version lives in one place in the code (e.g. `package.json`, a `VERSION` constant). The git tag is `v` + that version.
- Release steps: move `## [Unreleased]` items into a new version section with the date, bump the version
  in code, commit, tag `vX.Y.Z`, then create the GitHub release with the changelog section as notes.
- Release notes sections: Added, Changed, Fixed, Security, and **Breaking** with upgrade steps when needed.
- Never rewrite or re-tag published history.

## Repository settings

- Private vulnerability reporting: **on**.
- Discussions: off until there is a real need.
- Topics: `self-hosted`, `homelab`, `docker`, plus project-specific ones.
