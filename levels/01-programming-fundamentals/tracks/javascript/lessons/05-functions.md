# 05 (JavaScript): Functions

Core lesson: [05: Functions](../../../lessons/05-functions.md)

## Declarations and arrow functions

```js
function area(width, height) {
  return width * height;
}

const perimeter = (width, height) => 2 * (width + height);

console.log(area(4, 5)); // 20
```

Use function declarations for named, top-level functions. Arrow functions are great for short callbacks (`.map(x => x * 2)`).

A function without `return` returns `undefined`.

## Default parameters and "named arguments"

```js
function greet(name, greeting = "Hello") {
  return `${greeting}, ${name}!`;
}

// JS has no keyword arguments. Pass an object instead:
function createBook({ title, author, year = 2026 }) {
  return { title, author, year };
}
createBook({ title: "Dune", author: "Herbert" });
```

## Scope

```js
let count = 10;

function reset() {
  let count = 0; // a NEW local variable that shadows the outer one
}

reset();
console.log(count); // 10
```

Variables declared with `let`/`const` are scoped to the nearest `{ }` block.

## Documentation comments (JSDoc)

```js
/**
 * Convert a temperature from Celsius to Fahrenheit.
 * @param {number} celsius
 * @returns {number}
 */
function toFahrenheit(celsius) {
  return (celsius * 9) / 5 + 32;
}
```

Editors use JSDoc to show hints. It's optional at this level.

## Pure vs. side effects

```js
function average(numbers) {             // pure
  return numbers.length ? numbers.reduce((a, b) => a + b, 0) / numbers.length : 0;
}

function printReport(numbers) {         // side effect: output
  console.log(`Average: ${average(numbers).toFixed(2)}`);
}
```
