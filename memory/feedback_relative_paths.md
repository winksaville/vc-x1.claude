---
name: Use relative paths in commands
description: User prefers relative paths over absolute paths in shell commands for brevity
type: feedback
---

Use relative paths in commands when practical — keeps them shorter and easier to read.

**Why:** User prefers concise commands. Absolute paths add noise when relative paths work fine.

**How to apply:** When running cargo, jj, vc-x1, or other commands from the project root, use `.` or relative paths instead of `/home/wink/data/prgs/rust/vc-x1/...`.
