# CI examples

Working workflows from H0m3Lab projects. Copy one to `.github/workflows/ci.yml` in a new repo and
adjust the image names and paths. Every one has `permissions: contents: read`, `persist-credentials: false`,
and a gitleaks full-history scan (the gitleaks container, because gitleaks-action needs a paid license for organizations).

- `node-app.yml`: Node/TypeScript app (Seenarr): npm ci, build, test, Docker build
- `python-app.yml`: Python app (Leanarr): compile, ruff, Docker build
- `shell-compose.yml`: shell + Compose stack (Stackbrief): ShellCheck, compose config, Docker builds
