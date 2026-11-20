<p align="center">
  <img src="h0m3lab-logo.jpg" alt="H0m3Lab logo" width="160">
</p>

```
> H0m3Lab
> WHERE CURIOSITY MEETS COMPUTE._
```

**H0m3Lab builds small, practical, self-hosted software for people who run their own servers.**

Every project here started as a real problem on a real homelab: a TV history that kept getting lost,
a media library that kept growing, a daily wall of update and CVE noise. Each one was then cleaned up,
documented, and published so anyone with a Docker host can use it.

## Projects

| Project | What it does | Stack |
|---|---|---|
| [**Seenarr**](https://github.com/H0m3Lab/seenarr) | A permanent, self-hosted TV watch history. A Trakt replacement fed by Plex and Sonarr, stored in one SQLite file you own. | TypeScript, Fastify, React, SQLite |
| [**Leanarr**](https://github.com/H0m3Lab/leanarr) | Seed-aware library shrinker. Re-encodes old video to HEVC without touching any file a torrent still needs. Optional remote GPU/CPU workers. | Python (stdlib only), ffmpeg |
| [**Stackbrief - Powered by AI**](https://github.com/H0m3Lab/stackbrief) | A daily Docker update and CVE scan, sorted by AI into a short brief: what an agent can do, what needs you, and what nobody can fix yet. | Shell, Trivy, regclient, Claude Code |
| [**Claude gateway**](https://github.com/H0m3Lab/claude-gateway) | Claude Code as one shared service for your self-hosted apps: any app posts a job and gets text back, while Claude keeps one memory of your setup. No shell, no host access. | Node.js, Claude Code |

## What we care about

- **Your data stays yours.** Plain files and SQLite on your own disk. No accounts, no telemetry, no cloud dependency unless you choose one.
- **Safe by default.** Report modes before write modes, fail-closed checks, backups before imports, append-only history.
- **Small and boring.** Few dependencies, one `docker compose up`, settings in `.env`. Simple beats clever.
- **AI as a tool, not a pilot.** AI helps sort, explain, and write code. It does not act on your systems on its own.

## Contributing

Issues and pull requests are welcome on every project. Please read the
[contribution guide](https://github.com/H0m3Lab/.github/blob/main/CONTRIBUTING.md) first, and report
security problems privately through the **Security** tab of the affected repository
([security policy](https://github.com/H0m3Lab/.github/blob/main/SECURITY.md)).

All projects are MIT licensed.
