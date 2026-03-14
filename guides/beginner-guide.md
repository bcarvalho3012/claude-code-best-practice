# Beginner's Guide to Claude Code

Everything you need to know, explained without jargon. Start at Level 1 and work your way up.

<table width="100%">
<tr>
<td><a href="../START-HERE.md">← Back to Start Here</a> · <a href="../README.md">README</a></td>
<td align="right"><img src="../!/claude-jumping.svg" alt="Claude" width="60" /></td>
</tr>
</table>

---

## Level 1: The Essentials

### Talking to Claude

Open your terminal (the text window on your computer), type `claude`, and press Enter. That's it — you're in. Now type what you want in plain English:

- "Fix the bug in my login page"
- "Add a dark mode toggle"
- "Explain what this function does"

Claude reads your files, writes code, and runs commands — you just describe what you want.

### Giving Claude a Memory (CLAUDE.md)

Every time you start a new session, Claude starts fresh. But if you create a file called `CLAUDE.md` in your project folder, Claude reads it automatically at the beginning of every session.

Think of it as a sticky note on your desk that Claude checks every morning. You can write things like:

- "This project uses Python 3.11 and PostgreSQL"
- "Always write tests for new functions"
- "Never modify files in the /legacy/ folder"

Keep it short — under 200 lines works best.

### Using Shortcuts (Commands)

Instead of typing long instructions every time, you can create shortcuts called **commands**. You trigger them by typing `/` followed by the command name.

For example, this repository has a command called `/weather-orchestrator`. When you type it, Claude automatically runs a multi-step weather-fetching workflow — no need to explain each step.

To create your own command, add a markdown file to `.claude/commands/` in your project. The filename becomes the shortcut name.

---

## Level 2: Doing More

### Teaching Claude New Tricks (Skills)

Skills are instruction manuals that Claude can pick up and follow. They live in `.claude/skills/` folders inside your project.

Some skills are **automatic** — Claude discovers and uses them when it recognizes a relevant task. Others you trigger manually, like commands.

For example, the `weather-svg-creator` skill in this repo knows exactly how to create a visual weather card. When Claude needs to make one, it follows the skill's instructions step by step.

### Delegating Work (Sub-Agents)

When Claude has a complex task, it can create an independent copy of itself — called a **sub-agent** — to handle a specific piece of work. The sub-agent works separately and reports back with the result.

Why not just do everything in one conversation? Because sub-agents keep things clean. Each one focuses on one job without getting confused by unrelated context. It's like asking a coworker to handle one part of a project while you focus on another.

Sub-agents can have their own skills, permissions, and even use different AI models. You define them in `.claude/agents/` files.

### Seeing It All Together: The Weather Example

This repository includes a working example that shows how commands, agents, and skills work together. Here's what happens when you type `/weather-orchestrator`:

1. **Claude asks you a question** — "Do you want the temperature in Celsius or Fahrenheit?"
2. **You answer** — pick one
3. **A sub-agent goes to work** — it fetches the current temperature for Dubai from the internet, following instructions from its preloaded skill
4. **The sub-agent reports back** — "It's 26°C"
5. **A skill creates the output** — a visual weather card (SVG image) and a summary file

The pattern here is: **Command starts it** (handles your input) **→ Agent does the work** (fetches data) **→ Skill produces the output** (creates the visual). This "Command → Agent → Skill" pattern is reusable for all kinds of workflows.

---

## Level 3: Power Features

These are more advanced capabilities. You don't need them to get started, but they're good to know about.

### Automatic Actions (Hooks)

Hooks are scripts that run automatically when specific events happen — like a doorbell ringing when someone arrives. In this repository, sound effects play when Claude finishes tasks, starts working with a sub-agent, or makes a git commit.

You configure hooks in `.claude/settings.json`. See the [hooks directory](../.claude/hooks/) for examples.

### Connecting to External Tools (MCP Servers)

MCP (Model Context Protocol) lets Claude connect to tools beyond your local files — web browsers, documentation services, databases, and more. Think of it as plugging in accessories.

This repo connects to tools like [Playwright](https://playwright.dev/) (browser automation) and [Context7](https://context7.com/) (documentation lookup). Configuration lives in `.mcp.json`. See [claude-mcp.md](../best-practice/claude-mcp.md) for details.

### Settings and Permissions

Claude Code's behavior is controlled by settings files. The main one is `.claude/settings.json` in your project. It controls what Claude can do automatically vs. what requires your approval.

There's a hierarchy: team settings (shared) vs. personal settings (your overrides). See [claude-settings.md](../best-practice/claude-settings.md) for the full reference.

### Other Features Worth Knowing

| Feature | What It Does |
|---------|-------------|
| **Checkpointing** | Claude saves snapshots as it works — press `Esc Esc` to undo changes |
| **Agent Teams** | Multiple sub-agents working in parallel on the same project |
| **Voice Mode** | Talk to Claude instead of typing |
| **Remote Control** | Continue your Claude session from a different device |
| **Scheduled Tasks** | Have Claude repeat a task on a schedule (e.g., check a deployment every 5 minutes) |
| **Code Review** | Claude analyzes pull requests for bugs and issues |

---

## What to Explore Next

- [The Weather Workflow](../orchestration-workflow/orchestration-workflow.md) — the full technical walkthrough of the example above
- [Tips and Tricks](../README.md#-tips-and-tricks) — practical advice from Claude Code's creators
- [Reports](../README.md#reports) — deep dives on specific topics
- [Glossary](glossary.md) — look up any term you don't recognize

---

<p align="center"><a href="../START-HERE.md">Start Here</a> · <a href="glossary.md">Glossary</a> · <a href="../README.md">README</a></p>
