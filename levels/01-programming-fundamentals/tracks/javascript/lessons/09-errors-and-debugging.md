# 09 (JavaScript): Errors and debugging

Core lesson: [09: Errors and debugging](../../../lessons/09-errors-and-debugging.md)

## Reading a stack trace

Node prints the error **first**, then the call stack from innermost to outermost:

```text
file:///home/ana/project/src/storage.js:9
    return JSON.parse(text);
                ^
SyntaxError: Unexpected token 'o', "not json" is not valid JSON
    at JSON.parse (<anonymous>)
    at loadNotes (file:///home/ana/project/src/storage.js:9:17)
    at main (file:///home/ana/project/src/main.js:6:17)
```

1. Error type and message (`SyntaxError: ...`).
2. The first `at` line that's **your** file: `storage.js:9:17` (line 9, column 17).
3. Further down: how you got there.

## A big difference from other languages

JavaScript often **doesn't throw** where you'd expect:

| Expression | Result |
|---|---|
| `Number("abc")` | `NaN`, no error |
| `[1, 2][10]` | `undefined`, no error |
| `({}).missing` | `undefined`, no error |
| `undefined.missing` | **TypeError**: Cannot read properties of undefined |
| `JSON.parse("oops")` | **SyntaxError** |

So validate values explicitly (`Number.isNaN`, `=== undefined`) instead of relying only on `try/catch`.

## try / catch / throw

```js
function parseRating(text) {
  const rating = Number(text);
  if (!Number.isInteger(rating) || rating < 1 || rating > 5) {
    throw new RangeError("Rating must be a whole number between 1 and 5");
  }
  return rating;
}

try {
  const rating = parseRating(await rl.question("Rating: "));
  console.log(`Saved rating ${rating}`);
} catch (error) {
  if (error instanceof RangeError) {
    console.log(`Invalid rating: ${error.message}`);
  } else {
    throw error; // not ours: don't swallow it
  }
}
```

Always `throw new Error(...)` (or a subclass), never a plain string.

## Re-prompt until valid

```js
async function askInteger(rl, prompt) {
  while (true) {
    const raw = (await rl.question(prompt)).trim();
    const value = Number(raw);
    if (raw !== "" && Number.isInteger(value)) return value;
    console.log("Please enter a whole number.");
  }
}
```

## Debugging tools

- `console.log({ total, count })` prints names and values together.
- Put `debugger;` in your code and run with the VS Code debugger to pause there.
- VS Code: click left of a line number to set a breakpoint, then **F5** → "Node.js". Use the "JavaScript Debug Terminal" to debug `npm start`.
