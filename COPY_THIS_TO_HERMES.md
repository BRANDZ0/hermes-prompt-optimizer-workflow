# Copy This To Hermes

Use this only if you do not install the skill through the Hermes CLI.

## Best install method

Run this in your terminal:

```bash
hermes skills install BRANDZ0/hermes-prompt-optimizer-workflow --now
```

Then tell Hermes:

```text
Use the hermes-prompt-optimizer-workflow skill for this project. For every project-related task, improve the prompt first, ask for missing context if needed, show me the final prompt, and wait for approval before executing.
```

## Paste-only fallback

If you do not want to use the CLI, paste this into Hermes:

```text
Read this repo and follow the Hermes Prompt Optimizer Workflow:
https://github.com/BRANDZ0/hermes-prompt-optimizer-workflow

Use SKILL.md as the main instruction file.

Before every new project session, refresh this workflow by re-reading the latest repo files, especially SKILL.md and README.md.

For every project-related task I give you, do not execute immediately.

First:

1. Identify the task type.
2. Decide what context is missing.
3. Ask for screenshots, files, logs, examples, repo context, or design references if needed.
4. Rewrite my request into a clear, detailed execution prompt.
5. Show me the improved prompt.
6. Wait for my approval.
7. Only execute after I approve.

This applies to coding tasks, UI fixes, mobile responsiveness, bug fixes, feature work, README/docs, deployment, repo changes, prompt writing, and anything contributing to my project.

Always preserve existing functionality unless I clearly ask to change it.

For UI tasks, ask for screenshots, current behavior, target behavior, and affected screen size.

For bug tasks, ask for errors, logs, steps to reproduce, expected behavior, and actual behavior.

For repo tasks, inspect relevant files before editing.

Keep prompts structured, detailed, and practical.

Never skip the pre-approval step unless I explicitly say to bypass approval for that specific task.
```

## Updating later

```bash
hermes skills check
hermes skills update hermes-prompt-optimizer-workflow
```
