---
name: lean-and-safe
description: Use on any coding task (new feature, bug fix, change, refactor) when you want small, clean code that still covers every requirement, edge case and safety limit. Reuses what the project already has, writes no extras nobody asked for, but never cuts validation, limits, error handling or tests for risky logic, and checks every requirement against the real user path before saying done. Trigger words: "lean and safe", "keep it simple but solid", "no bloat".
---

# Lean and Safe

Write the least code that **fully** does the job, then prove it does. Small is good; small *and
broken* is worse than long. Every rule below exists because "simple" code tends to fail in the
same few places.

## 1. Understand before you write

- Read the request twice. Turn it into a numbered checklist of every requirement, keeping the
  user's exact words ("ask once", "fires only once", "max 50", "per symbol"). Each line is a
  promise you will check at the end.
- Read the code your change touches and the project's own rules (README, CLAUDE.md, AGENTS.md,
  contributing notes). Note the conventions: file layout, naming, error style, test style.
- Find what already exists that you can reuse: helpers, components, validators, patterns,
  installed libraries. Reuse beats writing new code. A new dependency for a few lines is never
  worth it.

## 2. Build the smallest complete version

- Do every part the checklist needs, including the callers, tests and config your change
  affects. Nothing else: no options, layers, wrappers or "for later" code nobody asked for.
- Follow the project's existing structure. Do not reorganise what you were not asked to touch.
- Prefer clear code over clever code. A short line that needs decoding is not simple.

## 3. Never cut these (the usual failures of "minimal" code)

- **Input from outside** (forms, URLs, request bodies, files, other services): validate type,
  range and format at the boundary.
- **Anything outside input can grow** (lists, files, records, keys, queues, retries): give it a
  limit. If the request names one limit, look for the other places that can grow too. Put the
  limit at the edge you are building (the new endpoint, form or file), count only live items,
  and do not change shared business rules nobody asked you to touch.
- **Order and timing:** saves, requests and writes that can overlap must not leave old data on
  top of new data. Queue them or make them safe to repeat.
- **Data loss:** never overwrite, delete or truncate data without being sure it is the right data
  (for example: do not save before the existing data has loaded).
- **Security and privacy:** no secrets in code or logs, no path built from user input, least
  access.
- **Accessibility and clear errors** for anything a person uses.

## 4. Walk the real user path (the step most often skipped)

Before you call it done, play the feature as a real user, step by step, with **the defaults your
own code offers**:

- Click the button and accept the suggested value. Does it still work?
- Do the action twice. Do it with nothing loaded yet, with the maximum, with bad input, after a
  reload, while something else is still running (a drag, a save, a poll).
- For every "only once", "never", "always" in the request: find the case that would break it.

If any step fails, fix it and add a test for that exact case.

## 5. Test what can break

- Logic with a branch, a loop, a parser, a limit, money or security gets a small automated test,
  in the project's existing test style.
- Test the edges: empty, exactly at the limit, one over, wrong type, duplicate, the default
  value, a corrupt or missing file.
- Run all the tests, old and new. Never say "should work" — say what you ran.

## 6. Check off the list and report

Go back to the checklist from step 1. For each requirement write **done** with where it is, or
**not done** with why. Then reply briefly:

1. **What changed** — in plain words.
2. **Proof** — which tests ran and passed, and which user paths you walked.
3. **Not checked / risks** — anything you could not test, assumptions you made, limits you set.

Leave out long explanations of the code; the person can read it.

## Rules of thumb

- Smallest *complete* change wins. "Complete" is decided by the checklist, not by line count.
- If two options are the same size, pick the one that is correct at the edges.
- If something in the request is unclear and a wrong guess would build the wrong thing, ask one
  short question first. Otherwise choose the safe option and say so in the report.
