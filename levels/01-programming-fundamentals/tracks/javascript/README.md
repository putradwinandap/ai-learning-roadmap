# Level 01: JavaScript (Node.js) track

## Versions and tools

| What | Use |
|---|---|
| Node.js | Current LTS (22 or newer) |
| Package manager | `npm` (ships with Node) |
| Formatter | Prettier |
| Linter | ESLint (flat config) |
| Debugger | VS Code JavaScript debugger (F5), or `node --inspect` |
| Built-in modules you'll use | `node:fs`, `node:path`, `node:readline/promises`, `node:process` |

## Project setup

From now on, each project gets a `package.json`:

```bash
cd learner/level-01/project
npm init -y
npm install --save-dev eslint @eslint/js globals prettier
```

Edit `package.json` to add:

```json
{
  "type": "module",
  "scripts": {
    "start": "node src/main.js",
    "lint": "eslint .",
    "format": "prettier --write ."
  }
}
```

- `"type": "module"` lets regular `.js` files use `import`, so you no longer need `.mjs`.
- `npm start` runs your program, `npm run lint` checks it, `npm run format` formats it.

Create `eslint.config.js`:

```js
import js from "@eslint/js";
import globals from "globals";

export default [
  js.configs.recommended,
  { languageOptions: { globals: globals.node } },
];
```

Add a `.gitignore` containing `node_modules/`.

### Recommended layout

```text
learner/level-01/project/
├── README.md
├── package.json
├── eslint.config.js
└── src/
    ├── main.js        # entry point
    ├── cli.js         # input/output
    ├── logic.js       # pure functions
    └── storage.js     # load/save
```

The program itself must use **only built-in Node modules**. ESLint and Prettier are dev tools, so they're allowed.

## Lessons

| # | Track lesson |
|---|---|
| 01 | [Values, variables and types](lessons/01-values-variables-and-types.md) |
| 02 | [Operators and expressions](lessons/02-operators-and-expressions.md) |
| 03 | [Conditionals](lessons/03-conditionals.md) |
| 04 | [Loops](lessons/04-loops.md) |
| 05 | [Functions](lessons/05-functions.md) |
| 06 | [Collections](lessons/06-collections.md) |
| 07 | [Strings and input/output](lessons/07-strings-and-input-output.md) |
| 08 | [Files and persistence](lessons/08-files-and-persistence.md) |
| 09 | [Errors and debugging](lessons/09-errors-and-debugging.md) |
| 10 | [Program structure](lessons/10-program-structure.md) |

## Grading add-on

[rubric-addon.md](rubric-addon.md)

## References

- [MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [Node.js documentation](https://nodejs.org/docs/latest/api/)
- [javascript.info](https://javascript.info/)
