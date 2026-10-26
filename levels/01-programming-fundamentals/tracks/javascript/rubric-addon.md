# Level 01 rubric add-on: JavaScript

These criteria are added to the [core rubric](../../rubric.md) and count toward the average.

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L01-JS-R1 | **Modern JS idioms** | `const` by default, `let` only when reassigned, no `var`. Strict equality (`===`). Template literals. `for...of` or array methods used appropriately. Explicit number validation (`Number.isNaN`/`Number.isInteger`). Errors thrown as `Error` objects. | Array methods (`filter`/`map`/`find`/`reduce`) used where they read better than loops. No accidental mutation (copies before `sort`). Readline closed in `finally`. | `var`, `==`, `parseFloat` accepting `"12abc"`, `for...in` over arrays, thrown strings, program hangs on exit. |
| L01-JS-R2 | **Tooling & modules** | `package.json` with `"type": "module"` and a working `npm start`. ESLint passes with 0 problems. Prettier applied. `node_modules/` git-ignored. Code split into ES modules with named exports, or one clearly organised file. | `lint` and `format` scripts present. The README states the exact Node version. | No `package.json`, lint errors, committed `node_modules`, unexplained runtime dependencies. |
