# Level 00: JavaScript (Node.js) track

In Levels 00–02 you'll run JavaScript in the terminal with **Node.js**. Browser JavaScript comes in Level 03.

## Versions and tools

| What | Use |
|---|---|
| Node.js | Current **LTS** release (22 or newer) |
| Run a file | `node hello.mjs` |
| Formatter | [**Prettier**](https://prettier.io/) (`npx prettier --write .`) |
| Linter | ESLint is introduced in Level 01 |
| Editor extension (VS Code) | "Prettier - Code formatter" |
| Optional: version manager | [`fnm`](https://github.com/Schniz/fnm) or [`nvm`](https://github.com/nvm-sh/nvm) |

## Why `.mjs`?

Files ending in `.mjs` use modern **ES modules** (`import` syntax, top-level `await`) without extra configuration. You'll switch to `package.json` with `"type": "module"` in Level 01.

## Lessons in this track

- [04: Editor and environment](lessons/04-editor-and-environment.md): installing Node.js, Prettier and editor setup
- [06: Your first program](lessons/06-your-first-program.md): `console.log`, reading input, template literals

## Grading add-on

[rubric-addon.md](rubric-addon.md)
