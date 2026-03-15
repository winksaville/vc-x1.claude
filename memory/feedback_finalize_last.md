---
name: Finalize must be the absolute last action
description: Nothing should happen after finalize — no memory writes, no output beyond the status line. Re-run finalize if any work follows.
type: feedback
---

Finalize must be the very last thing in a session. After running it, output only the status line ("Finalize is running ...") and nothing else.

**Why:** Any work after finalize (memory writes, tool calls, text output) generates more session data that won't be captured. The user had to re-run finalize because of post-finalize work.

**How to apply:** Do all memory writes, file edits, and other work BEFORE finalize. Then run finalize and output only the status line. If something unavoidably happens after finalize, run finalize again.
