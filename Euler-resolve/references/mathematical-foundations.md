# Mathematical Foundations

Structural systems for composition. Pick one deliberately rather than eyeballing placement — these are the load-bearing decisions everything else sits on top of.

## Proportion systems

**Golden ratio (φ ≈ 1.618).** Derived as the limit of the ratio between consecutive Fibonacci numbers (1,1,2,3,5,8,13,21... → 21/13 ≈ 1.615, converging on φ). A golden rectangle can be subdivided into a square plus a smaller golden rectangle, repeating infinitely — this is where the golden spiral comes from (a logarithmic spiral approximated by quarter-circle arcs through each square). Useful as a cropping and placement guide: put the focal point near where the spiral's "eye" lands, or size major/minor elements in roughly a 1:1.618 ratio.
Be honest about it: controlled studies on golden-ratio aesthetic preference are mixed at best — treat it as *one* structural option with a long design history, not a law of beauty. Its practical value is that it gives you an asymmetrical division point (roughly 62/38) instead of a boring 50/50, not that the number itself is magic.

**Rule of thirds.** A simplified, easier-to-use approximation of the golden ratio: divide the frame into a 3×3 grid, place focal points on the intersections ("power points") rather than dead center. Weaker mathematically than φ but far more practical for fast composition decisions.

**Root rectangles (dynamic symmetry).** Classical technique (Jay Hambidge): rectangles whose proportions are √2, √3, √5, etc. (a √2 rectangle, for instance, halves into two smaller √2 rectangles — this is also why ISO paper sizes A0-A4 use it). Diagonals of these rectangles, and the perpendiculars dropped from a diagonal to the corners, give a family of natural placement lines that's richer than a single rule-of-thirds grid.

**Modular scale.** For anything with repeated size decisions (typography, spacing, icon sizes), pick one ratio and generate every size by multiplying/dividing by it, rather than choosing sizes ad hoc. Common ratios: 1.125 (major second, subtle), 1.25 (major third), 1.333 (perfect fourth), 1.5 (perfect fifth, strong contrast), 1.618 (golden). Smaller ratio = more steps, subtler hierarchy; larger ratio = fewer steps, bolder hierarchy. As a hierarchy-legibility floor: two levels need at least roughly 1.5x difference in size (or equivalent contrast in weight/color) before they reliably read as *different levels* rather than the same level with noise.

## Grid systems

Column grids (e.g., 12-column responsive grids) give consistent horizontal rhythm and alignment across many elements. Baseline grids do the same vertically for text-heavy layouts. Margins and gutters aren't wasted space — they're what lets the eye separate "content" from "edge of canvas," and their consistency is often what makes a layout read as professional versus improvised.

## Symmetry groups

- **Bilateral (mirror)** — one axis of reflection. Reads as stable, formal, trustworthy (see perception file for why). Overused, it reads as static.
- **Radial (rotational)** — repetition around a center point, order-*n* (n-fold rotational symmetry). Common in mandalas, logos, natural forms (flowers, some shells).
- **Translational** — a motif repeated along a line at constant intervals. The basis of borders, textile patterns, brick coursing.
- **Glide reflection** — mirror plus translation together (e.g., footprints, some brick bonds). Less obvious than pure mirror symmetry, reads as more organic.
- Full pattern taxonomies (frieze groups for 1D repeats, wallpaper groups for 2D repeats) exist for exhaustive pattern/textile work but are usually more formalism than a given task needs.

## Perspective and projection

**Linear perspective**: 1-point (one vanishing point, used for views looking straight down a corridor/road), 2-point (two vanishing points on the horizon, the default for most object/architecture views), 3-point (adds a vertical vanishing point, used for extreme high/low angles). All vanishing points for parallel edges in the *same direction* must sit on the same point — inconsistent vanishing points is one of the most common structural errors (see anti-patterns).
**Foreshortening**: forms compress along the axis pointing toward the viewer; this is a projection effect, not the object actually changing shape.
**Atmospheric perspective**: distant elements lose contrast, saturation, and warmth, and shift toward the ambient/sky color — this is literal (scattering of light through atmosphere) and its absence is why some flat digital work feels like cardboard cutouts at different distances rather than real depth.

## Natural/fractal structure

Many organic forms (branching trees, river deltas, blood vessels, lightning, coastlines) are approximately self-similar across scales — a small branch looks statistically like a scaled-down version of the whole. Critically, this self-similarity is *statistical*, not exact: branch angles and lengths in real plants vary within a range rather than repeating identically. Perfectly regular, mechanically repeated "fractal-like" patterns are what read as fake/AI-generated — see the anti-patterns file. If you need a quick generative approximation, controlled randomness (e.g., Perlin/simplex noise, or an L-system with a randomized angle/length parameter within a defined range) gets closer to natural variance than fixed repetition.

## Color as geometry

Represent color as a wheel (hue = angle, 0-360°) with saturation/lightness as the other two dimensions (HSL/HSV). Standard harmony relationships are literally angular relationships on that wheel:

- **Complementary**: 180° apart. Maximum contrast; use sparingly and at controlled saturation or it visually vibrates (see opponent-process color perception in the perception file).
- **Split-complementary**: base hue + the two hues adjacent to its complement (±150°). Nearly as much contrast, less tension than pure complementary.
- **Triadic**: three hues 120° apart. Vibrant but balanced if one hue dominates and the other two are accents.
- **Analogous**: hues within about 30-60° of each other. Naturally harmonious, lower contrast, can feel monotonous without a value range to compensate.

**Contrast ratio (for anything with text or UI)**: WCAG defines contrast via relative luminance, not just perceived brightness. Minimums: 4.5:1 for normal text, 3:1 for large text (≥18pt or ≥14pt bold) and for UI component boundaries/icons. Below this, legibility failures are not a matter of taste — they're measurable, and they disproportionately affect users with low vision or color-vision deficiency (~8% of men have some form of red-green color-vision deficiency, which is also why color should never be the *only* channel distinguishing meaning — pair it with shape, position, or a label).
