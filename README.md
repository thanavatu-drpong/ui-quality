# ui-quality

UI/UX quality reviewer agent for Claude Code

---

## Overview

`ui-quality` is a Claude Code plugin that adds a proactive UI/UX review agent to your development workflow. After significant frontend changes, the `ui-reviewer` agent automatically inspects your code for visual composition issues, style guide violations, and gaps in modern UI patterns. It produces a structured, prioritized findings report — grouped into Must fix, Should fix, and Suggest — and waits for your approval before any action is taken. The agent never edits files; its sole purpose is to surface issues that are easy to miss during implementation but matter for the end user experience.

---

## Installation

```
claude plugin install github.com/thanavatu-drpong/ui-quality
```

---

## Features

| Category | What is reviewed |
|---|---|
| **Layout correctness** | Alignment, spacing, and visual hierarchy across components and pages |
| **Spatial composition** | Element grouping, use of whitespace, and overall visual balance |
| **Style guide compliance** | Color usage, typography, component patterns — checked against your project style guide |
| **Visual consistency** | Uniform spacing rhythm, consistent component styling, correct application of semantic colors |
| **Interactive states** | Presence and correctness of hover, loading, empty, disabled, and focus states |
| **Modern UI suggestions** | Non-blocking observations on contemporary UI patterns and potential improvements |

---

## Requirements

- Claude Code CLI installed and authenticated
- A style guide file present in the project for full review capability

The agent searches for files matching the patterns: `*style-guide*`, `*design-system*`, `*style*guide*`. Without a matching file, the agent performs a best-effort review using general UI/UX principles but cannot check project-specific color, typography, or component standards.

---

## How it works

1. The `ui-reviewer` agent is activated proactively after significant frontend or UI code changes are detected in a session.
2. The agent runs on Claude Sonnet for balanced speed and quality.
3. It reads the modified files and any discovered style guide, then produces a structured findings report.
4. Findings are grouped as **Must fix** (violations that will be visually broken or inaccessible), **Should fix** (inconsistencies or missing states that degrade quality), and **Suggest** (non-blocking improvement ideas).
5. The agent flags issues and waits for your explicit approval — it never applies changes itself.

---

## Scope and boundaries

This plugin focuses exclusively on visual and UX quality. Use it alongside, not instead of, a code reviewer and a dedicated design tool.

| Concern | Handled by |
|---|---|
| Visual composition, spacing, color, typography, component states | `ui-reviewer` (this plugin) |
| Code correctness, logic bugs, performance, security | `code-reviewer` (separate plugin) |
| Initial design creation, layout generation, component scaffolding | `frontend-design` skill |

---

## License

MIT
