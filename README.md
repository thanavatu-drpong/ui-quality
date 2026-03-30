# ui-quality

UI/UX quality toolkit for Claude Code — style guide creation and visual review.

---

## Overview

`ui-quality` is a Claude Code plugin that provides two agents for frontend UI quality:

1. **style-guide-creator** — An agent that generates a complete style guide for new projects through a friendly 8-question wizard. Produces a markdown style guide, tech-stack-specific token file, and automatic enforcement rule. Designed for non-technical users.

2. **ui-reviewer** — A proactive agent that reviews frontend code for visual composition, style guide compliance, and modern UI patterns. Runs on Sonnet after significant UI changes. Flags issues and waits for approval — never edits files.

---

## Installation

```
claude plugin install github.com/thanavatu-drpong/ui-quality
```

---

## Components

### style-guide-creator (Agent)

Generates a style guide through an 8-question wizard covering: project type, tech stack, brand colors, theme, typography, layout, content density, and charting.

**Outputs:**
- `style-guide/style-guide.md` — Complete design rules
- `style-guide/tokens.{css|js|ts|swift|dart}` — Token file matching your tech stack
- `.claude/rules/style-guide-enforcement.md` — Auto-loaded enforcement rule

**Trigger:** Ask "create a style guide" or "set up design system". Also suggested by ui-reviewer when no style guide exists.

**Company palette:** Optionally includes FCI/Dr.PONG brand palette (7 color groups, 56 shades). Not compulsory.

### ui-reviewer (Agent)

Proactive visual quality reviewer activated after significant frontend code changes.

**Review categories:**

| Category | What is reviewed |
|---|---|
| Layout correctness | Alignment, spacing, hierarchy |
| Spatial composition | Element grouping, space efficiency, visual balance |
| Style guide compliance | Colors, typography, component patterns |
| Visual consistency | Uniform spacing rhythm, semantic colors |
| Interactive states | Hover, loading, empty, disabled, focus |
| Modern UI suggestions | Non-blocking improvement ideas |

**Output:** Findings grouped as Must fix / Should fix / Suggest.

---

## Requirements

- Claude Code CLI installed and authenticated
- For full ui-reviewer capability: a style guide file in the project (use style-guide-creator to generate one)

---

## Scope and Boundaries

| Concern | Handled by |
|---|---|
| Style guide creation | `style-guide-creator` (this plugin) |
| Visual composition, spacing, color, typography, states | `ui-reviewer` (this plugin) |
| Code correctness, logic bugs, performance, security | `code-reviewer` (separate) |
| Initial design creation, layout generation | `frontend-design` skill (separate) |

---

## License

MIT
