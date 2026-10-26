# 05: Learning with AI

## Why this matters

AI can make you learn **much faster**, or stop you from learning at all. The difference is how you use it. In this curriculum the AI is your mentor and corrector. This lesson explains how to get the most out of it.

## Key ideas

### The ghostwriter trap

If the AI writes your code, *you* learn nothing, even if you read it carefully. It's the tutorial trap at full speed. Signs you've fallen in:

- You can't explain why a line is there.
- You couldn't rewrite the code tomorrow without help.
- You feel productive but anxious when the AI is unavailable.

That's why the rules in [`AGENTS.md`](../../../AGENTS.md) forbid the AI from writing your project, and why every review includes an **understanding check**.

### Good ways to use your AI mentor

| Use it to... | Example prompt |
|---|---|
| Explain a concept in another way | "Explain recursion with a non-math analogy." |
| Explain an error | "What does `TypeError: 'NoneType' object is not subscriptable` mean?" |
| Check your understanding | "Here's how I think a `for` loop works: ... Is that right?" |
| Get unstuck, step by step | `/hint I don't know how to keep the menu running after each action` |
| Review your code | `/review-project`, or "What would you improve in this function, without rewriting it?" |
| Quiz yourself | `/quiz` |
| Compare after trying | "I solved exercise 3 like this: ... How else could it be done?" |

### Ask good questions

A good question includes:

1. **Goal**: what you're trying to do.
2. **What you tried**: code or steps.
3. **What happened**: the exact error or output.
4. **What you expected.**

> ❌ "my code doesn't work"
> ✅ "I want to print the total of my expenses. My loop adds each amount to `total`, but it prints `0`. Here's the loop: ... I expected `45.5`."

Often, writing a good question solves the problem by itself. That's called "rubber duck debugging".

### Verify everything

AI can be confidently wrong: invented functions, outdated syntax, subtle bugs. Protect yourself:

- **Run** code before trusting it.
- **Check** official documentation for anything important.
- **Ask** "how do you know?" or "what would prove this wrong?"

### Privacy and safety

- Don't paste secrets (passwords, API keys, private data) into any AI tool.
- Code you share may be stored by the provider. Read your tool's policy.

## Exercise

1. Ask your AI mentor to explain "what a variable is" in three different ways (analogy, code, diagram in text). Which one clicked for you?
2. Ask it to write your whole Level 00 project. Watch it refuse and offer a hint instead. That's the system working.
3. Write a short reflection in your notes: *How will I use AI while learning? What will I never ask it to do?* You'll need this for the project.

## Check your understanding

1. Why can't you learn programming just by reading AI-written code?
2. Rewrite this question to be good: "python error help".
3. Name two ways to check whether an AI answer is correct.

## Further reading

- [docs/learning-with-ai.md](../../../docs/learning-with-ai.md)
