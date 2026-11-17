# Lean and Safe

A coding skill for AI assistants: **write the least code that fully does the job — then prove it
does.** Keep things simple, reuse what the project already has, skip extras nobody asked for, but
never cut the parts that make a feature actually work: input checks, limits, save order, data
safety, and tests for risky logic.

Works with any assistant that reads skills (Claude Code, OpenAI Codex and others). In a plain chat,
paste the contents of `SKILL.md` as your first message.

## Why it exists

"Minimal code" skills make AI write less code — good — but in our tests they also cut things that
mattered: an alert that could never fire because of the default value the code itself suggested, a
permission request that repeated on every click, missing limits. Lean and Safe keeps the
simplicity and adds one habit most assistants skip: **walk the real user path with your own
defaults before saying done.**

## What it makes the assistant do

1. Turn the request into a checklist, keeping the exact words ("only once", "max 50").
2. Read the code it touches and reuse what is there.
3. Build the smallest *complete* version — no extra options or layers.
4. Never cut: input validation, limits, safe save order, data-loss protection, security.
5. Walk the feature like a user: accept the suggested value, do it twice, with bad input, after a
   reload, while something else is running.
6. Test the edges, run every test, then report: what changed, proof, what was not checked.

## Test results

We gave the same 4 real coding jobs to the same AI model (Claude Sonnet) three ways: **plain**,
with a popular **"minimal code"** skill, and with **Lean and Safe**. A stronger model (Claude Opus)
then judged each set **blind**, without knowing which version was which, scoring correctness,
coverage of the request, safety, tests and simplicity (0–10).

| Job | Plain | Minimal-code skill | Lean and Safe |
|---|---|---|---|
| Price alerts in a chart app (front end + server) | 7 | 7 | **8** (1st) |
| CSV export with a safe download endpoint | 7 | 8 | **8** (1st) |
| Salon bookings: opening hours, staff, no overlaps, free slots | 8 | 7 | **9** (1st) |
| Small HTTP API with validation and size limits | **8** (1st) | 6 | 8 (2nd) |
| **Average score** | 7.5 | 7.0 | **8.25** |
| Lines of code written (all 4 jobs) | 1,502 | 871 | 1,335 |
| Model cost (all 4 jobs) | $2.47 | $2.01 | $3.03 |

**What this means:** Lean and Safe was ranked best in 3 of 4 jobs and second in the other. It
wrote a bit less code than plain AI. The minimal-code skill wrote by far the least code and was
the cheapest, but it scored lowest on correctness.

**Honest limits of this test:**

- One run per job and way; AI results vary from run to run.
- One judge model; a different judge might score differently.
- The price-alerts job was also the job that showed us what to add to this skill, so it is not a
  neutral test for it. The other three jobs were new.
- Lean and Safe costs a little more per job (it checks more before finishing).
- In the API job it added a booking limit nobody asked for; we tightened that rule afterwards
  (and have not re-run the test since).

## Install

See the [main README](../../README.md#install). Then just ask for coding work as usual, or start
with *"use lean and safe"*. For always-on use, add the contents of `SKILL.md` to your assistant's
project instructions (for example `AGENTS.md` or `CLAUDE.md`).
