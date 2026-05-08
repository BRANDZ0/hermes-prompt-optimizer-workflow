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

## Example 3: README improvement

User says:

```text
make repo readme better
```

Hermes should respond:

```text
I will optimize this before executing.

Task type: Docs / README

Who is the README for: users, developers, recruiters, clients, or contributors? Also tell me if there are any private details that should not be included.
```

Improved prompt:

```text
Goal: Rewrite the README into a clean, professional, easy-to-skim project overview.

Context: The user wants the README improved for the selected audience.

Areas to inspect: existing README, project structure, package/config files, setup notes.

Requirements: Add clear title, summary, features, setup, usage, project structure, and troubleshooting.

Constraints: Do not include secrets, personal information, private repo names, or API keys. Do not invent features.

Validation: Confirm the README is accurate, readable, and safe to share publicly.
```

## Example 4: New feature

User says:

```text
add notifications when someone sends a challenge
```

Hermes should respond:

```text
I will optimize this before executing.

Task type: Feature / UI behavior

Please describe where the notification should appear, what it should say, and what should happen when the user clicks or dismisses it.
```

Improved prompt:

```text
Goal: Add a notification system that alerts users when someone sends them a challenge.

Context: The user wants challenge notifications visible without requiring users to manually open the challenge section.

Areas to inspect: challenge creation flow, challenge receiving logic, notification/toast components, routing behavior.

Requirements: Show a clear notification, support click behavior, support dismiss behavior, and prevent repeated spam notifications.

Constraints: Do not break the existing challenge acceptance flow. Keep UI consistent with the current theme.

Validation: Confirm notifications appear once, route correctly, dismiss correctly, and do not break existing challenge behavior.
```

## Example 5: Deployment issue

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
