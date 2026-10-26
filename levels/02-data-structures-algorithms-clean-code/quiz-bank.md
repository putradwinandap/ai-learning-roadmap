# Level 02 quiz bank

See [ai/quiz-protocol.md](../../ai/quiz-protocol.md). Snippets go in the learner's language.

## 1. Complexity
- What does O(n) mean? Order these: O(n²), O(1), O(n log n), O(log n), O(n).
- *Predict:* the Big-O of a nested loop over the same list; of a loop that halves `n` each step.

## 2. Data structures
- Array vs. hash map vs. set: which one for "does this ISBN exist?" Why?
- Stack vs. queue: one real use of each.
- When is a linked list better than an array?

## 3. Recursion
- What's a base case? What happens without one?
- *Predict:* output of a small recursive function (e.g. factorial or countdown).
- *Spot the bug:* a recursive function whose recursive call doesn't move toward the base case.

## 4. Searching & sorting
- Binary search's precondition, and its complexity.
- Explain merge sort in plain words. Its complexity?
- What does it mean for a sort to be stable? When does it matter?

## 5. Trees & graphs
- What makes a binary search tree a *search* tree?
- DFS vs. BFS: which finds the shortest path in an unweighted graph?

## 6. Design
- Encapsulation: what and why?
- Composition vs. inheritance: give an example where composition is better.
- What is a pure function, and why does it make testing easier?

## 7. Clean code
- *Spot the smell:* a long function doing validation, calculation and printing.
- DRY vs. premature abstraction: when is duplication acceptable?
- Name one SOLID principle and explain it with an example.

## 8. Testing
- Arrange-act-assert: explain with an example.
- Why should tests not depend on the current date? How do you fix that?
- Red-green-refactor: describe the cycle.
- *Apply:* list 4 test cases for "borrow a book".
