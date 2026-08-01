---
name: euler-resolve
description: A structural framework for any visual/artistic task — painting, drawing, illustration, sketching, character or environment design, poster/editorial layout, branding and logo work, UI/UX and web design, or general "make this look better" requests. Combines mathematical composition frameworks (golden ratio, grids, symmetry, perspective), human visual perception and biology (Gestalt principles, eye anatomy, contrast sensitivity, color perception), classical artistic principles (balance, hierarchy, rhythm, unity), and a "negative design" checklist of the specific mistakes AI-generated visuals commonly make. Use this whenever a request involves creating, critiquing, or improving anything visual — including when the user asks why a design "looks off," "looks AI-generated," or "looks amateur," even if they don't name a specific technique.
---

# Euler-resolve

## What this is

Good visual work is not one skill — it's several layers stacked in a specific order. A composition can be mathematically well-structured and still fail perceptually (the eye never lands where the point is). It can be perceptually sound and still fail artistically (technically legible but lifeless). And it can pass every rule in this file and still look wrong, because it's making one of a small number of very common, very fixable mistakes.

This skill organizes those layers so you check them in the order that actually matters: **structure before surface**. Decide the skeleton (proportions, grid, hierarchy) before you decide the skin (color, texture, decoration). Most AI-generated and amateur work fails not because the details are bad, but because the structural decisions were never made explicitly — everything was decided at the same time, at the same level, which is why it tends to come out visually flat or centered-and-symmetric by default.

None of the references here are laws. They're defaults with known reasons behind them. A skilled artist breaks any of them on purpose, all the time. The failure mode this skill guards against is breaking them *by accident*, out of not having made a structural decision at all.

## Reference files

Load these as needed — don't pull all of them into context for a trivial request.

| File | Load it when... |
|---|---|
| `references/mathematical-foundations.md` | You need to choose a compositional structure: grid, proportion system, ratio, perspective, symmetry, or color-wheel relationship. |
| `references/perception-and-biology.md` | You need to check *where the eye will actually go* and whether the hierarchy will physically read — Gestalt grouping, contrast, eye-scan patterns, depth cues. |
| `references/artistic-principles.md` | You're deciding how to express the structure — balance, emphasis, rhythm, negative space, unity vs. variety. |
| `references/anti-patterns.md` | Always, before calling a piece finished. This is the "negative design" checklist — the specific, recurring mistakes that make work (especially AI-generated work) look generic, flat, or broken. |
| `references/application-guide.md` | You want the condensed per-domain checklist (painting, web/UI, branding, editorial) instead of re-deriving it from the four files above. |

## Workflow

For anything beyond a trivial/quick request, work through these steps. State which structural choices you're making — don't decide them silently, and don't apply them silently either; a one-line note ("using a rule-of-thirds grid with the focal point at the lower-right intersection") costs nothing and lets the user correct course before you've built on top of it.

1. **Identify the medium and constraints.** Static or interactive? Physical or digital? Fixed canvas or responsive? This determines which parts of `mathematical-foundations.md` even apply (e.g., WCAG contrast ratios matter for UI, not for oil painting).

2. **Choose one structural framework, deliberately.** Pick a proportion system or grid from `mathematical-foundations.md` and commit to it rather than eyeballing placement. If you don't have a specific reason to deviate, a grid/ratio-based structure will consistently outperform ad hoc placement.

3. **Check it against perception, not just geometry.** A mathematically centered focal point isn't automatically where the eye lands first. Cross-reference `perception-and-biology.md` for contrast, grouping, and scan-path — these are what actually route attention, math just gives you candidate positions.

4. **Apply artistic principles to give it life.** Structure and perception get you "correct." `artistic-principles.md` is what makes it feel intentional rather than mechanical: where balance is asymmetrical instead of static, where rhythm varies instead of repeating identically, where negative space is doing work instead of just being empty.

5. **Run the anti-pattern audit before finishing.** This is the mandatory verification step — treat it the way you'd treat running tests before declaring code done. Go through `references/anti-patterns.md` and check the piece against each item. This is where most of the "why does this look AI-generated" problems get caught.

6. **If the deliverable is code** (a web page, a UI component, a generative piece), the visual decisions above tell you *what* to build. *How* you build it follows `karpathy-guidelines`: minimum code that achieves the visual spec, no speculative configurability, surgical edits if you're modifying existing code. If you're working in this environment's React/HTML artifacts, also check `frontend-design` for the concrete CSS tokens and constraints available here — this skill tells you the design should have an asymmetrical focal point in the upper third; `frontend-design` tells you which utility classes are actually available to build it.

## Success criteria

Before presenting finished visual work, you should be able to answer all of these:

- What is the single focal point, and what three things (contrast, position, isolation, scale, color, direction) make it read first?
- What structural system (grid/ratio/symmetry) governs the placement, and is it applied consistently or violated on purpose?
- Does the value/contrast structure work if you squint or view it in grayscale?
- Have you gone through `anti-patterns.md` and can you say, for each item, either "not present" or "present on purpose, because..."?
- If there's text or a UI element: does it meet basic legibility/contrast requirements for its context?

Weak success criteria ("make it look good") force you to keep guessing and re-generating. Answering the questions above turns "good" into something you can actually check.

## Scope note

This skill is about visual/compositional judgment. It doesn't replace domain literacy you don't have — if a task needs accurate anatomy, architecture, or engineering (a real building's structural mathematics, a real species' biology), verify those specifics separately; this framework governs composition and perception, not factual correctness of subject matter.
