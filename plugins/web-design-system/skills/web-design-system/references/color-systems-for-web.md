# Color Systems for Web

A color *system* is not a palette. A palette is a set of colors that look good together. A system assigns every color a role, generates it predictably from a small set of decisions, and can be re-themed (dark mode, white-label, a rebrand) by changing the decisions instead of hunting down hardcoded hex values across the codebase. This file is about building the system; contrast verification and dark-mode specifics live in `accessible-contrast-and-dark-mode.md`.

## Color spaces: pick one to author in, deliberately

**sRGB / hex / rgb()** is device-referenced, not perception-referenced. Two colors with the same numeric "brightness" can look very different depending on hue.

**HSL** is more intuitive to hand-author than raw RGB, but its *lightness* channel is not perceptually uniform: `hsl(60 100% 50%)` (yellow) and `hsl(240 100% 50%)` (blue) share the same L value and look nothing alike in perceived brightness. This is exactly why hue-shifting HSL/RGB gradients pass through a muddy grey-brown middle — the interpolation has no concept of how bright a color actually looks partway through the hue rotation.

**OKLCH** (Oklab in cylindrical/polar form — Lightness, Chroma, Hue) is perceptually uniform: equal L values produce genuinely equal perceived brightness regardless of hue, and equal steps in L or C produce visually equal steps. It was designed by Björn Ottosson in 2020 specifically to fix this. As of 2026 it has solid browser support (Chrome 111+, Firefox 113+, Safari 15.4+, Edge 111+ — roughly 90%+ global coverage per current browser-support trackers; verify current numbers before treating this as a hard cutoff for a specific audience). Practical payoff: gradients between two saturated colors of different hues stay vivid instead of muddying in the middle, and lightness-based scale generation (below) actually produces even-looking steps.

```css
:root {
  /* author in oklch, ship a fallback via cascade order for older browsers */
  --brand-9: #3b5bfd; /* fallback, declared first */
  --brand-9: oklch(56% 0.21 264);
}
```

Use HSL if the project has a hard reason to stay in a simpler mental model or needs broad legacy support without a build step. Use OKLCH as the default for any new system where scale consistency and gradient quality matter — which is most product UI.

## Semantic / functional tokens, not raw values in components

Components should never reference a raw color value directly. They reference a *role*, and the role is mapped to a scale step once, centrally:

- **Background / surface** — canvas (page background), surface (card/panel), overlay (modal backdrop), each usually a different step of the neutral scale.
- **Foreground / text** — primary text, secondary/muted text, disabled text, text-on-color (for text sitting on a saturated background, which needs its own contrast check, not a reused text token).
- **Border** — subtle (barely-there separators), default, strong (focus/active emphasis).
- **Interactive** — primary action fill, its hover/active/disabled states, and a distinct focus-ring token (focus rings need their own contrast check against both the control and the page — see the next file).
- **Semantic / status** — success, warning, error/danger, info — each needs a text-safe variant and a background-safe (usually lower-chroma, tinted-surface) variant; these should not be arbitrary hues borrowed from wherever — pick them once and reuse.
- **Brand / accent** — the one or two hues that actually carry brand identity, used sparingly enough that they still mean something when they appear.

The test for whether tokens are actually working: swapping the whole system to dark mode, or to a white-label brand color, should be a change in the token *definitions*, not a search-and-replace across every component.

## Scale construction: pick a model, apply it consistently

Three established approaches, none of them "the" right answer — the failure mode is mixing conventions (half the components use scale tokens, the other half use bespoke `rgba()` overlays invented on the spot):

- **Tailwind-style 50–950 scale.** An 11-step ramp per hue, generated with the same shape of ramp across the whole palette so different hues feel consistent at the same step number. Simple, widely understood, good default for teams already in that ecosystem.
- **Radix Colors' 12-step scale.** Each step is engineered for a specific UI *job*, not just a lightness value: steps 1–2 are app/subtle backgrounds, 3–5 are component backgrounds and their hover/active states, 6–8 are borders (subtle to strong), 9–10 are solid/high-contrast fills (the "main" brand color usually lives here), 11–12 are text (low-contrast and high-contrast). This is a stronger model when the goal is "never have to think about which step to use for a hover state" because the step number already encodes the answer.
- **Material Design 3's HCT tonal palettes.** Colors are generated from a small set of seed/key colors in HCT (Hue, Chroma, Tone) space, producing full tonal ramps and "dynamic color" derivations automatically. Heavier machinery, most useful when the system needs to generate a full theme from a single brand color (e.g., extracting a theme from a user's wallpaper or a brand logo) rather than being hand-tuned.

Pick one model per project and apply it everywhere. A system that's 80% Radix-style semantic steps and 20% "I eyeballed a slightly-lighter blue for this one hover state" is worse than either pure approach, because the exception is invisible until someone tries to reuse it.

## Harmony, but for interfaces specifically

`euler-resolve`'s `mathematical-foundations.md` covers the geometry of color harmony (complementary, triadic, analogous) for composition generally — that still applies here for the *relationships between hues* when you do need more than one. But the harmony question that actually matters most in product UI usually isn't "which three hues go together" — it's: one neutral scale carrying almost all of the surface/text/border weight, one brand/primary hue used for interactive emphasis, and a small fixed set of semantic hues (success/warning/error/info) that are visually distinct enough from the brand hue and from each other that they don't compete for the same kind of attention. A five-hue "harmonious palette" applied literally to a dashboard usually reads as busier and less legible than a disciplined neutral-plus-one-accent system, precisely because interfaces need hierarchy more than they need chromatic variety.

## Gradients: signal or default?

A gradient should be doing a specific job — implying depth, direction, or brand energy — not filling space because a flat surface "felt unfinished." Two practical notes:

- **Hue-shifting gradients in sRGB/HSL interpolation pass through a muddy middle** (see the color-space section above); the same gradient interpolated in OKLCH stays vivid. If a hue-shifting gradient is genuinely the right call, prefer `color-mix(in oklch, ...)` or an `oklch()`-based gradient over a raw `linear-gradient(purple, blue)`.
- **A tonal gradient** — two stops of the *same* hue at different lightness/chroma — reads as considerably more intentional and brand-specific than a generic hue-shifting gradient, precisely because the hue-shifting purple-to-blue treatment is the single most-cited AI-generated-design signature (see `anti-slop-visual-patterns.md`, item 1). If a hero needs a gradient at all, a tonal gradient of the actual brand hue is a stronger default than a generic purple-blue sweep.

## CSS mechanics available now (verify current support before depending on any of these for a critical path)

```css
:root {
  --brand-9: oklch(56% 0.21 264);
}

/* runtime tinting without a build step — Baseline 2023, ~89%+ support as of 2026 */
.subtle-brand-bg {
  background: color-mix(in oklch, var(--brand-9), white 88%);
}
```

`contrast-color()` (auto-picks black/white text against a given background) exists in spec and has landed in some browsers, but as of current tracking it is not yet reliably available everywhere (Chrome support was still behind a flag in mid-2026 sources) — don't depend on it for anything shipping broadly yet; use `color-mix()`-based tinting or precomputed tokens instead, and re-check support before this becomes load-bearing.
