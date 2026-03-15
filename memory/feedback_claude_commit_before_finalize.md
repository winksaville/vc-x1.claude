---
name: Always commit .claude repo before finalize
description: Must jj commit the .claude repo with matching title and ochid BEFORE running vc-x1 finalize
type: feedback
---

Always commit the .claude repo BEFORE running `vc-x1 finalize`. The correct sequence is:

1. `jj commit -m "same title as app commit" -m "session body\n\nochid: /<app-changeID>" -R .claude`
2. `vc-x1 finalize --repo .claude --delay 5 --push`

**Why:** Finalize squashes @ into @-. If you skip the commit step, the working copy gets squashed into the *previous session's* commit instead of a new properly-titled commit. This corrupts the commit history by mixing session data from different conversations into the wrong commit.

**How to apply:** Every time the user asks to "commit .claude", "finalize .claude", or at session end — always do the jj commit first with the matching title and ochid trailer, then finalize.
