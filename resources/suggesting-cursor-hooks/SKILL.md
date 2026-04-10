---
name: suggesting-cursor-hooks
description: Analyze a project's workflow and suggest Cursor hooks (.cursor/hooks.json) that automate repetitive checks and validations around agent actions.
user-invocable: true
---

# Suggesting Cursor Hooks

Analyze a project and suggest hooks that automate quality checks around agent actions.

## What Are Cursor Hooks?

Hooks are scripts that run automatically at specific points in the agent's lifecycle:

| Event | When it fires |
|-------|---------------|
| `afterFileEdit` | After the agent edits a file |
| `beforeShellExecution` | Before the agent runs a shell command |
| `afterShellExecution` | After a shell command completes |
| `stop` | When the agent finishes its turn |

Hooks are defined in `.cursor/hooks.json` and scripts live in `.cursor/hooks/`.

## Workflow

### 1. Analyze the Project

Look for:

**Linting & Formatting**
- Does the project use ESLint, Prettier, Biome, Ruff?
- Are there pre-commit hooks already (husky, lint-staged)?
- → Suggest: `afterFileEdit` hook to lint changed files

**Type Checking**
- Is it a TypeScript project?
- → Suggest: `afterFileEdit` hook to run `tsc --noEmit` on `.ts`/`.tsx` files

**Testing**
- What test runner? (Jest, Vitest, Pytest)
- Are tests co-located or in a separate directory?
- → Suggest: `afterFileEdit` hook to run related tests when source files change

**Build Validation**
- Is there a build step that frequently breaks?
- → Suggest: `stop` hook to run a quick build check before the agent finishes

**Security**
- Are there secrets/env files that shouldn't be committed?
- → Suggest: `beforeShellExecution` hook to block `git add .env` or similar

### 2. Generate Hook Configuration

```json
{
  "hooks": [
    {
      "event": "afterFileEdit",
      "script": ".cursor/hooks/lint.sh",
      "pattern": "**/*.{ts,tsx,js,jsx}"
    },
    {
      "event": "afterFileEdit",
      "script": ".cursor/hooks/typecheck.sh",
      "pattern": "**/*.{ts,tsx}"
    },
    {
      "event": "beforeShellExecution",
      "script": ".cursor/hooks/guard-secrets.sh"
    },
    {
      "event": "stop",
      "script": ".cursor/hooks/final-check.sh"
    }
  ]
}
```

### 3. Create Hook Scripts

Each script should be:
- **Fast** — under 5 seconds, or the agent feels slow
- **Non-blocking** — exit 0 even on failure (report errors via stdout, don't block the agent)
- **Focused** — one check per script

Example `lint.sh`:
```bash
#!/bin/bash
npx eslint --fix "$1" 2>&1 | tail -5
exit 0
```

Example `guard-secrets.sh`:
```bash
#!/bin/bash
if echo "$1" | grep -qE '\.(env|pem|key)'; then
  echo "WARNING: Attempting to interact with a secrets file: $1"
fi
exit 0
```

### 4. Present to User

```
Suggested Cursor Hooks:

1. afterFileEdit → lint.sh
   Auto-lint TypeScript files after every edit
   
2. afterFileEdit → typecheck.sh
   Run tsc after .ts/.tsx edits to catch type errors early

3. beforeShellExecution → guard-secrets.sh
   Warn before touching .env, .pem, or .key files

4. stop → final-check.sh
   Run tests and type-check before the agent finishes

Want me to create these?
```

## Tips

- Check for existing `.cursor/hooks.json` — don't overwrite
- Hook scripts must be executable (`chmod +x`)
- Keep hooks fast — slow hooks make the agent feel unresponsive
- The `pattern` field uses glob syntax to scope which files trigger the hook
- Hooks that exit non-zero will block the agent action — use this sparingly
