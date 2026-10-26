# Level 01 quiz bank

The AI builds a 10-question quiz from these areas (see [ai/quiz-protocol.md](../../ai/quiz-protocol.md)). Write *Predict* and *Spot the bug* snippets in the learner's programming language.

## 1. Values, variables and types

- Difference between `42` and `"42"`; what happens when you add them in the learner's language.
- Why convert input before doing math?
- *Predict:* `0.1 + 0.2` printed raw and rounded to 2 decimals.
- Why is a float risky for money? Name alternatives.

## 2. Operators and expressions

- *Predict:* precedence (`10 - 2 * 3`), modulo (`17 % 5`), integer division.
- `=` vs `==` (and `===` for JavaScript).
- Explain short-circuit evaluation with an example that prevents an error.

## 3. Conditionals

- *Spot the bug:* an `if / else if` chain where the specific case comes after the general one.
- What is a guard clause? Rewrite a nested validation.
- Truthiness: why `if amount:` can be a bug.

## 4. Loops

- `for` vs `while`: when to use each.
- *Predict:* a loop with a range boundary (off-by-one).
- *Spot the bug:* an infinite `while` loop.
- Explain the accumulator pattern; `break` vs `continue`.

## 5. Functions

- Parameter vs argument; return vs print.
- What's a local variable? *Predict:* a function that assigns to a variable with the same name as an outer one.
- What makes a function pure? Why does it matter?
- *Apply:* split a described program into well-named functions.

## 6. Collections

- List vs dictionary: when to use each.
- *Predict:* aliasing (`b = a`, then modify `b`).
- *Apply:* describe how to compute totals per category.
- Index of the last element; what happens when you index out of range.

## 7. Strings and I/O

- Why normalise input? Show `trim` + `lower`.
- *Spot the bug:* splitting user input and indexing `parts[1]` without checking length.
- Format a number with 2 decimals and fixed width.

## 8. Files and persistence

- What is serialization? JSON vs CSV for records.
- What should happen on first run (no file)? With a corrupt file?
- Why list positions make bad IDs.
- Relative path vs working directory problem.

## 9. Errors and debugging

- Syntax vs runtime vs logic errors.
- Why not catch all exceptions? Why keep `try` blocks small?
- How to read a stack trace in the learner's language.
- Describe a debugging process for a wrong total.

## 10. Program structure

- Name the three layers of a CLI program, with an example function for each.
- Why logic functions shouldn't print.
- What `main` should look like and why.
