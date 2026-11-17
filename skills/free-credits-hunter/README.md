# Free Credits Hunter

A skill that turns your AI assistant into a careful helper for finding **free credits** for AI
and cloud services — startup programs, grants, free tiers and plan discounts — applying for them,
and tracking the results.

Works with any AI assistant that reads skills (Claude Code, OpenAI Codex, and other tools that
use the open `SKILL.md` format). In a plain chat (ChatGPT, Gemini, Grok…) you can paste the
contents of `SKILL.md` as your first message.

## What it does

1. **Talks to you first** — who is applying, what you build, what you already use and pay for.
2. **Checks official pages only** — OpenAI, Anthropic, xAI, Google, NVIDIA, AWS, Azure,
   Vercel, Cloudflare and the tools you already use. Writes down value, type, who qualifies, expiry.
3. **Spots the traps** — investor-only programs, "credits after you spend" offers, agency
   exclusions, one-application-only rules.
4. **Applies in your own browser** with your existing logins. You type passwords, codes, cards
   and CAPTCHAs yourself, and you approve every application before it is sent.
5. **Keeps a private tracker** with proof (confirmation emails, screenshots) for every program.
6. **Re-checks every week** — offers and pending answers — but never applies or pays by itself.

## Safety by design

- Never types passwords, codes, card or bank numbers.
- Never turns on billing or a paid plan.
- Never sends an application without your yes.
- Never invents company facts.
- Never saves API keys; the tracker stays private.

## Install

See the [main README](../../README.md#install) for setup steps for each assistant.
Then ask something like *"find free AI credits for my company"*.

## Files

- `SKILL.md` — the instructions your assistant follows.
- `templates/TRACKER-template.md` — the tracker layout (copy it to a private folder).

> Program terms change often. The skill always checks the official page on the day it runs;
> nothing here promises that any program will accept you.
