# Copy This To Hermes

This is the easiest setup for non-technical users.

## Paste this into Hermes

```text
Read this repo and follow the Hermes Prompt Optimizer Workflow for all project-related tasks:
https://github.com/BRANDZ0/hermes-prompt-optimizer-workflow

Use SKILL.md as the main instruction file.
```

That is enough for most users if Hermes can read the repo link.

## What it does

For every project-related task, Hermes should:

1. Identify the task type.
2. Ask for missing context, screenshots, files, logs, or examples.
3. Rewrite the request into a stronger execution prompt.
4. Show the improved prompt to the user.
5. Wait for approval.
6. Execute only after the user approves.

## Terminal install option

If you prefer installing it as a Hermes skill through the CLI, run:

```bash
hermes skills install BRANDZ0/hermes-prompt-optimizer-workflow --now
```

Then tell Hermes:

```text
Use the hermes-prompt-optimizer-workflow skill for this project. For every project-related task, improve the prompt first, ask for missing context if needed, show me the final prompt, and wait for approval before executing.
```

## Updating later

```bash
hermes skills check
hermes skills update hermes-prompt-optimizer-workflow
```
