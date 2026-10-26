# Level 01 rubric add-on: Python

These criteria are added to the [core rubric](../../rubric.md) and count toward the average.

| ID | Criterion | 3 = meets | 4 = exceeds | Typical 1–2 signs |
|---|---|---|---|---|
| L01-PY-R1 | **Pythonic idioms** | Iterates directly over collections (with `enumerate` when an index is needed), uses `with` or `pathlib` for files, `dict.get` where a key may be missing, f-strings with format specs, specific `except` clauses. | Uses comprehensions where they improve clarity, `match` or a dispatch dict for the menu, type hints on function signatures, `encoding="utf-8"` everywhere. | `for i in range(len(x))` everywhere, manual `open`/`close`, bare `except:`, string concatenation with `str()`. |
| L01-PY-R2 | **Tooling & entry point** | `ruff format --check .` and `ruff check .` pass, there's an `if __name__ == "__main__":` guard, and no third-party runtime dependencies. | Ruff configured in `pyproject.toml`. The README states the exact Python version used. | Formatter or linter not applied, code runs on import, unexplained dependencies. |
