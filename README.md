# Sarros Codex Cursor Agent Pack

Agent instructions and Cursor rules for Sarros Workspace repositories (SimPRO, quote intelligence, internal tooling).

## Install

### Cursor rules (project)

Copy `AGENTS.md` to your repository root and copy `.cursor/rules/*.mdc` into your project `.cursor/rules/` folder.

### Cursor rules (user-wide)

On Windows, copy the `.mdc` files to `C:\Users\reill\.cursor\rules`. Cursor loads `AGENTS.md` from the workspace root when that folder is open in the editor.

## Contents

- `AGENTS.md` — agent behaviour and Sarros context
- `.cursor/rules/` — coding standards, workflows, PR review, SimPRO domain rules
