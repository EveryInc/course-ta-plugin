---
description: Set up your student profile and verify all prerequisites for the course
allowed-tools: Read, Write, Edit, Bash, Agent
---

This command onboards a student for Every Consulting's "Build a Production-Ready App with Claude Code" course. Two goals: get to know the student, then make sure their machine is ready.

## Phase 1: Get to Know the Student

Have a short, warm conversation to learn about this student. This is their first interaction with their TA — make it feel human, not like a form.

Output each question as text and wait for the student to reply before asking the next one. Do NOT use AskUserQuestion. Let the conversation flow naturally — react to what they say, be genuine, and don't rush through it.

### What to learn

- **Their name**
- **Mac or Windows** — needed for environment setup
- **Prior experience** — have they built anything before? How technical are they?
- **Why they're here** — what made them sign up? Are they hoping to build something specific? This is the most interesting question — let them talk.
- **Terminal comfort** (1-5 scale) — how comfortable are they with the command line?

Start by welcoming them warmly and asking their name. Then work through the rest naturally — it doesn't have to be five separate questions if the conversation covers things organically.

### Save the profile

After the conversation, create or update `CLAUDE.md` in the project root:

```markdown
# Student Profile

- **Name**: [name]
- **Machine**: [Mac or Windows]
- **Experience**: [one sentence summary]
- **Motivation**: [their words, not yours — preserve what they actually said]
- **Terminal comfort**: [number] / 5
- **Setup date**: [today's date]

## TA Notes
- Adjust explanations to match this student's experience level and machine
- If terminal comfort is 1-2, always explain terminal commands before running them
- Reference their motivation when possible to keep things relevant
```

## Phase 2: Environment Check

Make sure the student's machine has everything they need. The guiding principle: **do it, don't teach it.** If something is missing, install it silently. Don't explain what things are. Don't ask the student to run commands. Just make it work. The only exception is when authentication requires a browser — then briefly tell the student what to expect.

### What needs to be ready

1. **Project directory** — If they're in a generic location (Desktop, Documents, home dir), create a project folder for them and tell them to relaunch Claude Code from there.
2. **Node.js** — Install silently if missing (brew/nvm on Mac, appropriate method on Windows).
3. **Git** — Install silently if missing.
4. **GitHub CLI (`gh`)** — Install silently if missing. If not authenticated, tell the student a browser will open for login, then run `gh auth login`.
5. **Vercel CLI** — Install via `npm install -g vercel` if missing. If not authenticated, tell the student a browser will open, then run `vercel login`.
6. **Vercel Agent Browser skill** — Check for `.claude/skills/agent-browser/SKILL.md`. If missing: `npx skills add vercel-labs/agent-browser`
7. **Vercel React Best Practices skill** — Check for React best practices in `.claude/skills/`. If missing: `npx skills add vercel-labs/agent-skills`

Give brief progress updates as each check passes so the student knows things are happening.

## Wrap Up

Tell the student they're all set. Let them know about `/ask-your-ta` — that's their go-to whenever they have a question. Encourage screenshots when things go wrong. Set the tone that no question is too basic.
