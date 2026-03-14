# Glossary

Plain-English definitions for terms used in this repository and Claude Code documentation.

<table width="100%">
<tr>
<td><a href="../START-HERE.md">← Back to Start Here</a> · <a href="../README.md">README</a></td>
<td align="right"><img src="../!/claude-jumping.svg" alt="Claude" width="60" /></td>
</tr>
</table>

---

| Term | What It Means |
|------|---------------|
| **Agent** | See *Sub-Agent*. |
| **Agent Teams** | Multiple copies of Claude working on different parts of the same project at the same time, like a team splitting up tasks. |
| **Agentic Loop** | The repeating cycle Claude follows: look at the situation, decide what to do, take action, check the result, and repeat until done. |
| **Checkpointing** | Claude automatically saves snapshots of your files as it works, so you can undo changes if something goes wrong. Press `Esc Esc` to rewind. |
| **CLI** | Command Line Interface — the text-based terminal window where you type commands instead of clicking buttons. |
| **CLAUDE.md** | A file you put in your project folder that gives Claude persistent instructions it reads at the start of every session. Like a sticky note for your AI assistant. |
| **Command** | A shortcut you type starting with `/` (e.g., `/weather-orchestrator`) to trigger a set of pre-written instructions. Like speed dial. |
| **Context Window** | The amount of conversation Claude can "remember" at once during a session. Think of it as short-term memory — it has a limit, and older parts get compressed when it fills up. |
| **Frontmatter** | Settings written at the very top of a file, between two `---` lines. It's how you configure commands, agents, and skills — like filling out a form header before the main content. |
| **Git Worktree** | A separate copy of your code that lets Claude (or you) work on a different version without affecting the main one. Used when multiple agents work in parallel. |
| **Hooks** | Small scripts that run automatically when specific events happen — like a doorbell that rings when someone arrives. Example: play a sound when Claude finishes a task. |
| **MCP (Model Context Protocol)** | A standard way to connect Claude to external tools like web browsers, databases, or APIs. Think of it as plugging in accessories. |
| **Model** | The AI brain powering Claude. Different models have different strengths: *Haiku* is fast, *Sonnet* is balanced, *Opus* is the most capable. |
| **Monorepo** | A single code repository that contains multiple projects or packages inside it, rather than using separate repositories for each. |
| **Orchestration** | Coordinating multiple components (commands, agents, skills) to complete a task together in sequence — like a conductor directing an orchestra. |
| **Permissions** | Rules controlling what Claude is allowed to do — edit files, run terminal commands, access the internet, etc. You approve or deny these as Claude works. |
| **Plugin** | A downloadable package that adds new skills, agents, hooks, or tools to Claude Code. Like installing an app on your phone. |
| **Progressive Disclosure** | Giving Claude only the information it needs for the current task, rather than dumping everything at once. Keeps things focused and efficient. |
| **Rules** | Instruction files in `.claude/rules/` that Claude follows automatically for specific file types or folders. Like house rules that apply in certain rooms. |
| **Sandboxing** | Restricting what Claude can access (files, network, commands) for safety. Like childproofing — it prevents accidental damage. |
| **Settings** | Configuration files (`.claude/settings.json`) that control how Claude Code behaves — permissions, which model to use, what tools are available, and more. |
| **Skill** | A bundle of instructions that teaches Claude how to do something specific. Stored in `.claude/skills/`. Think of it as an instruction manual Claude can pick up and follow. |
| **Sub-Agent** | An independent copy of Claude that handles a specific subtask and reports back. Like delegating a job to a coworker — they work separately and return with the result. |
| **Tokens** | The units Claude uses to measure text. Roughly 1 token = 3/4 of a word. Used to calculate costs and context window usage. |
| **YAML** | A simple text format for configuration, using `key: value` pairs. Used in frontmatter. Pronounced "YAM-ul." |

---

<p align="center"><a href="beginner-guide.md">← Beginner's Guide</a> · <a href="../START-HERE.md">Start Here</a> · <a href="../README.md">README</a></p>
