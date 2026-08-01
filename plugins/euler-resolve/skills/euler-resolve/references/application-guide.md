# Application Guide

Condensed per-domain checklists. Each still traces back to the four core reference files — this is just the shortcut so you don't have to re-derive it every time.

## Painting / drawing / illustration

1. Structure: pick a proportion system (mathematical-foundations.md) for the canvas before placing the subject.
2. Light: one consistent light source, derive all shadows/highlights from it (perception-and-biology.md, depth cues; anti-pattern #11).
3. Depth: layer occlusion, relative size, and atmospheric perspective together rather than relying on one cue alone.
4. Anatomy/reference accuracy: check proportion drift (anti-pattern #18) against real reference before stylizing.
5. Value pass: verify the composition reads in grayscale before finishing color (anti-pattern #3).
6. Organic detail: vary repeated elements (foliage, texture, crowd figures) within a range, not identically (anti-pattern #5).

## Web / UI / product design

1. Grid: establish a column grid and modular type/spacing scale before placing components (mathematical-foundations.md).
2. Hierarchy: one primary action per screen/section; verify size/weight/color differences clear the ~1.5x distinction floor (anti-pattern #14).
3. Contrast: check actual WCAG contrast ratios on text and interactive elements, not just perceived brightness (anti-pattern #16).
4. Scan pattern: align key content (nav, primary CTA) with the natural entry point for the reading direction (perception-and-biology.md).
5. Negative space: don't crowd the viewport edge-to-edge; give the primary action room (anti-pattern #7).
6. If implementing in code in this environment: use `frontend-design` for the concrete design tokens/CSS constraints available, and `karpathy-guidelines` for how to write the implementation itself once the visual spec is decided — minimum code, no speculative props/config that wasn't asked for.

## Branding / logo design

1. Symmetry choice is a message: bilateral symmetry reads stable/formal, asymmetry reads dynamic/energetic (perception-and-biology.md) — pick deliberately based on what the brand should communicate.
2. Must work at small scale and in a single color — simplify until the focal shape survives both constraints.
3. Negative space is often the differentiator (artistic-principles.md) — check whether an implied secondary shape in the negative space adds value or is just noise.
4. Avoid trend-as-crutch (anti-pattern #17): a logo built on a current effect (gradients, 3D bevels) ages out fast; check it still works as a flat, timeless mark.

## Poster / editorial / print layout

1. One focal point, established via contrast/isolation/convergence, not several competing ones (artistic-principles.md, anti-pattern #2).
2. Typographic hierarchy: headline/subhead/body should clear the modular-scale distinction floor (anti-pattern #14); avoid centered body paragraphs (anti-pattern #15).
3. Margins: consistent margins signal intentionality; edge collisions read as accidental unless bleed is clearly deliberate (anti-pattern #9).
4. Rhythm across a spread/series: use progressive or alternating rhythm (artistic-principles.md) rather than identical repetition if the goal is to keep attention across multiple pieces.

## Before delivering anything from any domain

Run the full checklist in `anti-patterns.md`. This step is what catches the "technically fine but reads as generic/AI-generated" failure mode — it's rarely one big thing, usually two or three small unaudited defaults (centered focal point + uniform weight + arbitrary color, for example) stacking together.
