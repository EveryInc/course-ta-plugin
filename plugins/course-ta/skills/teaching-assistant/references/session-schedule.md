# Session Schedule

## Course: Build a Production-Ready App with Claude Code
**Duration**: 2 half-days (4.5 hours each)
**Format**: Remote workshop via Zoom — live coding demos + hands-on exercises
**Headline**: "Ship it. Then make it compound."

---

## Day 1: Get Something Live

**Goal**: Every student has a production app — deployed, authenticated, tested — live on the internet.

### Block 1: Zero to MVP (~60 minutes)
- **Concepts 101** (~15 min): What is an app? Frontend (dining room), backend (kitchen), database (Google Sheet/pantry), auth (login screen), deployment (opening night). Full picture: all five pieces working together.
- **Demo**: Instructor scaffolds a Next.js app with TypeScript, Tailwind, ShadCN. Connects Supabase for database + auth. Shows first login.
- **Exercise** (30 min): Students scaffold their own app, connect Supabase, build core features, sign up and log in.
- **Success criteria**: Student can sign up, log in, and see their authenticated app running locally.

### Block 2: Ship It — GitHub + Vercel (~45 minutes)
- **Concepts**: What is GitHub (project's home base, version control). What is Vercel (one click to go live, auto-deploys from GitHub). Who uses Vercel (Walmart, Nike, Netflix, etc.). The deployment pipeline.
- **Demo**: Instructor initializes git, pushes to GitHub, connects Vercel, deploys. Shows live URL.
- **Exercise** (20 min): Students deploy their app to the internet.
- **Success criteria**: App is live at a public URL with auth working. Students share URLs in chat.
- **KEY MOMENT**: Chat fills with .vercel.app URLs. 100 apps going live simultaneously.

### Block 3: Testing + CI/CD (~45 minutes)
- **Concepts**: Testing = checking your own work (chef tasting food). Why testing matters for AI (AI writes fast, tests keep it honest). The self-evaluation loop (Claude writes code -> tests run -> pass/fail -> Claude fixes). CI/CD = automatic quality control (push code -> tests run automatically -> green check or red X).
- **Demo**: Set up test suite, write tests for auth, configure GitHub Actions, TDD for a new feature.
- **Exercise** (15-20 min): Students set up tests, write test for new feature, implement with Claude, push, watch CI run.
- **Success criteria**: Green check mark on GitHub repo.
- **KEY MOMENT**: The green check mark — CI passing on screen.

### Block 4: Vercel React Best Practices (~45 minutes)
- **Concepts**: Vercel's React Best Practices Skill — 40+ rules, 19 topic areas. Like having a senior engineer review your code.
- **Demo**: Install skill, run against project, fix issues live.
- **Exercise** (15 min): Students install skill, run review, fix issues.
- **Success criteria**: Project passes the Vercel best practices review.

### Day 1 Close
- Recap: MVP + Auth + Database -> GitHub + Vercel -> CI/CD + Testing -> Best Practices Review
- **Homework**: Break your own app. File as many GitHub issues as you can. Be ruthless.
- Preview Day 2: "Tomorrow: Make it compound."

---

## Day 2: Manage Your Agents

**Goal**: Students learn to manage AI agents — direct them, review their work, run multiple in parallel.

### Opening
- Poll: How many issues did you file? (Sets up the pain)
- "Your codebase is messy. Your backlog is full. This is normal."
- "Stop pushing to main. Start making pull requests."

### Block 1: Pull Requests (~45 minutes)
- **Concepts**: What is a branch (safe copy to experiment on). What is a pull request ("Here's what I changed. Review it." — the conversation around your code). The review loop: Comment -> Claude fixes -> You approve.
- **KEY INSIGHT**: "This is how you manage an AI agent."
- **Demo**: Pick issue from backlog, create branch, have Claude fix it, open PR, review on GitHub, leave inline comment, have Claude address it, approve, merge.
- **Exercise** (20 min): Students fix an issue via full PR workflow — branch, build, review with inline comments, merge.
- **Success criteria**: Issue closed via merged PR with at least one review comment addressed.

### Block 2: Multi-Claude / Worktrees (~60 minutes)
- **Breakout rooms** (10 min): Groups of 3. Share apps, each person suggests a feature for the others. Leave with 2 feature requests.
- **Concepts**: The naive approach — two terminals, same codebase, total chaos (two chefs, one kitchen). Worktrees = parallel PRs without the mess. `claude --worktree` — that's it. "Promote yourself to manager."
- **Demo**: Split screen — two Claude sessions building two features simultaneously via worktrees. Both open PRs. Review, merge, deploy.
- **Exercise** (30-40 min): Students build both features at once using worktrees. Review both PRs. Merge and deploy.
- **Success criteria**: Both features live and working. Two PRs merged.
- **KEY MOMENT**: Gold background slide — "You're the manager now." Identity shift lands.

### Block 3: Compound Engineering (~45 minutes)
- **Concepts**: Compound engineering — each unit of work makes the next one easier. The loop: Plan (skills) -> Work (worktrees) -> Review (PRs) -> Compound (lessons feed back). Install the Compound Engineering Plugin.
- **Demo**: Crush the entire remaining backlog — every issue becomes a worktree, each worktree becomes a PR, multiple agents in parallel.
- **Exercise** (20-30 min): Students clear every open issue using compound engineering workflow.
- **Success criteria**: Zero open issues. All PRs merged. App deployed with all fixes.

### Day 2 Close
- Full picture: 7 blocks across 2 days = production-ready app
- Compound engineering loop reinforced with real examples from what they built
- Tools they leave with: TA Plugin, Vercel Skill, Compound Engineering Plugin
- Community: Every membership, Discord, recordings, office hours
- "Ship it. Then make it compound."
