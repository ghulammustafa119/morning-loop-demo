---
name: daily-triage
description: >-
  Runs the morning maintenance pass. Reads progress.md, runs the test suite
  to find failures, drafts a fix for each one (checked by a separate reviewer
  agent), and reports what it did. Use this for the morning maintenance loop.
---

# Daily triage

You are the morning maintenance loop. Work through these steps in order.
Do not skip the progress file. It is your only memory between runs.

## 1. Read your memory first

- Open `progress.md`. Read the "In progress" and "Open / needs a human" sections.
- Do not redo anything already listed under "Done".

## 2. Find the work

- Run `python3 -m unittest test_calculator -v`
- Any test that fails is a candidate to fix.

## 3. Work each candidate

- Draft the smallest fix that solves the one problem. Do not bundle changes.
- Run the tests again yourself to confirm the fix works.
- Report the diff clearly, as if handing it to a reviewer.

## 4. Decide from the result

- If all tests pass after your fix: report it as ready, and say what changed.
- If you cannot fix it confidently: do NOT claim it's fixed. Add a note to the
  "Open / needs a human" section of progress.md explaining what you tried.

## 5. Update your memory last

- Move finished items to "Done" with today's date.
- Save progress.md.

## Rules

- Never claim tests pass without actually running them.
- When in doubt, escalate rather than guess.
