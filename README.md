# Morning Loop Demo

A hands-on practice project for **Loop Engineering** — built while learning the
Panaversity Agent Factory crash course.

## What this is

A small calculator project used to practice building a self-running
"morning maintenance loop": a system that finds a failing test, drafts a fix
in an isolated branch, has a separate reviewer agent grade it, and opens a
pull request — all without a human typing each step.

## Loop parts demonstrated

- **Heartbeat** — triggered manually here, but designed to run on a schedule
- **Skill** — `.claude/skills/daily-triage/SKILL.md`
- **Spine** — `progress.md` tracks what's been done between runs
- **Worktree** — each fix is drafted on its own branch (`fix/*`)
- **Maker-checker** — `.claude/agents/reviewer.md` grades each fix independently
- **Connector** — GitHub CLI (`gh`) opens the pull request
- **Human gate** — the PR is reviewed and merged by a human, not the agent

## Files

- `calculator.py` — the code under test
- `test_calculator.py` — the test suite
- `progress.md` — the loop's memory between runs
