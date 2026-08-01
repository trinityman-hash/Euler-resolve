# Accessible Contrast and Dark Mode

## The current, actually-enforceable standard: WCAG 2.x contrast

WCAG's contrast success criteria (1.4.3 and 1.4.11, unchanged between 2.1 and 2.2) are the standard to design and verify against right now:

- **4.5:1** minimum for normal text.
- **3:1** minimum for large text (≥18pt / 24px regular weight, or ≥14pt / 18.66px bold).
- **3:1** minimum for the visual boundaries of UI components (button borders, input outlines, icons that convey meaning) and for graphical objects required to understand content.

These are computed from relative luminance, not perceived brightness — always check an actual computed ratio (a contrast checker, or a library) rather than eyeballing it. Two colors that look "clearly different enough" side by side can still fail 4.5:1.

## APCA and WCAG 3: not yet the standard — stated with appropriate uncertainty

APCA (Advanced Perceptual Contrast Algorithm) was proposed as a more perceptually-accurate successor to the WCAG 2.x contrast math and was included in early WCAG 3 drafts. As of the most recent tracking available, **APCA was pulled from the WCAG 3 working draft (reportedly mid-2023) for insufficient Working Group support, and WCAG 3's own contrast algorithm is currently listed as undetermined** — with some tracking suggesting the standard as a whole may not finalize for years. Treat this section as a snapshot, not a guarantee: **if WCAG 3 or APCA compliance is actually load-bearing for a project, verify the current status directly rather than trusting this file**, since this is exactly the kind of fast-moving standards status that can change after this was written.

Practical guidance until that resolves: **design and verify against WCAG 2.x's 4.5:1 / 3:1 numbers as the real, current, enforceable target.** APCA-aware tooling can be used as an *additional* informative signal (some teams already do this), but don't trade away 2.x compliance for an APCA number, since 2.x is what's actually normatively required today.

## OKLCH lightness as a fast heuristic (not a replacement for a real check)

Because OKLCH lightness (L) is perceptually uniform, it gives a useful rule-of-thumb starting point when authoring a scale:

- Normal text on a white surface: roughly **L ≤ 0.55** tends to clear 4.5:1.
- Large text on a white surface: roughly **L ≤ 0.65** tends to clear 3:1.
- Text on a black/near-black surface: roughly **L ≥ 0.55** tends to clear 4.5:1.

These are heuristics, not guarantees — chroma and hue shift the real number, sometimes meaningfully. Use them to get close while authoring a scale, then verify the actual pair with a real contrast calculation before shipping.

## Never encode meaning in hue alone

Red-green color-vision deficiency affects a meaningful share of men (commonly cited around 8%, lower in women) — common enough that hue-only status encoding (red = error, green = success, with no other differentiator) is a real, frequent accessibility failure, not an edge case. Pair every status color with a second channel: an icon, a shape, a text label, or a position convention. Test palettes against a colorblindness simulation, not just by eye.

## Focus states need their own contrast check

A focus indicator (outline, ring) needs at least 3:1 contrast against *both* the control it surrounds and the page background behind it — a subtle `box-shadow` tint that looks fine against one background can disappear against the other. Don't reuse a decorative border token for focus; give focus its own token and check it against both surfaces it actually appears on.

## Dark mode is a redesign, not an inversion

Generating dark mode by inverting or auto-darkening the light palette is a common shortcut and a common source of a muddy, low-contrast, or headache-inducing result. Specific, concrete adjustments that separate a genuinely-designed dark mode from an inverted one:

- **Desaturate saturated brand/accent colors at dark-background lightness.** A brand blue tuned to look right at high lightness on white often reads as glowing or vibrating on a dark background at the same chroma — reduce chroma (and often adjust lightness slightly) rather than reusing the light-mode value unchanged.
- **Avoid a true-black (`#000000`) canvas for large surfaces.** Pure black behind bright text creates harsh edge contrast (visible "halation" on OLED displays in particular) and reads as harsher than intended. Most mature dark-mode systems use a dark neutral — low but non-zero lightness — as the base surface instead.
- **Elevation reads through lightness steps, not shadows.** Drop shadows barely register against a dark background the way they do against a light one. Dark-mode "elevation" (a raised card sitting above the canvas) is conventionally communicated by making the raised surface a step *lighter* than what's behind it, not by simulating a shadow that won't be visible.
- **Avoid pure white text on near-black.** Maximum contrast (`#FFFFFF` on very-dark) can produce a subtle glow/vibration effect for some readers even though it technically clears contrast minimums; a slightly off-white neutral (roughly 90–95% lightness) is a common, still-compliant mitigation.
- **Verify each token pair independently.** Don't assume that because the light-mode pairing passed contrast, its "opposite" in dark mode automatically does too — check both resolved outputs of the semantic token set separately.

## CSS mechanics

The `light-dark()` CSS function lets a single declaration resolve to different values depending on the active `color-scheme`, which is the mechanism to reach for once a project is authoring both themes from the same token set. Support has been landing across major browsers, but **verify current browser support before depending on it for a critical rendering path** rather than assuming universal coverage — CSS color-function support moves fast enough that a specific version cutoff stated here could already be stale.
