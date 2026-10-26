# Level 05 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md).

## 1. TypeScript
- Interface vs type alias; what is a union type; what is narrowing?
- *Spot the bug:* code that assumes an optional field is always present.
- Why is `any` dangerous? What's `unknown` for?

## 2. Components & state
- Props vs state. What is "lifting state up"?
- What is derived state, and why shouldn't you store it separately?
- *Predict:* what renders after a state update in a small component (framework of the learner's choice).
- Why do list items need stable keys?

## 3. Server state & data fetching
- Server state vs client state: why treat them differently?
- What is cache invalidation? When do you invalidate after a mutation?
- What is an optimistic update, and what must you do when it fails?

## 4. Auth in the browser
- Why is storing tokens in `localStorage` risky? Alternatives?
- What is CSRF? How do `SameSite` cookies help?
- What does CORS protect, and what doesn't it protect?

## 5. Rendering strategies
- CSR vs SSR vs SSG: one good use case for each.
- What is hydration?

## 6. Testing & deployment
- Component test vs E2E test: what belongs where?
- Why prefer selecting elements by role or label in tests?
- Why must frontend env vars never contain secrets?
- What happens to database migrations during a deploy?
