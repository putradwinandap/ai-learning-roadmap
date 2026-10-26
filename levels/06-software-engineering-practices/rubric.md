# Level 06 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L06-R1 | **Test strategy & quality** | Documented strategy matches the tests. Right balance of unit, integration and E2E. Domain ≥ 80% coverage. No flaky tests. | Thoughtful trade-offs, test data factories, contract tests. | Coverage chasing with assertion-free tests, flaky E2E, no strategy. |
| L06-R2 | **Containerisation** | Multi-stage, non-root, small images. Compose brings everything up with health checks. | Images scanned. Reproducible builds. Dev/prod parity explained. | Huge images, root user, secrets baked into images, Compose doesn't work from a fresh clone. |
| L06-R3 | **CI** | Lint, type-check, test (with DB) and build on every PR, required for merge, lockfile installs. | Fast pipeline (caching, parallel jobs), clear failure output. | CI optional or red, tests skipped in CI. |
| L06-R4 | **CD & release** | Automatic deploy from `main`, secrets in the CI store, migrations handled. | Preview environments, tagged releases, documented rollback. | Manual deploys, secrets in workflow files. |
| L06-R5 | **Collaboration workflow** | Protected branch, ≥ 5 PRs with templates and descriptions, conventional commits, review comments addressed. | Small focused PRs. A history that is easy to bisect. | Direct pushes to `main`, giant PRs, ignored reviews. |
| L06-R6 | **Dependency & supply-chain hygiene** | Lockfiles, automated updates, vulnerability scan in CI. | Pinned CI actions, SBOM, documented update policy. | No lockfile, known critical vulnerabilities ignored. |
| L06-R7 | **Documentation** | README, CONTRIBUTING, CHANGELOG and ≥ 1 ADR are accurate and useful. | Runbooks, architecture overview kept current. | Outdated or missing docs. |
