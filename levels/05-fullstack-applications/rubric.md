# Level 05 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L05-R1 | **Product completeness** | All Must pages and flows work on the live deployment. All acceptance scenarios pass. | Polished UX: sensible defaults, helpful empty states, no dead ends. | Broken flows, features only working locally. |
| L05-R2 | **Component & state architecture** | Small, reusable components. Clear separation of server state, client state and UI. No prop-drilling mess. | Feature-based folder structure. Custom hooks/composables. Derived state instead of duplicated state. | Giant components, duplicated fetch logic, state in too many places. |
| L05-R3 | **Type safety** | Strict TypeScript, no unjustified `any`, API responses typed. | Types shared or generated from the API contract. Runtime validation at the boundary. | `any` everywhere, type errors ignored, untyped API data. |
| L05-R4 | **Auth & security** | Secure session/token handling, protected routes, CORS limited to the real origin, CSRF considered, no secrets in the frontend bundle. | Security trade-offs documented. Session expiry handled gracefully. | Tokens in `localStorage` without justification, `*` CORS with credentials, API keys in the bundle. |
| L05-R5 | **UX, accessibility & performance** | Responsive, keyboard-accessible, focus managed, a11y ≥ 90, sensible loading and error UI. | Optimistic updates. Perf ≥ 80. Reduced-motion respected. | Inaccessible custom widgets, layout shifts, spinners everywhere. |
| L05-R6 | **Testing** | Component tests for key pieces + ≥ 3 E2E tests of critical flows, all passing. | Tests run against a seeded environment. Stable selectors (roles/labels). | Brittle snapshot-only tests, no E2E. |
| L05-R7 | **Deployment & configuration** | Frontend, API and DB deployed with HTTPS. Environment-specific config. Reproducible deploy steps. | Preview deployments. Health check endpoint. Migrations run automatically on deploy. | Manual, undocumented deploys. Hard-coded URLs. |
| L05-R8 | **Documentation** | Architecture overview, setup, env vars, URLs. | Diagram, decision log, known limitations. | Missing setup for one of the apps. |
