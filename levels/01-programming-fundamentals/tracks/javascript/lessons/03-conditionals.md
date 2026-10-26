# 03 (JavaScript): Conditionals

Core lesson: [03: Conditionals](../../../lessons/03-conditionals.md)

## if / else if / else

```js
const temperature = Number(await rl.question("°C: "));

if (temperature <= 0) {
  console.log("freezing");
} else if (temperature < 15) {
  console.log("cold");
} else if (temperature < 25) {
  console.log("mild");
} else {
  console.log("hot");
}
```

Always use braces `{}`, even for one-line bodies.

## Truthiness

Falsy values: `false`, `0`, `-0`, `""`, `null`, `undefined`, `NaN`. Everything else is truthy, **including `[]` and `{}`**.

```js
const name = (await rl.question("Name: ")).trim();
if (!name) {
  console.log("Name can't be empty");
}
```

## Ternary

```js
const label = age >= 18 ? "adult" : "minor";
```

Use it only for short, simple choices.

## switch

```js
switch (choice) {
  case "1":
    console.log("Start");
    break;
  case "2":
  case "s":
    console.log("Settings");
    break;
  case "q":
    console.log("Bye");
    break;
  default:
    console.log(`Unknown option: ${choice}`);
}
```

⚠️ Forgetting `break` makes execution "fall through" into the next case.

## Guard clauses in a function

```js
function describePages(text) {
  if (!text) return "Please type something";
  const pages = Number(text);
  if (!Number.isInteger(pages)) return "Whole numbers only";
  if (pages === 0) return "Nothing read today?";
  return `Great, ${pages} pages!`;
}
```
