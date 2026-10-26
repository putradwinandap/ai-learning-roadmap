# Track policy (programming languages)

Every level has a **language-agnostic core** (concepts, project spec, rubric). Some levels also have **tracks**: language-specific material in `levels/NN-*/tracks/<language>/`.

## Track folder names

Lowercase, no spaces: `python`, `javascript`, `typescript`, `go`, `java`, `csharp`, `php`, `rust`, `kotlin`, `ruby`, ... Map the learner's `programming_language` value to this form (`C#` → `csharp`, `Node.js` → `javascript`).

## When a track exists

Load:
- `tracks/<language>/README.md`: setup and tooling for this level (runtime version, package manager, formatter, linter, test runner).
- `tracks/<language>/lessons/<same-name-as-core>.md`: syntax and idioms for the matching core lesson. A track only includes lessons where the language makes a difference. If one is missing, teach from the core lesson.
- `tracks/<language>/rubric-addon.md`: extra criteria (`LNN-<LANG>-R*`, e.g. `L01-PY-R1`). These are **scored and counted** in the rubric average like core criteria.

## When no track exists

The learner can still use their language. Then you:
- Teach from the core lessons and show examples in their language, using your own knowledge of its idioms and current best practices.
- Recommend the language's standard tooling (official formatter, common linter, standard test runner) appropriate for the level.
- Grade with the core rubric only. Don't invent add-on criteria. You may still comment on idioms under the core "readability" criterion.
- Mention once that no track exists yet and that they could contribute one ([`docs/adding-a-track.md`](../docs/adding-a-track.md)).

## Switching languages

- A learner may pick a different language for each level. `progress.md` records `programming_language` per level.
- Within a level, the project should be in one language, except where the level says otherwise (for example, browser JavaScript plus a backend language in Levels 03 and 05).
- If they switch mid-level, the project is reviewed in the new language and earlier reviews are kept for reference.
