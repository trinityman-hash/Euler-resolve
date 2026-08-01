# Anti-Patterns (Negative Design Implementation)

This is the verification checklist — run it before calling any visual work finished. Each item names the symptom, why it tends to happen (especially in AI-generated or rushed work), which rule from the other reference files it's actually violating, and the fix. The goal isn't to ban any of these outright — every one of them is sometimes the right choice — it's to make sure it's a *choice* and not a default.

### 1. Dead-center gravity
**Symptom**: subject/focal point sits exactly in the middle of the frame with no compositional reason to. **Why it happens**: centering is the path of least resistance — it requires no decision. **Violates**: rule of thirds / golden ratio placement (mathematical-foundations.md). **Fix**: shift the focal point to a power point unless dead center is specifically motivated (formal portraiture, iconography, a UI element that genuinely needs bilateral symmetry).

### 2. Uniform visual weight
**Symptom**: nothing draws the eye first; every element competes equally. **Why it happens**: every element got the same amount of "importance effort" during creation instead of one being deliberately pushed forward. **Violates**: emphasis/focal point (artistic-principles.md) and pre-attentive processing (perception-and-biology.md) — if everything is pre-attentively distinct, nothing wins. **Fix**: pick the single primary focal point and deliberately subordinate everything else on whatever channel (contrast, scale, saturation) it's using.

### 3. Muddy value contrast
**Symptom**: elements sit in a narrow midtone band and blur together, especially visible in grayscale. **Why it happens**: color was tuned for hue/mood without checking value/lightness separately. **Violates**: contrast sensitivity and figure-ground grouping (perception-and-biology.md). **Fix**: check the piece desaturated; the hierarchy should still read.

### 4. Gradient/glow/shadow as a default depth crutch
**Symptom**: every element gets a drop shadow or glow regardless of whether it's motivated, often with inconsistent direction/intensity from element to element. **Why it happens**: it's a cheap way to fake depth without deciding an actual light source. **Violates**: consistent light direction (perception-and-biology.md, depth cues). **Fix**: pick one light source/direction for the whole piece and derive shadows from it; drop the effect entirely where it isn't earning its place.

### 5. Mechanically perfect repetition in organic elements
**Symptom**: leaves, rocks, hair, clouds, crowd figures that are exact or near-exact copies of each other. **Why it happens**: repetition is computationally/effort cheap; controlled variance is not. **Violates**: natural/fractal statistical self-similarity (mathematical-foundations.md) — real organic variance is random-within-a-range, not identical. **Fix**: vary scale, rotation, and spacing of repeated organic elements within a defined range rather than reusing one instance unmodified.

### 6. Symmetry used everywhere
**Symptom**: every element and the overall composition are all mirrored, flattening the piece into something static throughout. **Why it happens**: symmetry is an easy default that always "looks correct" at a glance. **Violates**: balance (artistic-principles.md) — symmetry is one tool for balance, not the only one, and using it everywhere removes the dynamic/energetic register entirely. **Fix**: reserve full symmetry for where stability/formality is the point; use asymmetrical balance elsewhere.

### 7. Horror vacui (overcrowding)
**Symptom**: elements packed edge-to-edge with no breathing room; the focal point has no space to be read as the focal point. **Violates**: negative space as active shape (artistic-principles.md). **Fix**: identify what can be removed or simplified, and make sure the area immediately around the focal point is comparatively quiet.

### 8. Under-filled without intent
**Symptom**: small, isolated elements floating in a large empty field with no compositional reason for the emptiness (the inverse failure of #7). **Fix**: either give the negative space a clear job (isolation = emphasis, per artistic-principles.md) or fill the compositional gap.

### 9. Edge collision
**Symptom**: important elements touch or get awkwardly cropped by the canvas boundary without that being an intentional bleed/crop choice. **Fix**: give important content margin, or commit fully to an intentional bleed (no ambiguous half-crop).

### 10. Inconsistent perspective
**Symptom**: parallel edges in the same direction converge toward different vanishing points, or multiple contradictory horizon lines. **Violates**: linear perspective consistency (mathematical-foundations.md). **Fix**: establish one horizon line and vanishing point set per view and check all parallel edges against it.

### 11. Inconsistent light source
**Symptom**: cast shadows point in different directions on different elements in the same scene. **Violates**: single consistent light direction (perception-and-biology.md, depth cues). **Fix**: pick one light source and derive every shadow/highlight from it.

### 12. Arbitrary color relationships
**Symptom**: hues chosen with no wheel relationship to each other — not complementary, analogous, or triadic, just whatever came up, and clashing without that being the intent. **Violates**: color-as-geometry (mathematical-foundations.md). **Fix**: pick a harmony scheme deliberately, even a loose one; if arbitrary/clashing color is the intentional statement, that's fine — but it should be a choice, not a default.

### 13. Palette-wide oversaturation
**Symptom**: every color pushed to maximum saturation, leaving no visual "rest points" and causing fatigue on longer viewing. **Fix**: reserve peak saturation for the focal point/accent; let most of the palette sit at lower saturation to give the accent somewhere to stand out *against*.

### 14. Typographic hierarchy collapse
**Symptom**: headings, body text, and calls-to-action all rendered at similar size/weight, or more than 2-3 typefaces used without a reason. **Violates**: hierarchy encoding (artistic-principles.md) and the ~1.5x minimum-distinction floor (mathematical-foundations.md). **Fix**: establish a modular type scale and make sure adjacent hierarchy levels clear that ratio.

### 15. Poor text legibility
**Symptom**: centered body paragraphs (harder to track line-to-line than left-aligned), or line lengths well outside roughly 45-90 characters. **Fix**: left-align body copy, constrain line length to a readable measure.

### 16. Accessibility neglect
**Symptom**: text/UI contrast below WCAG minimums (4.5:1 normal text, 3:1 large text/UI components), or meaning conveyed by color alone. **Violates**: contrast ratio requirements (mathematical-foundations.md) — this one is not a matter of taste, it's measurably a failure for a meaningful fraction of users (including the ~8% of men with red-green color-vision deficiency). **Fix**: check actual contrast ratios, not just perceived brightness; pair any color-coded meaning with a second channel (shape, icon, label).

### 17. Trend applied without function
**Symptom**: glassmorphism, neumorphism, excessive blur, or other of-the-moment effects applied because they're current, at the cost of legibility or clarity. **Fix**: ask what the effect is doing functionally (depth cue? focus cue?) — if the answer is only "it looks current," it's a decoration cost, weigh it against what it's costing in legibility.

### 18. Proportion drift in figurative work
**Symptom**: anatomy/proportions (hands, limb lengths, facial features, structural proportions of objects) deviate from a real reference without that being a deliberate stylistic choice — one of the most common visible failure signatures in AI-generated figures. **Fix**: check against real reference proportions; deviate deliberately and consistently if stylizing, not incidentally.

### 19. Scale doesn't match importance
**Symptom**: a decorative or secondary element rendered larger/bolder than the actual primary content. **Violates**: hierarchy encoding (artistic-principles.md) — size is one of the strongest hierarchy channels, so an inversion here actively misleads the eye about what matters. **Fix**: audit that visual size ranking matches intended importance ranking; they should match unless the mismatch itself is the deliberate point (e.g., ironic emphasis).
