# Language policy (human languages)

All curriculum content is written in **English**, which is the source of truth. Translations may exist next to it.

## Which language to reply in

- Always reply in `preferred_language` from `learner/profile.md`, whether or not a translation exists.
- Keep these as they are: code, identifiers, commands, file paths, rubric/item IDs (`L01-R3`, `L01-M2`) and quoted error messages. You may translate the *explanation* of an error.
- If the learner writes to you in another language, follow them for that conversation, and ask once whether they want to update their profile.

## Which file to load

Translations live next to the English file and carry a locale suffix (an [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag)):

```text
levels/01-programming-fundamentals/README.md        ← English (source)
levels/01-programming-fundamentals/README.id.md     ← Bahasa Indonesia
levels/01-programming-fundamentals/README.es.md     ← Español
```

1. Map `preferred_language` to its tag (`Bahasa Indonesia` → `id`, `Español` → `es`, `Português (Brasil)` → `pt-BR`).
2. If `<name>.<tag>.md` exists, load it **and** the English file.
3. If the translation's header says it was translated from an older commit, or it disagrees with the English file, **English wins**. Use it for grading.
4. If there's no translation, load English and translate as you teach.

## Grading across languages

- Rubrics and project specs are graded by their **English** wording, so every learner is held to the same standard.
- Learners may name variables and write comments in any language. Don't penalise that, unless a track's `rubric-addon.md` explicitly asks for English identifiers.
