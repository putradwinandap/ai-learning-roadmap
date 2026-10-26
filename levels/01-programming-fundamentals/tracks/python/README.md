# Level 01: Python track

## Versions and tools

| What | Use |
|---|---|
| Python | 3.12 or newer |
| Formatter + linter | Ruff: `ruff format .` and `ruff check .` |
| Debugger | VS Code Python debugger (F5), or `breakpoint()` in code |
| Standard-library modules you'll use | `json`, `pathlib`, `datetime`, `sys` |

### Recommended project layout

```text
learner/level-01/project/
├── README.md
├── ledger.py          # or split: main.py, cli.py, logic.py, storage.py
└── pyproject.toml     # optional: Ruff config
```

Optional `pyproject.toml` to configure Ruff:

```toml
[tool.ruff]
line-length = 100

[tool.ruff.lint]
select = ["E", "F", "W", "I", "B", "UP"]
```

## Lessons

| # | Track lesson |
|---|---|
| 01 | [Values, variables and types](lessons/01-values-variables-and-types.md) |
| 02 | [Operators and expressions](lessons/02-operators-and-expressions.md) |
| 03 | [Conditionals](lessons/03-conditionals.md) |
| 04 | [Loops](lessons/04-loops.md) |
| 05 | [Functions](lessons/05-functions.md) |
| 06 | [Collections](lessons/06-collections.md) |
| 07 | [Strings and input/output](lessons/07-strings-and-input-output.md) |
| 08 | [Files and persistence](lessons/08-files-and-persistence.md) |
| 09 | [Errors and debugging](lessons/09-errors-and-debugging.md) |
| 10 | [Program structure](lessons/10-program-structure.md) |

## Grading add-on

[rubric-addon.md](rubric-addon.md)

## References

- [The Python Tutorial (official)](https://docs.python.org/3/tutorial/)
- [Python standard library](https://docs.python.org/3/library/)
