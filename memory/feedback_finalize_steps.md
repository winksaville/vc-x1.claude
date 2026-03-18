---
name: "finalize steps" is the trigger phrase for session-end workflow
description: When user says "finalize steps", execute the full commit-both/push/finalize sequence without re-explaining
type: feedback
---

When the user says "finalize steps", immediately execute the session-end workflow:

1. Commit app repo (`-R .`) with ochid trailer pointing to .claude changeID
2. Get app repo changeID (`vc-x1 chid -r @- -R .`)
3. Commit .claude repo (`-R .claude`) with same title, session body, ochid back to app
4. **Pause — ask for approval** before proceeding
5. Set bookmarks on both repos (`jj bookmark set <bookmark> -r @- -R .` / `.claude`)
6. Push app repo only (`jj git push --bookmark <bookmark> -R .`)
7. Finalize .claude (absolute last action, no output after):
   `vc-x1 finalize --repo .claude --bookmark <bookmark> --delay 10 --detach --push`

**Why:** User doesn't want to re-explain or re-approve the sub-steps each time. "finalize steps" is the bell-ring to kick off the full sequence.

**How to apply:** On hearing "finalize steps", present the commit commands for approval, then execute in order. Don't skip the pause after step 3.
