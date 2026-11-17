# AI Unmasked Skills

Ready-made skills for AI assistants — plain instructions that teach an assistant to do one job
well and safely. Free to use, copy and adapt.

They follow the open `SKILL.md` format, so they work with **Claude Code**, **OpenAI Codex** and
other assistants that read skills. In any chat assistant you can also paste a skill's `SKILL.md`
as your first message.

## Skills

| Skill | What it does |
|---|---|
| [Lean and Safe](skills/lean-and-safe/) | Coding skill: the least code that fully does the job, then proof that it does — simple, but never cutting checks, limits or tests. Blind-tested against plain AI and a popular minimal-code skill. |
| [Free Credits Hunter](skills/free-credits-hunter/) | Finds, applies for and tracks free AI and cloud credits (startup programs, grants, free tiers) — official pages only, you stay in control of passwords, cards and every submission. |

More skills are on the way.

## Install

Each skill is one folder under `skills/`. Download this repository:

```bash
git clone https://github.com/aiunmasked/skills.git
```

Then copy the skill folder to where your assistant looks for skills:

| Assistant | Copy the folder to |
|---|---|
| Claude Code | `~/.claude/skills/` (all projects) or `.claude/skills/` inside one project |
| OpenAI Codex | `~/.codex/skills/` |
| Other skill-aware tools | the skills folder named in that tool's docs |
| Any chat assistant | no install — paste the contents of `SKILL.md` into the chat |

Example for Claude Code:

```bash
cp -r skills/skills/lean-and-safe ~/.claude/skills/
```

## How a skill is built

```
skills/<skill-name>/
├── SKILL.md      # the instructions (name + description at the top, then the steps)
├── README.md     # what it does, for people
└── templates/    # optional files the skill uses
```

## Good to know

- Skills are instructions, not programs: they don't install anything or run code by themselves.
- Read a skill before you use it — it tells your assistant what it may and may not do.
- Offers, prices and rules from outside companies change. The skills always check the official
  source on the day they run.

## License

[MIT](LICENSE) — use it, change it, share it.
