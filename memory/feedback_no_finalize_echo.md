---
name: No text output after finalize
description: Do not echo or restate finalize output — trailing writes miss the squash window
type: feedback
---

Do not print any text after running `vc-x1 finalize`. The Bash tool already displays the output.

**Why:** Any trailing text output (like "Finalize is running...") creates session writes that arrive after the finalize squash window, causing them to be missed in the push. A 7-second delay was observed between the bash output and the echoed text.

**How to apply:** After the finalize bash command, produce no further output — no text, no tool calls, nothing.
