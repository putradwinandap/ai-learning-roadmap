# 10 (JavaScript): Program structure

Core lesson: [10: Program structure](../../../lessons/10-program-structure.md)

## ES modules

Each file is a module. Export what other files need, and import it where it's used:

```js
// src/logic.js
export function totalPages(notes) {
  return notes.reduce((sum, n) => sum + n.pages, 0);
}
```

```js
// src/cli.js
import { totalPages } from "./logic.js";   // the .js extension is required
```

Use **named exports** (`export function ...`), which are easier to search and refactor than default exports.

## Entry point

```js
// src/main.js
import { run } from "./cli.js";

await run();
```

`package.json` → `"start": "node src/main.js"`, so `npm start` runs it.

## Constants

```js
// src/config.js
import path from "node:path";

export const DATA_FILE = path.join(import.meta.dirname, "..", "notes.json");
export const MENU = `
1) Add note
2) List notes
q) Quit
`;
```

## Dispatch table

```js
const ACTIONS = {
  1: addNote,
  2: listNotes,
};

export async function run() {
  const rl = createInterface({ input, output });
  let notes = loadNotes(DATA_FILE);
  try {
    while (true) {
      const choice = (await rl.question(`${MENU}> `)).trim().toLowerCase();
      if (choice === "q") break;
      const action = ACTIONS[choice];
      if (!action) {
        console.log("Unknown option");
        continue;
      }
      notes = await action(rl, notes);
      saveNotes(DATA_FILE, notes);
    }
  } finally {
    rl.close(); // always close, even on errors
  }
}
```

## Before submitting

```bash
npm run format
npm run lint
```

Lint should report **0 problems**. Don't commit `node_modules/`.
