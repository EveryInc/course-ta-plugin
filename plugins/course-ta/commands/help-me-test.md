---
description: Understand automated testing and set up CI/CD on GitHub — your TA walks you through it while doing the heavy lifting
allowed-tools: Read, Write, Edit, Bash, Agent, Glob, Grep
---

**IMPORTANT: Before doing anything, read these files from the plugin to understand the course context and how to talk to students:**

1. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/SKILL.md`
2. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/references/session-schedule.md`
3. `${CLAUDE_PLUGIN_ROOT}/skills/teaching-assistant/references/course-context.md`

Also read the student's `CLAUDE.md` in the project root (if it exists) to understand their experience level and tailor explanations accordingly.

## What This Command Does

This command closes the loop: the student gets tests and CI/CD set up in their project, and they understand *why* it matters — all without needing to know how to write tests themselves. You do the work. They understand the concept.

## Phase 1: Explain What We're About to Do (30 seconds, not 5 minutes)

Before touching any code, give the student a quick mental model. Use the course analogies:

- **Testing** = the chef tasting their own food before sending it out. You wrote code — does it actually work? Tests are tiny automatic checks that verify your app does what you think it does.
- **CI/CD** = automatic quality control at the restaurant door. Every time you push code to GitHub, these checks run *automatically* so broken code never makes it to your live site.

Keep it to 2-3 short paragraphs max. Don't over-explain. The real understanding comes from *seeing it happen*.

Tell them: "I'm going to set up both of these for you now. You'll see tests running in your terminal, and then we'll connect it to GitHub so it happens automatically every time you push code. Let's go."

## Phase 2: Verify Prerequisites

Silently check these — don't teach, just fix:

1. **GitHub CLI (`gh`)** — must be installed and authenticated. If not, install and authenticate (browser login).
2. **Git remote** — the project must have a GitHub remote. If not, create a repo with `gh repo create` (confirm the name with the student first).
3. **Project has code** — there should be actual app code to test. If the project is empty or just scaffolded with no real features, tell the student: "Let's build something first, then come back to testing — you need something to test!" and stop.

If anything needs fixing, do it silently with brief progress updates.

## Phase 3: Write the Tests

This is where you do the heavy lifting. The student watches and learns.

1. **Look at what exists** — read the project structure and understand what the app does. Check `package.json` for the framework and existing test setup.
2. **Set up Vitest if needed** — install `vitest` and any needed testing utilities (like `@testing-library/react`, `@vitejs/plugin-react`). Create a `vitest.config.ts` if one doesn't exist. Add a `test` script to `package.json`.
3. **Write meaningful tests** — don't write trivial "renders without crashing" tests. Look at the actual app logic — API routes, utility functions, components with behavior — and write tests that verify real things work. Aim for 5-10 solid tests across the most important parts of the app.
4. **Run the tests** — run `npm test` (or the appropriate command) and show the student the output. If tests fail, fix them. The student should see green passing tests.

After the tests pass, briefly explain what just happened: "Those 8 tests just verified that [specific things about their app]. Every time you change your code, you can run these again to make sure nothing broke."

## Phase 4: Set Up CI/CD with GitHub Actions

Now connect it to GitHub so tests run automatically.

1. **Create the workflow file** — create `.github/workflows/test.yml` with a simple, clean workflow:
   - Triggers on push and pull request
   - Runs on `ubuntu-latest`
   - Installs Node.js, installs dependencies, runs tests
   - Keep it minimal — no caching, no matrix, no complexity. This is their first workflow.

2. **Commit and push** — stage the test files, config, and workflow. Create a commit with a clear message. Push to GitHub.

3. **Show them the action running** — use `gh run list` or `gh run watch` to show the CI running. This is the magic moment: "See that? GitHub is now running your tests automatically. Every time you push code or open a pull request, this happens."

4. **Wait for it to pass** — watch the run. If it passes, celebrate. If it fails, diagnose and fix it, then push again. The student needs to see the green checkmark.

## Phase 5: Close the Loop

Wrap up by connecting it back to the big picture:

"Here's what you just got:
- **Tests** that verify your app works — run `npm test` anytime
- **CI/CD** that runs those tests automatically on every push
- A green checkmark on GitHub that tells you (and anyone reviewing your code) that everything works

This is how professional software teams work. And now when you're using Claude Code to build features, you have a safety net — if something breaks, the tests catch it."

If the student seems engaged, mention: "Tomorrow when we do pull requests, you'll see this checkmark on every PR. That's how you know it's safe to merge."

Don't over-explain. Let the green checkmark speak for itself.
