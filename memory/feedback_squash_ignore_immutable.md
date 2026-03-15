---
name: Use --ignore-immutable for late squash after push
description: After pushing, commits become immutable — use jj squash --ignore-immutable to fold in late changes
type: feedback
---

When changes are made to a repo after it has been pushed, `jj squash` will fail because the commit is now immutable. Use `jj squash --ignore-immutable -R <repo>` to fold late changes in, then re-set the bookmark and push.

**Why:** Pushed commits are immutable by default in jj. Late changes (e.g. CLAUDE.md updates, memory writes) after the initial push need this flag.

**How to apply:** Whenever squashing into a previously-pushed commit, add `--ignore-immutable`. Then `jj bookmark set main -r @-` and `jj git push`.
