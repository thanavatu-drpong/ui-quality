# ui-quality Plugin

This plugin provides UI/UX quality tools for frontend development: a style guide creator and a visual quality reviewer.

## Agent: style-guide-creator

Generates a complete style guide for new projects through an 8-question guided wizard. Designed for non-technical users — every question includes plain-language explanations and real-world examples.

### When to use

- Starting a new project that needs a style guide
- When ui-reviewer reports no style guide found

### What it produces

- `style-guide/style-guide.md` — Complete design rules document
- `style-guide/tokens.{ext}` — Token file matching your tech stack (CSS vars, JS module, etc.)
- `.claude/rules/style-guide-enforcement.md` — Ensures Claude follows the guide automatically

### Company palette

Optionally uses the FCI/Dr.PONG brand palette (7 color groups with full shade ramps). Not compulsory — users can define their own colors.

## Agent: ui-reviewer

Activated proactively after significant frontend/UI code changes. Reviews visual quality only — not code logic (use code-reviewer for that).

### Requirements

A style guide file must exist in the project for full review capability. The agent searches for files matching: `*style-guide*`, `*design-system*`, `*style*guide*`.

### What it checks

1. Layout correctness (alignment, spacing, hierarchy)
2. Spatial composition (element grouping, space efficiency, visual balance)
3. Style guide compliance (colors, fonts, component patterns)
4. Visual consistency (uniform elements, spacing rhythm, semantic colors)
5. Interactive states (hover, loading, empty, disabled, focus)
6. Modern UI suggestions (non-blocking)

### Output

Findings grouped as Must fix / Should fix / Suggest. The agent flags issues and waits for approval — it never makes changes itself.

