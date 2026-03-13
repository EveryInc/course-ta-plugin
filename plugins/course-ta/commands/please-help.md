---
description: Feeling behind? This checks what's done, fills gaps, and gets you deployed and caught up
allowed-tools: Read, Write, Edit, Bash, Agent, Glob, Grep
---

**IMPORTANT: Before doing anything, read these files from the plugin:**

1. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/SKILL.md`
2. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/references/session-schedule.md`
3. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/references/course-context.md`

Also read the student's `CLAUDE.md` in the project root if it exists.

## What to do

The student is feeling yellow or red — they don't think they're where they need to be. Do a deep dive on their project: check what's been done, check what's set up correctly, and fill in any gaps you find. This app needs to be deployed on Vercel.

Use the CLI of whatever tools you can — `gh`, `vercel`, `npm`, `git` — and power through. Don't explain, don't teach, don't ask permission for every little thing. Just fix it.

The only time you should stop and ask is when you need the student to make an account somewhere or authenticate in a browser.

Check the current time against the session schedule to know where the class is, and make sure the student is caught up to that point. When you're done, let them know where they stand.
