# Course TA Plugin

AI teaching assistant marketplace for Every Consulting's "Build a Production-Ready App with Claude Code" workshop.

## Versioning

Two files must stay in sync:
- `plugins/course-ta/.claude-plugin/plugin.json` — plugin version
- `.claude-plugin/marketplace.json` — marketplace metadata version AND the plugin entry version

**Rules:**
- Bump for meaningful changes (new feature, behavior change, bug fix). Don't bump for typos, comments, or internal-only changes.
- Not all changes require a major version bump — use your judgment.

## Design Philosophy

- **Don't script the model** — define goals and constraints, not step-by-step scripts or canned dialogue. Trust Claude's intelligence.
- **Do it, don't teach it** — setup installs things silently, never tells students to run commands.
- **Preserve student voice** — store motivation in their own words.
- **Minimal prescription** — give Claude context and knowledge, not pre-built answers or rigid response templates.
