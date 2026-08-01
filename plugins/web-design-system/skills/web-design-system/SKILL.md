---
name: web-design-system
description: A color system and anti-slop negative-design framework specifically for web and product UI work — use whenever a task involves choosing colors, building or auditing a design system/token set, implementing dark mode, or building any web page, landing page, dashboard, or UI component. Also use whenever the user asks why a web design "looks AI-generated," "looks like every other SaaS site," "looks generic," or asks for a design that stands out. Covers perceptually-uniform color theory (OKLCH), semantic/functional color tokens, color scale construction, WCAG contrast and current APCA/WCAG3 status, dark mode as a genuine redesign rather than an inversion, and two forceful negative-design checklists (visual/layout and typography/copy) naming the specific, currently-overused AI-generated web design defaults — gradient hero backgrounds, glassmorphism-as-default, bento-grid-as-default, floating shadow cards, Inter-and-giant-centered-headline, vague copy — to be treated as defaults to avoid unless deliberately justified.
---

# Web Design System (Color + Anti-Slop)

## What this is

Two problems that compound, addressed as one discipline.

First: on the web, color is usually chosen ad hoc — a hex code here, a slightly-off shade picked to "look about right" there — instead of engineered as a system. That's why so many interfaces have inconsistent button states, muddy dark modes, and text that fails contrast nobody checked.

Second: since roughly 2024, a large share of AI-generated web design has converged on the same handful of defaults — a purple-to-blue gradient hero, glassmorphism applied everywhere instead of on one element, a bento grid used as furniture instead of as a hierarchy tool, floating cards with an identical soft shadow, Inter set huge and centered above two lines of vague aspiration, feature grids padded to a round number. This isn't a vague aesthetic complaint anymore; it's specific and nameable enough that design communities routinely list the exact patterns (see `anti-slop-visual-patterns.md` and `anti-slop-typography-and-copy.md`). It happens because those patterns are the statistical average of the training data — the safest, most inoffensive choice — not because anyone decided they were right for a specific product.

This skill treats both problems the same way `euler-resolve` treats general composition: build the structure deliberately, then run a specific, named checklist before calling it finished. The difference is that this skill is scoped to the web/product medium specifically, where color is a system with real technical constraints (contrast math, color spaces, browser support) and where the anti-pattern list is time-bound to what's actually overused right now, not a timeless principle.

## Reference files

| File | Load it when... |
|---|---|
| `references/color-systems-for-web.md` | You're choosing or building a color system: color spaces, semantic/functional tokens, scale construction, harmony for UI specifically, gradients. |
| `references/accessible-contrast-and-dark-mode.md` | You need real contrast numbers, the current WCAG/APCA status, colorblind-safety checks, or you're building (not just inverting) a dark mode. |
| `references/anti-slop-visual-patterns.md` | Always, before shipping any web/product visual or layout work. The layout/visual negative-design checklist. |
| `references/anti-slop-typography-and-copy.md` | Always, before shipping. The typography and copy-voice negative-design checklist — separate from visual patterns because it's a distinct, equally-common failure mode. |
| `references/pre-ship-verification.md` | The final gate. Run this before presenting any web/product design as finished. |

## Workflow

1. **Establish the color system deliberately.** Load `color-systems-for-web.md` before picking colors. Don't choose hex codes ad hoc and don't skip straight to "make it look nice" — decide the color space, the token roles, and the scale approach first.
2. **Verify contrast and dark-mode strategy as part of building the system**, not as an afterthought bolted on at the end. Load `accessible-contrast-and-dark-mode.md`.
3. **Build the actual layout, components, and copy.**
4. **Run both anti-slop checklists against the real output — mandatory, not optional.** For every item in `anti-slop-visual-patterns.md` and `anti-slop-typography-and-copy.md`, you must be able to say either "not present" or "present, because [specific reason tied to this brief]." Silently having three of these patterns land in the output because they were the path of least resistance is exactly the failure mode this skill exists to catch — treat the checklist as something you actively refute, not skim.
5. **Run `pre-ship-verification.md` as the final gate** before telling the user the work is done.

## How this relates to the rest of this marketplace and environment

`euler-resolve` (the sibling plugin here) covers general compositional and artistic judgment — proportion, perception, balance, focal point — independent of medium. This skill is the web/product-specific layer on top of it: use `euler-resolve` to check whether something composes well at all; use this skill to check whether the color system is actually engineered (versus guessed) and whether the result reads as generic AI output.

For how the code itself gets written once the visual/color decisions are made, defer to `karpathy-guidelines` (minimum code, surgical edits, no speculative config). In this environment's React/HTML artifacts, defer to `frontend-design` for the concrete CSS tokens and utility constraints actually available here.

## Success criteria

- Every color used has a defined *role* (background/surface, text, border, interactive state, semantic status) at a stated emphasis level — not just a color that was picked because it looked fine.
- Every text/background and icon/background pair meets WCAG contrast for its role, checked with an actual computed ratio, not by eye.
- If dark mode is claimed, it was designed as its own pass (surface elevation, adjusted chroma, no pure-black canvas) — not generated by inverting the light palette.
- You can name, for every item on both anti-slop checklists, either its absence or the specific reason it's present.

## Scope note

The anti-slop lists in this skill are deliberately opinionated and dated — they name what's specifically overused as of 2026, not eternal design law. Trends shift; a pattern listed here as an unmotivated default could become a genuinely correct choice for a specific brief. The requirement isn't that these patterns are permanently banned, it's that using one has to be a stated decision, not something that happened because it was the statistically safest output.
