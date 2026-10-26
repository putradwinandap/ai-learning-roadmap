# Level 02 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L02-R1 | **Correctness of business rules** | All loan rules enforced, all acceptance scenarios pass. | Edge cases beyond the spec handled and documented. | Rules bypassable through some path, wrong overdue logic. |
| L02-R2 | **Data structures & complexity** | O(1) lookups by key. The README's Big-O claims are correct and justified. | Thoughtful trade-offs discussed (memory vs. speed, ordering). | Linear scans for key lookups, wrong or missing complexity analysis. |
| L02-R3 | **Algorithm implementation** | Own merge sort or quicksort is correct (including empty, single-element and duplicate inputs) and tested against the built-in sort. | Stable sort, generic over the sort key, clear explanation of how it works. | Incorrect on edge cases, copied without understanding (fails the understanding check). |
| L02-R4 | **Design & separation** | Domain logic independent of the CLI and storage. Cohesive classes or modules with clear names and responsibilities. | Dependencies passed in (clock, storage), making the domain trivially testable. Composition over inheritance. | God class, CLI code mixed with rules, hidden global state. |
| L02-R5 | **Clean code** | Small functions, meaningful names, no duplication, no dead code. | Reads like a specification. Refactoring is visible in the history. | Long functions, copy-paste, unclear names, magic values. |
| L02-R6 | **Testing** | ≥ 20 meaningful, independent tests following arrange-act-assert. They cover rules and edge cases and all pass. | TDD visible in history. Time injected. Descriptive test names that document behaviour. | Few tests, tests that only cover the happy path, tests depending on each other or on the real date. |
| L02-R7 | **Documentation & Git** | README covers running, testing and design decisions. Incremental commits. | Clear trade-off discussion. A tidy, readable history. | Missing test instructions or design section. |
