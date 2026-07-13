# Claude Skills for Leaders

A small collection of ready-to-use Claude Skills for the recurring writing work of running a company: board updates, decision memos, meeting debriefs, and weekly briefs.

If this is the first time you've opened a GitHub repository, welcome — this page will walk you through everything, no prior technical experience assumed.

## What is this place?

This is a **GitHub repository** (or "repo" for short) — basically a folder of files, stored online, that can be shared, downloaded, and updated over time. Right now it contains four text files. Each one teaches Claude how to do a specific writing task the way you'd want it done, instead of generically.

You don't need to know anything about coding to use what's in here.

## What is a "Claude Skill"?

Normally, when you ask Claude for something like "write a board update," you have to re-explain your format, your tone, and what to include — every single time.

A **Skill** is a saved set of instructions that teaches Claude how to do one specific task well, once, so you don't have to re-explain it. Each skill in this repo is a single file (`SKILL.md`) that tells Claude:

- What the task is and when to use this skill
- What information to ask you for if you haven't given enough
- Exactly what format the output should follow
- Rules for tone and voice (so it sounds like you, not like generic AI writing)
- A worked example, so Claude has a concrete pattern to follow

Once a skill is loaded into Claude, you can just say "use the decision memo skill on this" and hand it your messy notes — Claude does the rest.

## What's in this repo

| Skill | Use it when... |
|---|---|
| [`board-investor-update`](skills/board-investor-update/SKILL.md) | You need to turn metrics and notes into a board meeting narrative or investor update email |
| [`decision-memo`](skills/decision-memo/SKILL.md) | You're weighing a decision and want to pressure-test it, or need to explain a decision you've made to your team or board |
| [`meeting-debrief-actions`](skills/meeting-debrief-actions/SKILL.md) | You just left a meeting with a transcript or messy notes and need decisions, owners, deadlines, and a follow-up message |
| [`weekly-exec-brief`](skills/weekly-exec-brief/SKILL.md) | It's the start of the week and you have a pile of updates, Slack threads, and metrics to turn into one brief for your leadership team |
| [`grill-me`](skills/grill-me/SKILL.md) | You have a plan or a design and want someone to interview you on it, question by question, until every weak spot is found before you commit to it |

Each skill file is plain text (written in a format called Markdown) — you can click any of the links above right now to open it and read exactly what it does. Nothing in it is hidden or complicated; it reads like a very detailed instruction sheet.

## How to actually use these skills

There are two common ways to use Claude, so pick whichever matches how you already work. If you're not sure, use **Option A** — it's the one built for non-technical use.

### Option A: Using Claude.ai (the website or desktop app)

This is the simplest path if you just chat with Claude normally.

1. **Download the skill files to your computer.**
   - At the top of this repository's page on GitHub, click the green **`<> Code`** button, then click **Download ZIP**.
   - Find the downloaded ZIP file (usually in your Downloads folder) and unzip it (double-click it on Mac; right-click → "Extract All" on Windows).
   - Inside, you'll find a `skills` folder containing one subfolder per skill, each with a `SKILL.md` file.
2. **Add a skill to Claude.**
   - Go to [claude.ai](https://claude.ai) and log in.
   - Open **Settings → Capabilities** (or look for a **Skills** section — Anthropic occasionally moves this, so if you can't find it, search "Claude Skills" in Claude's help center).
   - Choose to add/upload a new skill, and select the `SKILL.md` file (or its folder) for the skill you want — for example, `skills/decision-memo/SKILL.md`.
   - Repeat for each skill you want available.
3. **Use it in a conversation.**
   - Start a new chat, turn the skill on if prompted, and just describe your task — e.g., paste your rough notes and say *"use the decision-memo skill to write this up."*
   - Claude will ask you for anything it's missing (see each skill's "What to ask for if the input is incomplete" section) before producing the final document.

### Option B: Using Claude Code (for technical teammates)

If someone on your team uses Claude Code (Anthropic's command-line tool), they can make these skills available by copying the `skills` folder from this repo into a `.claude/skills/` folder in their project, or into `~/.claude/skills/` to make them available everywhere. If this doesn't mean anything to you, that's fine — hand this repo's link to whoever on your team does development work, or just use Option A above.

## Customizing a skill for your own voice

These skills are starting points, not fixed templates. Each `SKILL.md` file has a **Voice rules** section and an **Output format** section you can edit directly:

- Open the file (either on GitHub by clicking it, or in the unzipped folder on your computer, using any text editor like Notepad or TextEdit).
- Edit the plain-English instructions — for example, change "One page, no longer than ~400 words" to whatever length actually works for your board.
- Save the file, and re-upload it to Claude if you're using Option A.

You don't need to know how to code to edit these — it's all plain instructions, the same as editing a Word document.

## Keeping this repo updated

If you or a teammate improve a skill (tighten the voice rules, fix an example), the changes should be saved back to this repository so everyone is always working from the same version, rather than emailing files around. If you're not comfortable with GitHub's "commit and push" process yet, the easiest path is to ask a technical teammate to make the update for you, or ask Claude directly — it's good at walking non-technical users through basic GitHub steps one command at a time.

## Questions

If a skill isn't producing what you expect, the most common fix is giving it better raw input — check the "What to ask for if the input is incomplete" section at the top of the relevant `SKILL.md` file to see what Claude needs from you to do its best work.
