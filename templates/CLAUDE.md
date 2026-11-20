# CLAUDE.md: <Project name>

<!-- Template from H0m3Lab/.github. Replace every <placeholder>; delete sections that do not apply. -->

Guide for AI coding agents (and humans) working on this repository. Organization rules:
https://github.com/H0m3Lab/.github/blob/main/STANDARDS.md

## Purpose

<One paragraph: what the app does and for whom.>

## Architecture

<Main components and how data flows between them. Name the files.>

## Stack

- Language / runtime: <...>
- Frameworks / libraries: <...>
- Storage: <...>
- Packaging: Docker (`<Dockerfile path>`), Compose example in `<file>`

## Repository layout

```
<tree of the important paths with one-line notes>
```

## Commands

| Task | Command |
|---|---|
| Install | `<...>` |
| Build | `<...>` |
| Test | `<...>` |
| Lint | `<...>` |
| Run locally | `<...>` |
| Docker image | `docker build -t <name>:local .` |

CI (`.github/workflows/ci.yml`) runs <list>. Keep it green.

## Configuration

Environment variables are documented in the README settings table and `.env.example`. When you add
or change one: update both, give it a safe default, and add a CHANGELOG line.

## Conventions

- <Code style, naming, error handling, logging>
- Keep dependencies few; ask before adding one.
- <Project-specific rules>

## Data safety (do not break)

- <What must never be lost or rewritten, e.g. user history, migrations rule>
- Schema changes are new numbered migrations. Never edit an applied one.

## Security

- Never hardcode credentials or private values (real IPs, host names, domains, keys, names). Use
  placeholders like `example.com` / `192.0.2.10` in code, tests, and docs.
- <Auth model, what is exposed, what must stay internal>

## Releases

Semantic versioning. Version lives in `<file>`. Steps: CHANGELOG `[Unreleased]` → new version section,
bump version, commit, tag `vX.Y.Z`, GitHub release with the changelog section as notes.
