# ui-quality Plugin

This plugin provides a UI/UX quality reviewer agent that checks frontend code for visual composition, style guide compliance, and modern UI patterns.

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
