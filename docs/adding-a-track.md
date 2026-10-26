# Adding a language track

A **track** teaches a level's core concepts in one specific programming language: setup, syntax, idioms, tooling and language-specific grading. See [ai/track-policy.md](../ai/track-policy.md) for how the AI uses tracks.

## Folder layout

```text
levels/NN-level-name/tracks/<language>/
├── README.md          # Versions, tools, project layout, list of track lessons, references
├── lessons/
│   └── <same filename as the core lesson>.md
└── rubric-addon.md    # Optional but recommended
```

Folder names are lowercase with no spaces: `python`, `javascript`, `typescript`, `go`, `java`, `csharp`, `php`, `rust`, `kotlin`, `ruby`, ...

## Track README checklist

- [ ] Language/runtime version
- [ ] Formatter, linter, test runner (if the level needs one), debugger
- [ ] Recommended project layout for this level's project
- [ ] Table linking every track lesson
- [ ] Link to the rubric add-on
- [ ] Official references

## Track lessons

- **Mirror the core filenames exactly** (`04-loops.md` → `tracks/go/lessons/04-loops.md`), so the AI can pair them.
- Start with `Core lesson: [link]`. Don't repeat the concept explanation. Show **how it looks in this language** and the language's idioms and gotchas.
- Use examples from a **different domain than the level's project**, so lessons don't hand out project solutions.
- Only add lessons where the language makes a real difference. Skipped lessons fall back to the core.

## Rubric add-on

- 1–3 criteria, IDs `LNN-<LANG>-R<n>` (e.g. `L01-GO-R1`). Use a short uppercase code: `PY`, `JS`, `TS`, `GO`, `JAVA`, `CS`, `PHP`, `RS`, `KT`, `RB`.
- Same columns as the core rubric: criterion, 3 = meets, 4 = exceeds, typical 1–2 signs.
- Grade idioms and tooling, not things the core rubric already covers.
- Keep it fair for the level. Don't require Level 06 practices in Level 01.

## Register the track

1. Update the level's `tracks/README.md` table.
2. Update the **Programming languages** table in the root `README.md`.
3. Open a PR. Ideally, someone who knows the language reviews it.

## Quality bar

- Every code example runs on the stated version.
- Commands work on Windows, macOS and Linux (or the differences are noted).
- No third-party libraries where the level's rules require the standard library.
