# Euler-resolve

A Claude Code plugin marketplace containing one plugin: `euler-resolve`.

## What it does

`euler-resolve` is a skill that gives Claude a structural framework for visual and artistic work, including painting, illustration, UI and web design, branding, and editorial layout. It is organized into four layers, applied in order:

1. **Mathematical foundations** - proportion systems, grid structures, symmetry groups, perspective, color-wheel relationships, contrast ratios.
2. **Perception and biology** - Gestalt grouping, eye physiology, contrast sensitivity, scan patterns, depth cues.
3. **Artistic principles** - balance, emphasis, rhythm, negative space, hierarchy.
4. **Anti-patterns** - a checklist of recurring mistakes in visual work, including patterns common in AI-generated output, with the cause and fix for each.

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
                ├── anti-patterns.md
                └── application-guide.md        # per-domain checklists
```

## Installation

**Claude Code / Claude Cowork:**
```
/plugin marketplace add trinityman-hash/Euler-resolve
/plugin install euler-resolve@euler-resolve
```

**Manual (claude.ai Skills):**
Download the `plugins/euler-resolve/skills/euler-resolve` folder and add it under Settings > Capabilities > Skills.

## Notes

This skill does not duplicate implementation guidance that already exists elsewhere. For how to write code once a visual spec is decided, it defers to `karpathy-guidelines`. In claude.ai's environment, it also defers to `frontend-design` for the available CSS and design-token constraints.
