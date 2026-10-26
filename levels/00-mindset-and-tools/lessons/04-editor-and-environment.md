# 04: Editor and environment

> **Track lesson available.** Language-specific install steps are in `tracks/<your-language>/lessons/04-editor-and-environment.md` ([Python](../tracks/python/lessons/04-editor-and-environment.md), [JavaScript](../tracks/javascript/lessons/04-editor-and-environment.md)).

## Why this matters

To write code you need an **editor**, and to run it you need a **runtime** (or compiler) for your language. A good setup removes friction: formatting happens automatically, errors show up as you type, and the terminal is one shortcut away.

## Key ideas

### Choosing an editor

Any modern editor works. If you have no preference, use **Visual Studio Code** (free, all platforms, huge extension ecosystem). Alternatives: JetBrains IDEs (PyCharm, WebStorm, ...), Zed, Neovim.

Learn these editor skills early:

| Skill | VS Code shortcut (Windows/Linux · macOS) |
|---|---|
| Open the command palette | `Ctrl+Shift+P` · `Cmd+Shift+P` |
| Open a file by name | `Ctrl+P` · `Cmd+P` |
| Toggle the integrated terminal | ``Ctrl+` `` · ``Cmd+` `` |
| Find in all files | `Ctrl+Shift+F` · `Cmd+Shift+F` |
| Format the document | `Shift+Alt+F` · `Shift+Option+F` |
| Multi-cursor | `Alt+Click` · `Option+Click` |

Open the **whole folder** (`File → Open Folder`, or `code .` in the terminal), not single files.

### Runtimes, compilers, interpreters

- **Interpreted** languages (Python, JavaScript/Node.js, PHP, Ruby) run source code directly via a runtime.
- **Compiled** languages (Go, Rust, C#, Java) are first translated into an executable or bytecode.

Either way, install the language from its **official source** or a well-known version manager, and check it works with `--version`.

### Version managers

Projects often need specific language versions. Version managers let you install several side by side: `pyenv` or `uv` (Python), `nvm` or `fnm` (Node.js), `sdkman` (Java). You don't need one on day one, but know they exist.

### Formatter and linter

- A **formatter** rewrites your code into a consistent style (spaces, line breaks). You stop thinking about it.
- A **linter** warns about likely bugs and bad patterns.

Turn on **format on save** in your editor. Your track tells you which tools to use.

### AI assistant in the editor

You'll use an AI assistant with this repo. Two settings matter:

1. Make sure it can read the repo's `AGENTS.md` / `CLAUDE.md` (most tools do this automatically).
2. **Turn off inline code autocompletion while working on graded projects** (or at least in `learner/`). Autocomplete writing your code defeats the purpose. Chatting with a mentor is fine.

## Exercise

1. Install an editor and open this repo folder in it.
2. Install your programming language using your track's instructions, and verify with `--version` in the editor's integrated terminal.
3. Install the formatter your track recommends and enable format on save.
4. Write the versions you installed in your `notes.md`.

## Check your understanding

1. What's the difference between an editor and a runtime?
2. Why open the whole folder instead of a single file?
3. What does a formatter do, and how is it different from a linter?

## Further reading

- [VS Code: Getting started](https://code.visualstudio.com/docs/getstarted/getting-started)
- [The Missing Semester: Editors (MIT)](https://missing.csail.mit.edu/2020/editors/)
