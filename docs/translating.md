# Translating the curriculum

English is the source of truth. Translations make the curriculum easier to read for everyone else. Learners can already *talk* to the AI in any language (see [ai/language-policy.md](../ai/language-policy.md)), so translations are a bonus, never a blocker.

## File naming

A translation sits **next to** its English source, with an [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag) before `.md`:

```text
levels/01-programming-fundamentals/lessons/04-loops.md       ← English source
levels/01-programming-fundamentals/lessons/04-loops.id.md    ← Bahasa Indonesia
levels/01-programming-fundamentals/lessons/04-loops.es.md    ← Español
levels/01-programming-fundamentals/lessons/04-loops.pt-BR.md ← Português (Brasil)
```

## Required header

Every translated file starts with:

```markdown
<!--
translation-of: levels/01-programming-fundamentals/lessons/04-loops.md
source-commit: <short hash of the English file's last commit when you translated it>
translator: <your GitHub username>
-->
```

Get the hash with:

```bash
git log -1 --format=%h -- levels/01-programming-fundamentals/lessons/04-loops.md
```

This lets anyone see whether a translation is outdated: if the English file has newer commits, the translation needs an update.

## What to translate, and what not to

| Translate | Keep as is |
|---|---|
| Explanations, headings, exercises, questions | Code, commands, file paths |
| Table text | IDs: `L01-M3`, `L01-R2`, `L01-PY-R1` |
| Link text | Link targets (point to the translated file if it exists, otherwise to English) |

Code comments inside examples may be translated if it helps learners. Keep identifiers in English.

## What to translate first

1. Root `README.md` → `README.<tag>.md`
2. `docs/how-to-use.md`
3. A level's `README.md`, `project.md`, then its lessons
4. Rubrics last. Grading always uses the English wording, so translated rubrics are for reading only.

`AGENTS.md` and `ai/` are instructions for the AI. Keep them in English only.

## Workflow

1. Open an issue "Translate Level NN to <language>" so others know you're on it.
2. Translate in small PRs (one level or a few lessons each).
3. Update the **Translations** table in the root README.
4. A second speaker of the language reviewing your PR is ideal.
