# Plan: Simplify the Repo for Non-Technical Users

## Context

This repository has 48+ markdown files covering 21+ Claude Code concepts with heavy technical jargon ("frontmatter," "orchestration," "agentic loop," "context window"). There's no beginner guide, no glossary, and no concept hierarchy. A non-technical person landing on this repo would be overwhelmed. The goal is to create an accessible entry point without disrupting the existing advanced documentation.

## Approach: 3 New Files + 1 Small README Edit

```
claude-code-best-practice/
  START-HERE.md                    # NEW — root-level entry point (~60 lines)
  guides/
    beginner-guide.md              # NEW — progressive walkthrough (~150 lines)
    glossary.md                    # NEW — plain-English jargon definitions (~100 lines)
  README.md                       # MODIFIED — add 1 callout link near the top
```

### Why this approach
- A single file would be too long and intimidating
- Adding to README would bloat an already 28KB file
- Progressive files mirror how people learn: start simple, go deeper when ready
- Follows the repo's own "one topic per file" rule (`.claude/rules/markdown-docs.md`)

---

## File 1: `START-HERE.md` (repo root, ~60 lines)

Short enough to read in under 2 minutes. Answers three questions:

1. **What is Claude Code?** — 2 sentences, no jargon
2. **What is this repo?** — "A cookbook of tips and patterns"
3. **Where should I go?** — Links based on experience level

Includes **"5 Things You Need to Know"** — the 5 most important concepts (Memory, Commands, Skills, Sub-Agents, Hooks) explained with everyday analogies:
- CLAUDE.md → "a sticky note your AI reads every morning"
- Commands → "speed dial buttons"
- Skills → "instruction manuals Claude can pick up"
- Sub-Agents → "delegating to a coworker"
- Hooks → "automatic reactions, like a doorbell"

## File 2: `guides/beginner-guide.md` (~150 lines)

Progressive walkthrough in 3 levels:

**Level 1 — Essentials:** Talking to Claude, CLAUDE.md (memory), Commands (shortcuts)

**Level 2 — Doing More:** Skills, Sub-Agents, Weather Example re-explained in plain English
- The weather walkthrough is retold as 5 simple steps without mentioning "frontmatter," "YAML," or "orchestration"

**Level 3 — Power Features:** Brief mentions of Hooks, MCP, Settings, Checkpointing, Agent Teams, Voice Mode, Remote Control, Scheduled Tasks — one-line descriptions with links to advanced docs

## File 3: `guides/glossary.md` (~100 lines)

Alphabetical table of ~25 jargon terms with plain-English definitions. Key terms:
- Context Window, Frontmatter, Tokens, MCP, Orchestration, Agentic Loop, Worktree, Monorepo, YAML, Sandboxing, Progressive Disclosure, etc.

No definition uses another jargon term without that term also being in the glossary.

## File 4: `README.md` modification

Insert a blockquote callout after line 8 (after the badge row, before the CONCEPTS table):

```markdown
> **New to Claude Code?** Start with the [Beginner's Guide](START-HERE.md) — a plain-English introduction to everything in this repository.
```

Everything else in README stays untouched.

---

## Conventions Followed

| Rule (from `.claude/rules/markdown-docs.md`) | How |
|----------------------------------------------|-----|
| One topic per file | 3 files, 3 purposes (orientation, walkthrough, reference) |
| Relative links | All cross-file links use `../` relative paths |
| Back-navigation at top | Both `guides/` files use the existing table pattern with Claude mascot |
| Formatting hierarchy | Headings are hierarchical, no skipped levels |

---

## Files to Modify

| File | Action |
|------|--------|
| `START-HERE.md` | Create new |
| `guides/beginner-guide.md` | Create new |
| `guides/glossary.md` | Create new |
| `README.md` (line ~9) | Insert 2-line callout |

## Reference Files (read-only, for context during implementation)

- `README.md` — existing structure, badge patterns
- `orchestration-workflow/orchestration-workflow.md` — weather walkthrough to simplify
- `reports/claude-agent-command-skill.md` — command vs agent vs skill comparison
- `.claude/rules/markdown-docs.md` — documentation conventions
- `tips/claude-boris-13-tips-03-jan-26.md` — back-navigation pattern to match

## Verification

1. All relative links resolve correctly (no broken links)
2. `START-HERE.md` is visible in the GitHub file listing at repo root
3. README callout appears above the CONCEPTS table
4. Back-navigation links in guides/ work correctly
5. Glossary covers all jargon used in beginner-guide.md
6. No file exceeds 200 lines (per CLAUDE.md guidance)
