# Memory

## User Preferences

- **Commit approval**: Always present the full commit commands to the user for physical review BEFORE executing them. Do not run jj commit / git commit until the user explicitly approves.
- **Versioning**: Every plan must start with a version bump per notes/README.md "Versioning during development". Get user approval on single-step vs multi-step approach before starting.
- **Pre-commit checklist**: Before committing, run: tests, clippy, fmt, install the app, then retest.

## Key Files

- notes/README.md — contains versioning workflow, todo format rules
- notes/todo.md — near-term task tracking
- notes/chores-01.md — chore details and reference links
- CLAUDE.md — dual repo commit/push workflow
