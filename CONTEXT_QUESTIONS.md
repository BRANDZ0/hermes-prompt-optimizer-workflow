# Context Questions

Hermes should ask for missing context only when it will improve the result.

Do not ask every question in this file. Pick the questions that match the task.

## UI and design tasks

Ask for:

- screenshot of the current UI
- screenshot, mockup, or description of the target design
- device or screen size where it looks wrong
- whether desktop, tablet, or mobile is the priority
- exact issue: spacing, size, alignment, colors, overflow, responsiveness, layering, or readability
- whether the change should match an existing theme or component style

Useful question:

```text
Send a screenshot of the current UI and tell me the screen size where it breaks. If you have a target design, send that too.
```

## Mobile responsiveness tasks

Ask for:

- mobile screenshot
- desktop screenshot if layout differs
- affected viewport width
- whether the layout should stack, scale, crop, scroll, or stay fixed
- elements that must not move
- elements that can resize

Useful question:

```text
Send the mobile screenshot and tell me what should stay fixed, what can resize, and what screen width you are testing on.
```

## Bug tasks

Ask for:

- exact error message
- console logs
- network logs if API-related
- steps to reproduce
- expected behavior
- actual behavior
- when it started happening
- recent files changed

Useful question:

```text
Send the error message, console logs, and the exact steps to reproduce the bug.
```

## Feature tasks

Ask for:

- what the feature should do
- who uses it
- where it appears
- required user flow
- acceptance criteria
- edge cases
- permissions or roles
- data source or API details

Useful question:

```text
Describe the exact user flow and where this feature should appear. Include any required states, buttons, data, or edge cases.
```

## Refactor tasks

Ask for:

- goal of the refactor
- files or areas involved
- whether behavior must stay identical
- whether tests exist
- whether breaking changes are allowed
- preferred structure or pattern

Useful question:

```text
Should this refactor preserve behavior exactly, or are small behavior changes allowed if they improve the structure?
```

## Deployment tasks

Ask for:

- platform: Vercel, Railway, Netlify, VPS, AWS, etc.
- build command
- error logs
- environment variable names, not secret values
- recent changes
- whether it works locally
- runtime or framework version

Useful question:

```text
Send the deployment platform, build logs, and environment variable names involved. Do not send secret values.
```

## README and docs tasks

Ask for:

- target audience
- project purpose
- setup steps
- install commands
- environment variables needed
- screenshots or demo links
- features to highlight
- private details to avoid

Useful question:

```text
Who is the README for: users, developers, recruiters, clients, or contributors?
```

## Repo cleanup tasks

Ask for:

- what should be kept
- what should be removed
- whether old files can be deleted
- whether file names can change
- whether imports/routes depend on the current structure
- whether a branch or PR is required

Useful question:

```text
Should I only organize files, or am I allowed to delete unused files too?
```

## Prompt writing tasks

Ask for:

- target agent or model
- task goal
- desired tone
- context the agent should know
- output format
- constraints
- examples of good or bad output

Useful question:

```text
What agent/model is this prompt for, and should it be short, strict, detailed, or beginner-friendly?
```

## When not to ask questions

Do not ask for more context if:

- the task is already specific
- the missing detail can be safely inferred
- the user asked for a simple text rewrite
- the user gave enough screenshots/logs/files already
- asking would slow down a small obvious fix

Instead, create the optimized prompt and ask for approval.
