# Euler-resolve

A Claude Code plugin marketplace. Currently ships one plugin:

## euler-resolve

A structural framework for visual/artistic work of any kind (painting, drawing, illustration, UI/web design, branding, editorial layout).

It layers four things, checked in order — structure before surface:

1. **Mathematical foundations** — proportion systems (golden ratio, root rectangles), grids, symmetry groups, perspective, color-wheel relationships, WCAG contrast.
2. **Perception and biology** — Gestalt grouping, how the eye and fovea actually work, contrast sensitivity, pre-attentive processing, scan patterns, color perception, depth cues.
3. **Artistic principles** — balance, emphasis, rhythm, proportion, negative space, hierarchy.
4. **Anti-patterns ("negative design")** — a checklist of the specific, recurring mistakes that make visual work (especially AI-generated work) look generic, flat, or broken, with the reason each one happens and how to fix it.

## Structure

```
.claude-plugin/
└── marketplace.json                          # marketplace manifest
plugins/
└── euler-resolve/
    ├── .claude-plugin/
    │   └── plugin.json                       # plugin manifest
    └── skills/
        └── euler-resolve/
            ├── SKILL.md                       # entry point: when to use this, and the workflow
            └── references/
                ├── mathematical-foundations.md
                ├── perception-and-biology.md
                ├── artistic-principles.md
                ├── anti-patterns.md            # the "negative design" checklist
                └── application-guide.md        # condensed per-domain checklists
```

## Install

**Claude Code / Claude Cowork (plugin):**
```
/plugin marketplace add trinityman-hash/Euler-resolve
/plugin install euler-resolve@euler-resolve
```

**Manual (claude.ai Skills):**
Download the `plugins/euler-resolve/skills/euler-resolve` folder and add it as a skill in Claude (Settings → Capabilities → Skills).

This skill intentionally does not duplicate implementation guidance that already exists elsewhere — when a task requires writing actual code, it defers to `karpathy-guidelines` for how to write it (minimum code, surgical edits, no speculative config) and, in Claude.ai's environment, to `frontend-design` for concrete CSS/design-token constraints.
