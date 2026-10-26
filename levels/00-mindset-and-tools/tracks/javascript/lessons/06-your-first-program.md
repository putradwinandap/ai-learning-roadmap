# 06 (JavaScript): Your first program

Core lesson: [06: Your first program](../../../lessons/06-your-first-program.md)

## Output: `console.log`

```js
console.log("Hello, world!");
console.log("Two", "values"); // values are separated by a space
```

## Input: `readline/promises`

Node.js reads keyboard input through the built-in `readline` module. Copy this pattern for now. You'll understand `await` and modules properly in later levels.

```js
// first.mjs
import { createInterface } from "node:readline/promises";
import { stdin as input, stdout as output } from "node:process";

const rl = createInterface({ input, output });

const city = await rl.question("Which city do you live in? ");
console.log("Nice, I've heard", city, "is lovely.");

rl.close(); // without this, the program keeps waiting
```

`rl.question(...)` returns what the user typed **as text** (a string).

## Combining text: template literals

Use backticks and `${}`:

```js
console.log(`Welcome to ${city}!`);
console.log(`${city} has ${city.length} letters.`); // .length counts characters
```

You can put any expression inside `${}`.

## Cleaning input

`.trim()` removes spaces from both ends:

```js
const city = (await rl.question("Which city? ")).trim();
```

## Running your file

```bash
cd learner/level-00/scratch
node first.mjs
```

## Today's date and time (useful for computed details)

```js
const now = new Date();
console.log(now.toLocaleDateString("en-US", { weekday: "long" })); // e.g. "Monday"
console.log(now.getHours()); // 0–23
```

## `const` vs `let`

Use `const` by default. Use `let` only when you'll reassign the variable later. Never use `var`.

## Common first errors

| Error | Usually means |
|---|---|
| `SyntaxError: Invalid or unexpected token` | Missing quote or backtick. |
| `ReferenceError: citty is not defined` | Typo in a variable name, or used before it was declared. |
| `SyntaxError: Cannot use import statement outside a module` | File ends in `.js` instead of `.mjs`. |
| Program never exits | You forgot `rl.close()`. |
| `Error: Cannot find module` | Wrong folder or filename. Check with `pwd` and `ls`. |

## Exercise (JavaScript)

Do the core lesson's exercise in JavaScript: ask for a name and a favourite food, print a sentence with both, and add one computed detail of your choice (but don't reuse it in your project).
