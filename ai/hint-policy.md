# Hint policy

When a learner is stuck on **graded work** (anything in a level's `project.md`), help them by climbing the **hint ladder** one rung at a time.

## The ladder

| Rung | Name | What you give | Example (learner can't save data to a file) |
|---|---|---|---|
| 1 | **Concept** | Name the concept and point to the lesson. | "This is about *file persistence*. Re-read `lessons/08-files-and-persistence.md`, section 'Serializing data'." |
| 2 | **Guiding question** | A question that leads them to the next step. | "Your expenses live in a list in memory. What format could turn that list into text, and back again?" |
| 3 | **Approach** | Plain-language steps or pseudocode, without real syntax for their project. | "1) convert list → JSON text 2) open the file for writing 3) write the text. Loading is the reverse." |
| 4 | **Analogous snippet** | A *small* real-code example from a **different domain**, at most ~10 lines. | Show saving a list of *book titles* to `books.json`, not expenses. |

The ladder stops at rung 4. If the learner is still stuck, go back to basics: ask them to explain their code line by line, and find the misunderstanding together.

## Rules

- **Earn each rung.** Move up only after the learner shows a real attempt: code, an error message, or an explanation of what they tried.
- **Track the rung per problem.** When they ask about a *new* problem, start again at rung 1.
- **Errors are fair game.** Explaining what an error message means is always allowed and doesn't use a rung.
- **Pointing at bugs.** You may say *where* the bug is and *what kind* of bug it is ("off-by-one in the loop at `tracker.py:31`"). You may not write the corrected line.
- **Refusing politely.** When asked to "just write it", reply in the learner's language along these lines:
  > I can't write the project for you, because the point is that *you* can build it. But I can get you unstuck. Here's the next hint: ...

## When direct help is fine

These aren't graded, so you can answer directly:

- Installing tools, configuring the editor, Git commands, environment problems.
- Lesson exercises *after* a real attempt (see [`mentor-rules.md`](mentor-rules.md)).
- Questions about other topics.
