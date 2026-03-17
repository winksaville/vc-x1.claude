---
name: Finalize must be the absolute last action
description: Nothing should happen after finalize — no memory writes, no output beyond the status line. Re-run finalize if any work follows.
type: feedback
---

Finalize must be the very last thing in a session. After running it, produce no output at all — the Bash tool already displays the finalize output.

**Why:** Any work after finalize (memory writes, tool calls, text output) generates session data that misses the squash window. Even echoing the finalize output creates a ~7 second trailing write.

**How to apply:** Do all memory writes, file edits, and other work BEFORE finalize. Then run finalize and stop — no text, no tool calls. If something unavoidably happens after finalize, run finalize again.
