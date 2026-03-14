---
name: Always include ochid trailer in commits
description: App repo commits must include ochid trailer referencing the .claude repo counterpart changeID
type: feedback
---

Always include the `ochid` trailer when committing to the app repo. The trailer links the commit to its .claude session counterpart.

**Why:** The ochid trailer is part of the inter-repo cross-reference convention. Missing it breaks the ability to correlate app and session commits.

**How to apply:** Before proposing any app repo commit, check `jj log -R .claude --limit 1` to get the current .claude working copy changeID, then add `ochid: /.claude/<changeID>` as a trailer in the commit body.
