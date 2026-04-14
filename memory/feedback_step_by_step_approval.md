---
name: Step-by-step approval for commit/push/finalize operations
description: User wants to approve every individual action during commit/push/finalize sequences, not just batch approval at checkpoints
type: feedback
originSessionId: bcdae425-aa30-4c91-a6ec-24a6faf26bfe
---
During session-end workflow (commit → push → finalize) and any time
we're touching the `.claude` repo beyond straightforward commits, stop
and ask for approval **before each individual action**, not just at
the two CLAUDE.md checkpoints.

**Why:** `.claude` repo operations are especially error-prone because
of the circular reference pattern (session data writes while we're
operating on it, ochid trailers cross-reference between repos). A
single non-straightforward action on `.claude` can cascade into a
disaster. The strict CLAUDE.md commit/finalize rules exist precisely
because of these circular-reference hazards. When a planned command
fails partway (e.g. push fails and needs a bookmark-track fix first),
do NOT chain the fix + retry — pause, explain, wait for approval.

**How to apply:**
- Treat any deviation from the pre-approved plan (even a small fix
  like `jj bookmark track`) as a new action requiring its own
  explicit approval.
- For multi-step sequences in the session-end flow, prefer asking
  "proceed with X?" between each step rather than batching.
- This applies most strongly to `.claude` operations — anything
  beyond a plain `jj commit` on `.claude` should be flagged and
  approved first.
- Chained `&&` commands like `push && finalize` are acceptable ONLY
  when that exact sequence was explicitly approved; if one half
  fails, unbundle and re-approve each half.
