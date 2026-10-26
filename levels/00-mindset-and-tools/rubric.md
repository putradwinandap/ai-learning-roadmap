# Level 00 rubric

Scale: 0 missing · 1 attempted but broken · 2 partial · **3 meets** · 4 exceeds. See [ai/review-protocol.md](../../ai/review-protocol.md).

Track add-on criteria are in `tracks/<language>/rubric-addon.md` and count toward the average.

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L00-R1 | **Working program** | Runs with the README's commands, asks for a name, prints a personalised greeting with a computed detail. | Also handles empty input gracefully and the output is polished (clear prompts, tidy formatting). | Crashes, wrong output, greeting not personalised, no computed detail. |
| L00-R2 | **Run instructions** | README states what the program does, the language version, and copy-pasteable run commands that work. | A newcomer could run it without any prior knowledge: prerequisites, example output, troubleshooting tip. | Missing or wrong commands. Assumes knowledge not written down. |
| L00-R3 | **Git hygiene** | ≥ 3 focused commits with clear imperative messages, pushed. No junk or secrets committed. | Each commit is one logical step. A `.gitignore` is present. History reads like a story. | Single "initial commit" dump, messages like `update`/`fix`, junk files tracked, not pushed. |
| L00-R4 | **Learning plan & AI reflection** | Concrete weekly plan (days, times, durations). The reflection names specific good uses of AI and things to avoid. | Plan is realistic for the learner's stated hours and includes a strategy for being stuck. The reflection shows real insight. | Vague ("I'll study when I can"), missing parts, copy-pasted generic text. |
| L00-R5 | **Readability** | Clear variable names, consistent formatting, no dead or commented-out code. | Tiny, well-named pieces. A comment explains any non-obvious choice. | Names like `x`, `a1`. Inconsistent indentation. Leftover experiments. |
