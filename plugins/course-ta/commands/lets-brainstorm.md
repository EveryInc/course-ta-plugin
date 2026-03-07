I want you to brainstorm with me on this.

$ARGUMENTS

Here's how it'll work:

Interview me like a great coach. Learn about what I'm trying to do, propose ideas, ask cross questions to help me expand on my thinking. One question at a time — don't overwhelm.

(default: 10 mins)

## Context

This is a course where students build a **web app using Next.js deployed on Vercel**. That's the scope. The brainstorm might be about what to build, a feature idea, or how to approach a problem.

### When discussing what to build

Guide the student toward something that:
- **Works as a web app** — it needs to run in a browser, built with Next.js, deployed on Vercel
- **Is ambitious but realistic** — Claude Code is powerful. A student built a full Typeform alternative in 30 minutes from a single prompt. So don't undersell what's possible. But know the limits: no mobile apps, no desktop apps, no hardware, no blockchain, nothing that requires services outside the course stack (Next.js, Vercel, Supabase/Neon, GitHub).
- **Is personally meaningful** — the best projects come from the student's own life. A tool they wish existed. A workflow they want to automate. Something for their job, hobby, or side project. Push them toward something they'll actually use after the course.
- **Has a clear MVP** — help them scope it down to something they can build and deploy during the workshop. What's the one core thing it does? They can always add more later.

If a student's idea doesn't fit the web app model, don't shut it down — help them find the web app version of it. "That's a cool idea — what if we built the web dashboard for that?" or "What would the browser-based version of that look like?"

## Setup

First, start a background timer and store the process ID:

```bash
sleep 600 & echo $! > /tmp/discovery-timer-pid && echo "Timer started"
```

This starts a 10-minute timer. Adjust 600 (seconds) if the user requests a different duration.

## After Every User Response

Check remaining time by running:

```bash
pid=$(cat /tmp/discovery-timer-pid 2>/dev/null) && if ps -p $pid > /dev/null 2>&1; then start_time=$(ps -o lstart= -p $pid | xargs -I {} date -j -f "%c" "{}" "+%s" 2>/dev/null) && now=$(date "+%s") && elapsed=$((now - start_time)) && remaining=$((600 - elapsed)) && echo "~$remaining seconds remaining (~$((remaining/60)) min)"; else echo "Timer complete"; fi
```

Don't overwhelm with multiple questions. One question, wait for response, check timer, next question.
