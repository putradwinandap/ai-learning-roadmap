# Level 06 project: Production-ready Gather

Take your Level 05 application and make it something a team could safely work on and ship every day.

**Location:** your Level 05 repo (record its location in `progress.md`). All Level 06 work is done through **pull requests**.

## Requirements

### Must

| ID | Requirement |
|---|---|
| L06-M1 | **Test strategy** documented (`docs/testing.md`): what is tested at which level and why. |
| L06-M2 | Tests added or refactored to match the strategy: unit (domain), integration (API + DB), E2E (critical flows). Coverage report generated. Domain logic ≥ 80% covered. |
| L06-M3 | **Dockerfiles** for frontend and backend: multi-stage, non-root user, small final image, `.dockerignore`. |
| L06-M4 | **Docker Compose** brings up the whole stack (frontend, API, database) locally with one command, with health checks. |
| L06-M5 | **CI pipeline** (e.g. GitHub Actions) on every PR: install with lockfile, lint, type-check, unit + integration tests (with a DB service), build images. Required to pass before merge. |
| L06-M6 | **CD pipeline**: merges to `main` deploy automatically. Secrets come from the CI secret store. Migrations run as part of the deploy. |
| L06-M7 | **Team workflow**: protected `main`, all changes via PR with a description template. At least **5 merged PRs** for this level. Conventional commit messages. |
| L06-M8 | **Code review**: at least 2 PRs reviewed by your AI mentor (or a human) with comments addressed in follow-up commits. |
| L06-M9 | **Dependency hygiene**: lockfiles committed, automated dependency updates configured, vulnerability scan in CI. |
| L06-M10 | **Docs**: README updated (one-command local setup), CONTRIBUTING.md, CHANGELOG.md, and at least 1 ADR. |

### Should

| ID | Requirement |
|---|---|
| L06-S1 | Pre-commit hooks for formatting and linting. |
| L06-S2 | CI caching makes the pipeline noticeably faster. Pipeline time documented. |
| L06-S3 | Preview deployments per PR. |
| L06-S4 | Release tags with semantic versioning and generated release notes. |
| L06-S5 | One legacy area refactored safely: characterisation tests first, then the refactor, in separate PRs. |

### Stretch

| ID | Requirement |
|---|---|
| L06-X1 | Contract tests between frontend and API (or schema-based type generation checked in CI). |
| L06-X2 | Container image scanning and SBOM generation. |
| L06-X3 | Rollback procedure documented and rehearsed. |

## Acceptance scenarios

1. Fresh clone → `docker compose up` → the app works locally.
2. Open a PR with a failing test → CI blocks the merge.
3. Merge a PR → it deploys automatically. The live version shows the change.
4. The PR list shows ≥ 5 merged PRs with descriptions and review comments.
