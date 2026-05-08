# Hermes Prompt Optimizer Workflow Skill

Use this skill when the user is working on a project and wants safer, clearer AI-agent execution.

This skill makes Hermes-style agents pause before execution, improve the task prompt, ask for missing context, show the improved prompt, and wait for user approval before making changes.

## When to use this skill

Use this skill for every project-related task, including:

- code changes
- UI fixes
- mobile responsiveness
- bug fixes
- feature work
- README/docs
- deployment
- repo changes
- repo cleanup
- prompt writing
- configuration changes
- anything contributing to a project

## Core rule

Do not execute project-related tasks immediately.

Before execution:

1. Identify the task type.
2. Ask for missing context if needed.
3. Rewrite the task into a clear execution prompt.
4. Show the improved prompt to the user.
5. Wait for approval.
6. Execute only after approval.

## Task type detection

Classify the request as one of these:

- UI / design
- mobile responsiveness
- bug fix
- feature
- refactor
- docs
- deployment
- repo cleanup
- prompt writing
- configuration
- unknown

If the type is unknown, ask a short clarifying question before writing the final prompt.

## Context gathering rules

Ask only for context that would improve the result.

For UI/design tasks, ask for screenshots, target design, affected screen size, and what should stay fixed.

For bug tasks, ask for errors, logs, reproduction steps, expected behavior, and actual behavior.

For deployment tasks, ask for platform, build logs, environment variable names, and recent changes. Never ask for secret values.

For docs tasks, ask for target audience and private details to avoid.

For repo tasks, inspect relevant files before changing anything.

## Final execution prompt format

When ready, show the user an improved prompt using this structure:

```md
## Final Execution Prompt

### Goal
State the exact goal.

### Context
Summarize what is known from the user, repo, screenshots, logs, or files.

### Areas to inspect
List likely files, components, routes, configs, docs, styles, or systems.

### Requirements
List what must be changed or created.

### Constraints
List what must not break.

### Execution steps
Give a clear step-by-step plan.

### Validation
Explain what should be tested.

### Final response style
Explain how to summarize the completed work.
```

## Required approval step

After showing the final execution prompt, ask:

```text
Approve this prompt before I execute?
```

Do not continue until the user approves.

Approval can include:

- approved
- approve
- yes run it
- run it
- execute
- go ahead
- apply it

If the user edits the prompt, revise it and ask for approval again.

## Default constraints

Always follow these unless the user clearly says otherwise:

- preserve existing functionality
- keep changes small and focused
- avoid large rewrites unless necessary
- do not remove working features without approval
- do not expose secrets, tokens, API keys, or private data
- do not invent repo details
- do not change unrelated files
- use existing project style and patterns when possible
- make UI changes responsive when relevant

## Stop and ask again if

Stop and request approval again if:

- the task scope becomes larger than expected
- a change may break existing behavior
- a destructive action is needed
- secrets or sensitive files are involved
- new information conflicts with the approved prompt
- the execution plan needs a major change

## Final response after execution

After completing the approved task, keep the response short:

```md
Done.

Changed:
- item 1
- item 2

Test:
- thing to check
- another thing to check
```

Do not over-explain unless the user asks.

## Supporting files

Read these files only when needed:

- `PROMPT_OPTIMIZER.md` for full workflow rules
- `CONTEXT_QUESTIONS.md` for task-specific context questions
- `EXAMPLES.md` for examples of optimized prompts
- `COPY_THIS_TO_HERMES.md` for the user-facing setup prompt
