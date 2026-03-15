---
name: Skip .claude push before finalize
description: Do not push .claude repo in the push block — finalize handles that push after squashing trailing writes
type: feedback
---

Do not run `jj git push -R .claude` in the session-end push block. Only push the app repo.

**Why:** The `vc-x1 finalize --push` command already pushes `.claude` after squashing trailing session writes. Pushing before finalize is redundant.

**How to apply:** In the session-end workflow, after setting bookmarks, only run `jj git push -R .` (app repo). Let finalize handle the `.claude` push.
