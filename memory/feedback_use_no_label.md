---
name: Use -L for ochid retrieval
description: Use vc-x1 chid -R .,.claude -L for clean parseable output when fetching ochid values
type: feedback
---

When fetching changeIDs for ochid trailers, use `-L` (no label) for clean output:
`vc-x1 chid -R .,.claude -L` → two plain lines, first is app repo, second is .claude repo.

**Why:** The default headers add noise when programmatically using the output. The feature was built for this exact use case.

**How to apply:** During session-end workflow when retrieving ochid values for commit trailers.
