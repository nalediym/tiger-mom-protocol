# tiger-mom-protocol

> An operating system for people who start too many projects and abandon most of them.

I'm [Naledi](https://github.com/nalediym). I start a lot of projects. For most of last year I didn't finish them. 75 git repos. 93% of them have three or fewer commits. After a while that stops looking like willpower and starts looking like a system that needs instrumentation.

So I wrote one. Tiger-mom-protocol does for me what an SRE practice does for a flaky service. It starts each session by pointing me at the nearest-finished PR, works around the hours when I actually focus (10–11am and 4–5pm, with a separate stricter midnight mode after 11pm), celebrates every merge on purpose, and saves enough context that I can come back weeks later without starting over. It's a markdown protocol plus a few bash snippets, loaded as a skill in Claude Code or OpenCode. I've been running it on my own work for nine weeks.

This repo is a portfolio piece. I'm publishing the protocol so people can see how I think and how I work, not because I'm running an open source project. See [CONTRIBUTING.md](./CONTRIBUTING.md).

> By "operating system" I mean the rules that decide what I work on next and when I can call it done.

## What it does

- **Session start checklist.** Surfaces open PRs and recent unfinished work before any new work starts.
- **Nudge system.** Three escalation levels of warm, specific reminders. No guilt, no shame.
- **Celebration loops.** Every merge gets an over-the-top response, on purpose.
- **Six-step shipping workflow.** Issue → branch → build → test → PR → merge.
- **Peak-hours model.** The protocol expects more from me when I'm sharp and less when I'm not.
- **Midnight mode.** A stricter, shorter-session mode that triggers automatically after 11pm.
- **Context save at session end.** Multi-week projects don't make you rebuild context every time.

## What using it actually looks like

You install tiger-mom-protocol and load it into a Claude Code or OpenCode session. The first thing the assistant does is run the session-start checklist: it looks at your open PRs, your recent commits, and the current time. If you have a stale PR sitting at 80% done, it says something close to:

> "Hey! Last time you were working on PR #42 (`feat: streaming responses`). Want to pick that back up?"

You can take the nudge or ignore it. If you ignore it, the protocol does not guilt-trip you. It just notes the open PR for next time. If you take it, the assistant helps you define what done looks like for this session: usually three concrete acceptance criteria you can verify with tests or screenshots before you call it shipped.

Once you start working, the assistant follows the six-step shipping flow: GitHub issue → branch → build → test → PR → merge. It refuses to skip steps. If a shiny new idea comes up mid-session, it captures the idea in a "shiny things" box and refuses to chase it. One thing per session.

When you do merge, the celebration is over the top, on purpose:

> "YOOOO YOU DID THAT! PR #42 is DONE. That's real. That counts."

At the end of the session the assistant offers to write a short summary: what got done, what is still unfinished, what is next. That summary is what your next session reads first, so the protocol stays continuous instead of restarting from zero every time.

If you log in past 11pm, midnight mode triggers automatically. No pretending tomorrow-you will pick up loose ends.

That is the experience. The rules in [skills/tiger-mom/SKILL.md](./skills/tiger-mom/SKILL.md) are what make it happen.

## Architecture

```
tiger-mom-protocol/
├── skills/
│   ├── rules/         # 17 core rules every session inherits (load this first)
│   └── tiger-mom/     # Workflow, nudges, celebration, mid-session guardrails
├── ETHOS.md           # The principles the protocol is built on
├── ORIGIN.md          # Where this came from, and the books and disciplines that shaped it
└── METHOD.md          # The interview I ran on myself to design this — questions you can reuse
```

Two skills, layered. `rules` is the foundation. `tiger-mom` is the workflow on top of it. Either works on its own; they were designed to compose.

## How to read this repo

If you're here because you want to see how I work:

- [ORIGIN.md](./ORIGIN.md) — where the name came from and which books shaped the protocol.
- [ETHOS.md](./ETHOS.md) — the principles each rule is trying to protect.
- [skills/rules/SKILL.md](./skills/rules/SKILL.md) and [skills/tiger-mom/SKILL.md](./skills/tiger-mom/SKILL.md) — the actual protocol files I run.
- [METHOD.md](./METHOD.md) — the interview I ran on myself to design this. Reusable questions if you want to write your own.

## Install

Install instructions are kept here for completeness. The protocol genuinely runs on Claude Code and OpenCode if you want to load it yourself.

> Requires macOS or Linux. The install paths use `ln -sfn`. Windows users will need `mklink /D` or copy the directories.
>
> If you already have a `rules` or `tiger-mom` skill installed, back it up first (e.g. `mv ~/.claude/skills/rules ~/.claude/skills/rules.bak`) before running the install — `ln -sfn` will refuse to overwrite a real directory.

### Claude Code

```bash
git clone --depth 1 https://github.com/nalediym/tiger-mom-protocol.git ~/.claude/skills/tiger-mom-protocol && \
  ln -sfn ~/.claude/skills/tiger-mom-protocol/skills/rules ~/.claude/skills/rules && \
  ln -sfn ~/.claude/skills/tiger-mom-protocol/skills/tiger-mom ~/.claude/skills/tiger-mom
```

Add to `CLAUDE.md`:

```markdown
Load the `rules` skill at the start of every session, then layer `tiger-mom` for any coding work.
```

### OpenCode

```bash
git clone --depth 1 https://github.com/nalediym/tiger-mom-protocol.git ~/.opencode/skills/tiger-mom-protocol && \
  ln -sfn ~/.opencode/skills/tiger-mom-protocol/skills/rules ~/.opencode/skills/rules && \
  ln -sfn ~/.opencode/skills/tiger-mom-protocol/skills/tiger-mom ~/.opencode/skills/tiger-mom
```

## What shaped the design

A join of these sources:

- ***Site Reliability Engineering: How Google Runs Production Systems*** (Beyer/Jones/Petoff/Murphy, eds., O'Reilly, 2016 — free at [sre.google](https://sre.google)) — SLOs, error budgets, toil, runbooks. Mostly the toil chapter.
- **Chaos engineering writing** out of Netflix and Casey Rosenthal's resilience community — for stress-testing systems on purpose to find the failure modes early.
- ***Getting Things Done*** (David Allen, 2001) — the capture habit. Rule #4 ("Shiny things go in the box") is GTD capture in an AI-session shell.
- ***Atomic Habits*** (James Clear, 2018) — environment design. Make the cue obvious, externalise the system.
- ***Grit*** (Angela Duckworth, 2016) — the long-arc framing. Session-save and cross-session nudges exist so projects survive the dip.
- ***Battle Hymn of the Tiger Mother*** (Amy Chua, 2011) — where the name comes from. Warm-but-strict, retuned for adult solo work.

See [ORIGIN.md](./ORIGIN.md) for how the join came together.

## License

MIT. See [LICENSE](./LICENSE).

---

This is a portfolio repository. I am not accepting pull requests for the protocol content. If you want to discuss the work or follow up about a role, reach me at [@nalediym](https://github.com/nalediym).
