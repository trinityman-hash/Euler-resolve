# Euler-resolve — Agent Instructions

This file follows the [AGENTS.md](https://agents.md) open standard, read natively by Codex, Cursor, GitHub Copilot, Windsurf, Aider, Zed, Amp, Devin, Jules, VS Code, JetBrains Junie, and most other coding agents. Claude Code and Claude.ai use the richer `SKILL.md` plugins in `plugins/` instead — see the main [README](README.md) for that install path.

**Scope note:** everything below applies *only* when the current task involves visual/artistic composition or web/product UI design (choosing colors, building a page or component, reviewing a design, answering "why does this look off / AI-generated"). For unrelated tasks (backend logic, data processing, general refactors), ignore this file's content below and proceed normally — don't inject design checklists into non-design work.

## If you're working inside this repository

This repo has no build or test commands — it's documentation (Markdown skill/plugin content) for `euler-resolve` (general visual composition) and `web-design-system` (web color systems + anti-slop checklists). If asked to edit a reference file, match the existing voice: concrete, specific, willing to state uncertainty (see `references/accessible-contrast-and-dark-mode.md` for the tone to match), never vague marketing language. Don't touch `.claude-plugin/` manifests unless the task is specifically about plugin metadata.

## If you pulled this file into your own project

This is the condensed, portable version of both skills. Full explanations, reasoning, and sourcing live in this repo's reference files, linked below — load this condensed version for fast application, load the full files when you need the "why."

### Composition (from `euler-resolve`)

Before finishing any visual/artistic work: pick a proportion system deliberately (don't eyeball placement), check it against perception (contrast, grouping, scan path — not just geometry), apply artistic principles (balance, emphasis, rhythm) to make it feel intentional, then run this checklist — for each item, state "not present" or "present, because [reason]":

1. Dead-center focal point with no reason to be centered
2. Uniform visual weight — nothing draws the eye first
3. Muddy value contrast — fails in grayscale
4. Drop shadow/glow applied by default, inconsistent light direction
5. Mechanically identical repetition in organic elements (foliage, crowds, texture)
6. Symmetry used everywhere, nothing asymmetric
7. Horror vacui — no breathing room around the focal point
8. Empty space with no compositional job
9. Elements colliding with the canvas edge unintentionally
10. Inconsistent perspective / multiple vanishing points
11. Inconsistent light source across the scene
12. Arbitrary, unrelated color choices
13. Every color pushed to max saturation, no rest points
14. Typographic hierarchy collapse — headings/body barely differ
15. Poor text legibility — centered body copy, bad line length
16. Contrast/accessibility neglect — color as the only signal
17. Trend effect applied with no functional reason
18. Anatomy/proportion drift with no stylistic intent
19. Element scale doesn't match its actual importance

Full detail: `plugins/euler-resolve/skills/euler-resolve/references/` (mathematical-foundations.md, perception-and-biology.md, artistic-principles.md, anti-patterns.md, application-guide.md).

### Color system + anti-AI-slop (from `web-design-system`)

Build color as a system, not ad hoc: pick a color space (OKLCH over HSL for scale/gradient work — perceptually uniform lightness), assign every color a semantic role (background/text/border/interactive/status), build the scale with one consistent model (Tailwind-style, Radix-style, or Material HCT — don't mix). Verify contrast against real WCAG 2.x numbers (4.5:1 normal text, 3:1 large text/UI boundaries) — APCA/WCAG3 is still unsettled, don't design to it instead of 2.x. Design dark mode as its own pass: desaturate saturated colors at dark-background lightness, avoid pure-black canvas, use lightness steps (not shadows) for elevation.

Then run this checklist against the actual output — mandatory, not optional, same rule: "not present" or "present, because [reason]":

**Visual/layout:**
1. Purple-to-blue gradient hero background
2. Glassmorphism as the default background (not one isolated element)
3. Bento grid used as furniture, not to encode real importance variance
4. Floating cards with a generic soft shadow applied to everything
5. Icon-in-rounded-square × 3/4 feature grid for non-parallel content
6. Generic "trusted by" logo strip under the hero
7. Testimonial carousel with vague, generic praise
8. Decorative gradient blobs with no relation to content
9. Center-everything layout on inherently asymmetric content
10. Uniform scroll-fade-in on every element, no variation
11. One border-radius value on every element regardless of role
12. Generic AI-illustration or stock photography disconnected from the product

**Typography/copy:**
1. Giant bold centered headline as the unexamined hero default
2. Inter (or whatever ships by default) unexamined for the entire type system
3. Gradient-fill text on headlines
4. Uniform font weight — size alone carrying the hierarchy
5. All-caps eyebrow label above every section
6. Generic marketing voice — copy that could describe any competitor unchanged
7. Title Case on every heading by reflex
8. Feature list padded to a round number

Full detail and sourcing: `plugins/web-design-system/skills/web-design-system/references/` (color-systems-for-web.md, accessible-contrast-and-dark-mode.md, anti-slop-visual-patterns.md, anti-slop-typography-and-copy.md, pre-ship-verification.md).

### Before calling it finished

Real computed contrast ratios (not eyeballed), a grayscale/colorblind check, both anti-slop checklists walked completely, and real content in every slot (no lorem ipsum) — see `pre-ship-verification.md` for the full gate.
