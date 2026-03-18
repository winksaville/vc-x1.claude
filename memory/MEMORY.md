# Memory

## User Preferences

- **Commit approval**: Always present the full commit commands to the user for physical review BEFORE executing them. Do not run jj commit / git commit until the user explicitly approves.
- **Versioning**: Every plan must start with a version bump per notes/README.md "Versioning during development". Get user approval on single-step vs multi-step approach before starting.
- **Pre-commit checklist**: Before committing, run: tests, clippy, fmt, install the app, then retest.

## Feedback

- [Always include ochid trailer in commits](feedback_ochid_trailer.md)
- [Always commit .claude repo before finalize](feedback_claude_commit_before_finalize.md)
- [Skip .claude push before finalize — finalize handles it](feedback_no_claude_push.md)
- [Finalize must be absolute last action — only status line after](feedback_finalize_last.md)
- [Use --ignore-immutable for late squash after push](feedback_squash_ignore_immutable.md)
- [Use vc-x1 chid to retrieve changeIDs, not jj log](feedback_use_chid.md)
- [Recognize when stuck — 5+ min thinking on simple task means stuck](feedback_stuck_detection.md)
- [No --allow-new flag for jj git push](feedback_jj_no_allow_new.md)
- [No text output after finalize — trailing writes miss squash window](feedback_no_finalize_echo.md)
- [Ask for clarification on ambiguous input instead of spinning](feedback_ask_on_ambiguity.md)
- ["finalize steps" triggers full session-end workflow](feedback_finalize_steps.md)

## Lessons Learned

- **Avoid duplicate commits in .claude repo**: Committing the bot session repo multiple times in one session can create duplicate-titled commits with other session commits interleaved, making squashing non-trivial. Prefer a single commit to .claude at session end.
- **ochid trailers need updating after squash**: When squashing changes the target commit in .claude, the ochid reference in the app repo must be updated to point at the correct changeID.
- **Don't modify .claude repo programmatically mid-session**: Session data updates continuously, so bot-initiated changes to .claude can create circular modifications.

## Key Files

- notes/README.md — contains versioning workflow, todo format rules
- notes/todo.md — near-term task tracking
- notes/chores-01.md — chore details and reference links
- CLAUDE.md — dual repo commit/push workflow
