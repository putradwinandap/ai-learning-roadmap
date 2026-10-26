# 04 (JavaScript): Editor and environment

Core lesson: [04: Editor and environment](../../../lessons/04-editor-and-environment.md)

## Install Node.js

**All platforms (simplest):** download the **LTS** installer from [nodejs.org](https://nodejs.org/), install it, and open a *new* terminal.

**With a version manager (recommended if you're comfortable):**
```bash
# fnm (Windows, macOS, Linux). Install instructions: https://github.com/Schniz/fnm
fnm install --lts
fnm use lts-latest
```

Check:
```bash
node --version    # v22.x or newer
npm --version     # npm comes with Node.js
```

## Install Prettier

For now, run it through `npx` (no global install needed):

```bash
npx prettier --version
npx prettier --write hello.mjs    # reformat the file
```

## VS Code setup

1. Install the extension **Prettier - Code formatter**.
2. Open settings (JSON) and add:
   ```json
   "[javascript]": {
     "editor.defaultFormatter": "esbenp.prettier-vscode",
     "editor.formatOnSave": true
   }
   ```

## Check

- `node --version` prints v22 or newer.
- `npx prettier --version` works.
- Saving a badly formatted `.mjs` file reformats it.
