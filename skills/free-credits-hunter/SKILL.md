---
name: free-credits-hunter
description: Use when someone wants to find, apply for and keep track of free credits for AI and cloud services (startup programs, research grants, free tiers, plan discounts) from providers such as OpenAI, Anthropic, xAI, Google, NVIDIA, AWS, Microsoft Azure, Vercel or Cloudflare. Researches only official program pages, applies with the person's existing logins while they handle passwords, codes and cards themselves, keeps a private tracker with proof for every program, and sets up a weekly re-check.
---

# Free Credits Hunter

Find every free AI / cloud credit a company or person can **really** get, apply where it is
possible, and keep an honest record of what happened. The person you work for may not be
technical: talk in plain words, do the work yourself, and stop only for the steps that must be
theirs.

## Hard rules (never break these)

1. **Official sources only.** Trust the provider's own page as it reads *today*. Blog posts,
   coupon sites and old forum threads are leads, never proof. Record the date you checked.
2. **You never type secrets.** Passwords, one-time codes (email/SMS), card numbers, bank details
   and CAPTCHAs are always done by the person. Stop at that step and tell them exactly what to do.
3. **No money moves.** Never turn on a paid plan, billing, auto top-up or a trial that converts to
   paid. If a program needs a card on file, stop and ask the person about *that* program.
4. **Ask before you submit.** Show the filled-in application and get a clear yes before pressing
   Submit. One yes covers one application.
5. **True data only.** Use the real company facts. You may choose *which* real product to present
   (see "Eligibility traps"), but never invent revenue, staff, funding or customers.
6. **No keys saved.** If a program hands out an API key or token, tell the person where it is;
   do not copy it into notes, the tracker or chat.
7. **The tracker is private.** It holds company details and account facts. Keep it out of any
   public repo or shared folder (add it to `.gitignore`).

## Step 1 — Brainstorm first (before any searching)

Agree on the basics with the person in a short chat. Ask only what you cannot find yourself:

- **Who is applying?** Company name, country, registration date, type (sole trader, limited
  company…), staff count, outside investors yes/no. Look up public registers yourself where
  possible and ask the person to confirm.
- **What do they build?** List their *products* (apps, AI services, tools) with public websites.
- **What do they spend on today?** Which AI APIs, clouds, hosting, voice or video tools. Credits
  for tools they will never use are worth nothing.
- **Which accounts already exist?** Re-use existing accounts; never register twice.
- **Which email to apply with?** Many programs want an address on the company's own domain
  (not Gmail/Outlook).
- **Card rule:** may you ever bring them to a card step, or skip every program that needs one?

Write a short design note (why, scope in priority order, rules, done-when) and get a yes.

## Step 2 — Research each provider

Start with this list, in this order unless the person says otherwise, then widen only after
their yes:

| Area | Providers to check |
|---|---|
| AI models | OpenAI, Anthropic, xAI, Google (Gemini API free tier) — startup programs, API credits and plan offers |
| Cloud | Google for Startups Cloud Program, AWS Activate, Microsoft for Startups / Azure credits, NVIDIA Inception |
| Hosting / edge | Vercel, Cloudflare for Startups |
| Tools they already use | voice, video, database, monitoring etc. — many have startup grants |

For each program, record from the official page:

- value and currency, and **type**: API credit · cloud credit · plan discount · free tier
- who qualifies (age of company, funding, staff, country, industry)
- how long the credit lasts / expiry
- card needed? existing account needed? referral or partner code needed?
- official link and the date you checked

## Eligibility traps (check every program for these)

- **Investor / accelerator only.** If a program is only open through a VC, accelerator or partner
  the person does not have, mark it **No**, not "pending".
- **Conditional credits.** "Get X after you spend Y" is *not* free money. List it as
  conditional and never add it to the available total.
- **Agency exclusion.** Many programs refuse agencies and client-service businesses. If the
  company also has a real product, apply as the product company — truthfully.
- **One per company.** Some programs allow a single application ever. Prepare it carefully.
- **Changed or expired offers.** If today's page differs from what you remember or what a blog
  says, today's official page wins.

## Step 3 — Apply

Work in the person's own browser where they are already signed in.

1. Open the official application page. Fill the form with the agreed true facts.
2. When you reach a login, code, card or CAPTCHA step: stop, tell the person the exact step
   ("type the 6-digit code from the email into the box on the left"), wait until they say done.
3. Show the finished form and ask "Submit this one?". Submit only after a yes.
4. Save proof: confirmation screenshot file name, or the confirmation email's subject + date.
5. Programs that need a card: list them and ask about each one separately.

Never use scripts or bots to fill applications — most sites forbid it, and it would need the
person's passwords.

## Step 4 — Keep the tracker

Copy `templates/TRACKER-template.md` into a **private** folder as `TRACKER.md` and keep one row per
program. Allowed statuses:

- **Confirmed** — credits are visible in the account (proof attached)
- **Applied / pending review** — submitted, waiting for an answer
- **Needs person** — parked at a named step only they can do (login, code, card, domain email)
- **Not eligible** — with the reason (investor-only, agency excluded, country…)
- **Not applied** — eligible but skipped, with the reason

Totals are split by currency, by type and by status. Conditional credits are listed but never
counted as available.

## Step 5 — Weekly re-check

Create a recurring task (for example Mondays 09:00 in the person's time zone) that:

1. Reads `TRACKER.md`.
2. Re-opens each official program page and notes changes (new programs, changed values, closed).
3. Checks the inbox **read-only** for replies to pending applications.
4. Updates the tracker and sends the person a short notification.

The weekly task **only researches and reminds**. It never applies, submits, signs up or pays on
its own. Confirm the task appears in the schedule list before calling the job done.

## Step 6 — Report

Give the person a short plain-language summary:

- what is **confirmed** (amounts by currency and type)
- what is **pending** and when an answer is expected
- what **needs them** — numbered steps, one action each
- what is **not possible**, and why in one line

## If your assistant lacks a tool

- **No browser control:** do all research and fill the tracker, then give the person
  ready-to-paste text for each form field plus the link; they submit it themselves.
- **No scheduler:** at the end, give the person a one-line reminder to ask for the weekly
  re-check, and write the re-check steps at the top of the tracker.
- **No web access:** say so at once. Do not answer from memory — offers change too often.

## Done when

Every priority provider has a checked status in the tracker, every possible free application
is sent or parked at a named step for the person, and the weekly re-check exists and shows in
the schedule list.
