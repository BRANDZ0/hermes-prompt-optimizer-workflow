# Examples

These examples show how Hermes should turn project requests into structured, approval-based execution prompts.

## Example 1: Mobile UI fix

User says:

```text
fix this mobile ui the buttons look funny
```

Hermes should respond:

```text
I will optimize this before executing.

Task type: Mobile responsiveness / UI

Please send a screenshot of the current mobile UI and tell me the screen size or device where the buttons look wrong. If you have a target design, send that too.
```

Improved prompt:

```text
Goal: Fix the mobile button layout so buttons look clean, aligned, readable, and properly sized.
Context: The user reported the mobile buttons look wrong. Use the screenshot as the current state.
Areas to inspect: button components, mobile layout, CSS/Tailwind classes, responsive breakpoints, parent containers.
Requirements: Fix spacing, sizing, alignment, and touch target size. Test common mobile widths.
Constraints: Preserve existing functionality. Do not redesign unrelated sections. Keep changes focused.
Validation: Confirm buttons look correct on mobile and still work when clicked.
```

Hermes should then ask:

```text
Approve this prompt before I execute?
```

## Example 2: Bug fix

User says:

```text
login is broken fix it
```

Hermes should respond:

```text
I will optimize this before executing.

Task type: Bug fix

Please send the error message, console logs, and the exact steps to reproduce the login issue. Also tell me what should happen after login.
```

Improved prompt:

```text
Goal: Fix the login flow so users can sign in successfully and reach the correct post-login state.
Context: The user reported login is broken. Use logs and reproduction steps to find the root cause.
Areas to inspect: auth components, login button/form, API calls, callback handling, redirects, environment variable usage, session state.
Requirements: Reproduce the issue, identify the root cause, apply the smallest safe fix, and preserve logged-in/logged-out behavior.
Constraints: Do not replace the auth system. Do not expose secrets. Do not change unrelated routes or UI.
Validation: Confirm successful login, failed login, and logout behavior.
```

## Example 3: Deployment issue

User says:

```text
vercel deploy failed fix it
```

Hermes should respond:

```text
I will optimize this before executing.

Task type: Deployment

Please send the Vercel build error logs, framework used, and recent changes. Do not send secret values.
```

Improved prompt:

```text
Goal: Fix the Vercel deployment failure while preserving local development behavior.
Context: The user reported a failed Vercel deploy. Use the build logs and project config to identify the cause.
Areas to inspect: package.json, build command, framework config, env var names, import paths, TypeScript/lint errors, Vercel config.
Requirements: Identify the failure, apply the smallest safe fix, and keep local behavior intact.
Constraints: Do not change deployment platform. Do not remove important checks unless approved. Do not expose secrets.
Validation: Confirm the project builds successfully and list any Vercel settings the user must check.
```
