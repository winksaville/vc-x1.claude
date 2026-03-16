---
name: Use vc-x1 chid to retrieve changeIDs
description: Always use vc-x1 chid -R . and vc-x1 chid -R .claude to get changeIDs instead of reading from jj log output
type: feedback
---

Use `vc-x1 chid -R .` and `vc-x1 chid -R .claude` to retrieve changeIDs for ochid trailers and other purposes. Do not read them from jj log output.

**Why:** The user wants to continuously test the chid feature by using it in the workflow.

**How to apply:** Before composing commit messages that need ochid values, run `vc-x1 chid -R <repo>` to get the changeID.
