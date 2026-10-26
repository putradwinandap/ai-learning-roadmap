# 04 (Python): Editor and environment

Core lesson: [04: Editor and environment](../../../lessons/04-editor-and-environment.md)

## Install Python

**Windows**
1. Download the latest Python 3 installer from [python.org/downloads](https://www.python.org/downloads/).
2. In the installer, **tick "Add python.exe to PATH"**, then install.
3. Open a *new* terminal: `python --version`.

**macOS**
- With [Homebrew](https://brew.sh): `brew install python`, then `python3 --version`.
- Or use the python.org installer.

**Linux**
- Usually preinstalled: `python3 --version`. If it's older than 3.12, install a newer one with your package manager or `uv python install`.

> `python` vs `python3`: on macOS/Linux, `python` may not exist or may point to an old version. Use whichever command prints 3.12+, and write that one in your README.

## Install Ruff

```bash
python -m pip install --user ruff
ruff --version
```

(If you use `uv`: `uv tool install ruff`.)

Try it:

```bash
ruff format hello.py    # reformat the file
ruff check hello.py     # look for problems
```

## VS Code setup

1. Install the extensions **Python** (Microsoft) and **Ruff** (Astral).
2. Open settings (JSON) and add:
   ```json
   "[python]": {
     "editor.defaultFormatter": "charliermarsh.ruff",
     "editor.formatOnSave": true
   }
   ```
3. `Ctrl/Cmd+Shift+P` → "Python: Select Interpreter" → pick your 3.12+ install.

## Check

- `python --version` (or `python3`) prints 3.12 or newer.
- `ruff --version` works.
- Saving a badly indented `.py` file reformats it.
