# Perception and Biology

Math gives you candidate structure. This is what actually determines whether a human eye finds it — the hardware and the grouping rules the brain runs before conscious attention even engages.

## Gestalt principles (how the eye groups things before you tell it to)

- **Proximity** — elements placed close together are read as one group, regardless of what they actually are. The single fastest way to create or destroy a sense of organization is adjusting spacing, not adjusting the elements themselves.
- **Similarity** — elements sharing color, shape, or size are grouped, even across distance. Use this to link related items across a layout; misuse of it (accidentally making unrelated things look similar) is a common source of confusing hierarchy.
- **Closure** — the eye completes incomplete shapes (a circle implied by a broken outline still reads as a circle). Lets you imply form with less detail than you'd think.
- **Continuity** — the eye follows the smoothest path through a set of points/lines, even across gaps. This is the mechanism behind "leading lines."
- **Figure-ground** — the eye segments a scene into a subject (figure) and a background (ground). Ambiguous figure-ground (unclear what's foreground vs. background) is disorienting unless that ambiguity is the intentional point (as in Escher-style work).
- **Common region / common fate** — elements sharing an enclosing boundary, or moving/oriented the same way, are grouped even if not close together.

## The eye itself

The **fovea** — the small central part of the retina, covering only about 2° of visual field — is where essentially all fine detail and color discrimination happens; it's dense with cones. Everything outside that 2° (**peripheral vision**) is rod-dominated: much lower resolution, poor color discrimination, but highly sensitive to motion and coarse contrast. Practically: a viewer only ever sees *one small area* in true detail at a time and reconstructs the rest via rapid eye movements (**saccades**) — so fine detail placed somewhere the eye has no reason to fixate is wasted effort, while large-scale contrast or motion is what pulls the eye there in the first place. Design for the sequence of fixations, not for "the whole image is seen at once," because it isn't.

**Contrast sensitivity** peaks at a middling spatial frequency (roughly 3-5 cycles per degree of visual field) and falls off at both very fine and very coarse detail. In practice: extremely fine texture/detail can be nearly invisible at normal viewing distance even though it's "there," and line weights or detail scale should be chosen relative to expected viewing distance, not in the abstract.

## Pre-attentive processing

A small set of visual attributes — color, orientation, size, motion, and position — are processed pre-attentively, meaning the visual system registers them (in roughly 200-250ms) *before* conscious, effortful search kicks in. This is why a single red dot among gray ones is spotted instantly, but a single rotated "N" among other rotated letters is not. The direct design consequence: these attributes are what you should reserve for the one thing that actually needs to be found first. If several elements are all pre-attentively distinct (all different colors, all different sizes, all differently oriented), none of them wins — this is the mechanism behind "everything is emphasized, so nothing is."

## Scan patterns

In left-to-right (LTR) reading cultures, eyes tend to default to a **Z-pattern** on sparse/image-led layouts (top-left → top-right → diagonal down → bottom-right) and an **F-pattern** on dense text layouts (a full pass across the top, a shorter pass partway down, then a vertical scan down the left edge). In right-to-left (RTL) reading cultures (Arabic, Hebrew, and others), both patterns mirror horizontally — the natural entry point is top-right, not top-left. Get the reading direction of the actual audience right before applying either pattern; assuming LTR by default for an RTL context will fight the viewer's natural scan path instead of working with it. Neither pattern is a hard rule in either direction, but a layout that fights the natural entry point needs a strong enough visual cue to override the default, or key content placed near the natural entry/exit points for that audience.

## Color perception

Human color vision is **trichromatic**: three cone types roughly tuned to short (blue), medium (green), and long (red) wavelengths. But the brain doesn't process raw cone output directly — it recodes it via **opponent-process channels**: red-vs-green, blue-vs-yellow, and black-vs-white (light-vs-dark). This is why there's no such thing as a "reddish-green" (the channels are mutually exclusive) and why saturated red and green at equal lightness placed adjacent to each other create visual vibration/afterimage effects — the opponent channel is being driven hard in both directions at once with no lightness difference to stabilize it. If a strong complementary pairing is intentional, controlling the lightness/saturation of one side calms this; if it's unintentional, it reads as a mistake ("why does this hurt to look at").

## Depth cues, in order of how strongly they read in a 2D image

1. **Occlusion** (one object overlapping another) — strongest, least ambiguous cue there is.
2. **Relative size** — larger reads as closer, all else equal.
3. **Texture gradient** — texture detail gets denser/finer with distance.
4. **Atmospheric perspective** — contrast/saturation loss with distance (see mathematical-foundations.md).
5. **Linear perspective / convergence** — parallel lines appearing to converge.
6. **Shading and cast shadow** — also the primary cue for an object's own 3D form, not just its position; requires one *consistent* light direction across the whole scene to read correctly.

## Visual weight

Elements aren't equally "heavy" to the eye even at equal size: dark reads heavier than light, warm reads heavier than cool, textured/detailed reads heavier than flat, isolated reads heavier than grouped, and irregular reads heavier than regular. Balance (see artistic-principles.md) is calculated with these weights, not with literal geometric symmetry — a small, dark, isolated shape can balance a much larger pale one.

## Symmetry and faces

Human perception has an innate bias toward detecting bilateral symmetry, plausibly rooted in face and predator recognition. This is the underlying reason symmetric logos/compositions read as stable, trustworthy, or formal, while asymmetric ones read as dynamic or energetic — it's not just convention, there's a perceptual reason the association holds.

<sub>Note: this is a design-heuristics summary, not a biology or medical reference — treat specifics as working approximations useful for composition decisions, not as citations for clinical or scientific claims.</sub>
