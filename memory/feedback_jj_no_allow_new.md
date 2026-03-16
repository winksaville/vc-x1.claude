---
name: jj git push has no --allow-new flag
description: Don't use --allow-new with jj git push — it doesn't exist. jj pushes new bookmarks without special flags.
type: feedback
---

Never use `--allow-new` with `jj git push` — the flag doesn't exist.
Just use `jj git push --bookmark <name> -R <repo>` for both new and existing bookmarks.

**Why:** Used `--allow-new` which triggered deprecation warnings. Checking `jj git push -h` confirmed the flag isn't listed at all.

**How to apply:** Any time pushing bookmarks with jj, just use `--bookmark` — no extra flags needed.
