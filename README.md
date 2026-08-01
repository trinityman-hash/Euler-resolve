# Euler-resolve

A Claude skill: **artistic-design-hierarchy** — a structural framework for visual/artistic work of any kind (painting, drawing, illustration, UI/web design, branding, editorial layout).

It layers four things, checked in order — structure before surface:

1. **Mathematical foundations** — proportion systems (golden ratio, root rectangles), grids, symmetry groups, perspective, color-wheel relationships, WCAG contrast.
2. **Perception and biology** — Gestalt grouping, how the eye and fovea actually work, contrast sensitivity, pre-attentive processing, scan patterns, color perception, depth cues.
3. **Artistic principles** — balance, emphasis, rhythm, proportion, negative space, hierarchy.
4. **Anti-patterns ("negative design")** — a checklist of the specific, recurring mistakes that make visual work (especially AI-generated work) look generic, flat, or broken, with the reason each one happens and how to fix it.

## Structure

```
artistic-design-hierarchy/
├── SKILL.md                              # entry point: when to use this, and the workflow
└── references/
    ├── mathematical-foundations.md
    ├── perception-and-biology.md
    ├── artistic-principles.md
    ├── anti-patterns.md                  # the "negative design" checklist
    └── application-guide.md              # condensed per-domain checklists
```

## Install

Download the `artistic-design-hierarchy` folder and add it as a skill in Claude (Settings → Capabilities → Skills, or the equivalent in Claude Code/Cowork).

This skill intentionally does not duplicate implementation guidance that already exists elsewhere — when a task requires writing actual code, it defers to `karpathy-guidelines` for how to write it (minimum code, surgical edits, no speculative config) and, in Claude.ai's environment, to `frontend-design` for concrete CSS/design-token constraints.
