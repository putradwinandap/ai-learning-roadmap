# 06: Your first program

> **Track lesson available.** Syntax for this lesson is in `tracks/<your-language>/lessons/06-your-first-program.md` ([Python](../tracks/python/lessons/06-your-first-program.md), [JavaScript](../tracks/javascript/lessons/06-your-first-program.md)).

## Why this matters

You've set up your tools. Now you'll write a program that talks to a user. You'll meet the core loop of all software, **input → processing → output**, and the full workflow: write, run, fix, commit.

## Key ideas

### A program is a list of instructions

A program runs **top to bottom**, one statement at a time, unless you tell it otherwise (you'll learn how in Level 01).

```text
print "What's your name?"
name ← read a line from the keyboard
print "Hello, " + name + "!"
```

That's pseudocode: plain-language steps that look a little like code. Writing pseudocode before real code is a habit worth building.

### Input, processing, output

| Part | Example |
|---|---|
| **Input** | Read text from the keyboard, read command-line arguments, read a file |
| **Processing** | Combine text, do math, make decisions |
| **Output** | Print to the screen, write a file |

### Variables (preview)

`name` above is a **variable**: a named box that holds a value. You'll study variables properly in Level 01. For now: you put something in, then use it later by name.

### Running your program

1. Save the file with the right extension (`.py`, `.js`, `.go`, ...).
2. In the terminal, `cd` into the folder that contains it.
3. Run it with your language's command (your track shows how).

### Reading errors

Your first programs will fail. Typical first errors:

- **Syntax error**: you broke the language's grammar (missing quote or bracket). The error points to the line, or the one just after.
- **Name error / not defined**: a typo in a variable name.
- **File not found**: you're running from the wrong folder (`pwd` to check).

Read the **whole** message, find the line number, look at that line *and the one before it*.

## Exercise

1. Write a program that asks for the user's name and favourite food, then prints a sentence using both.
2. Break it on purpose: remove a quote, misspell a variable. Run it and read each error. What does each message tell you?
3. Fix it, run it, and commit it in `learner/level-00/scratch/` (or anywhere outside `project/`).

## Check your understanding

1. In what order do statements in a simple program run?
2. Name the input, the processing and the output in your exercise program.
3. An error says the problem is on line 8, but line 8 looks fine. Where else should you look?

## Next

You're ready for the [Level 00 project](../project.md).
