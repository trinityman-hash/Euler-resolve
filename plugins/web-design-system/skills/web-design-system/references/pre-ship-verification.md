# Pre-Ship Verification

The final gate. Run this after the anti-slop passes, before presenting web/product design work as finished — this is user-facing work, verify it like it matters, because it does.

## 1. Contrast — computed, not eyeballed
For every text/background pair and every icon/background or border/background pair actually used in the output: state the pair and confirm it clears 4.5:1 (normal text) or 3:1 (large text, UI component boundaries) per current WCAG 2.x requirements (see `accessible-contrast-and-dark-mode.md`). "It looks readable" is not a pass.

## 2. Colorblind check
Strip all hue mentally (or actually, if you can render a grayscale/desaturated preview) and confirm every status/state distinction — success vs. error, active vs. inactive — still reads from shape, icon, position, or label alone, not color alone.

## 3. Dark mode, if claimed
If dark mode is part of the deliverable: confirm it's a genuinely separate design pass, not an inverted filter. Check surface elevation reads correctly through lightness steps, there's no pure-black canvas or pure-white-on-black text, and brand/accent colors were re-checked for chroma at dark-background lightness — not reused unchanged from light mode.

## 4. Motion
Every animated element respects `prefers-reduced-motion`. Every animation has a reason beyond decoration — state what each one is communicating.

## 5. Full anti-slop pass, both files, item by item
Walk `anti-slop-visual-patterns.md` and `anti-slop-typography-and-copy.md` completely. For each of the 20 items across both files: "not present" or "present, because [specific reason tied to this brief]." No skipped items, no "mostly fine."

## 6. The relabel test
Step back and ask honestly: could this exact layout, color scheme, and copy be relabeled with a competitor's name in thirty seconds with nothing else changed, and would anyone notice? If yes, something upstream didn't get a deliberate decision — go back to whichever section produced it.

## 7. Real-context check
Before calling it finished, confirm: at least one narrow and one wide viewport, both color-scheme states if dark mode is claimed to be supported, and actual copy in every text slot — not lorem ipsum, not `[headline here]`. If real copy isn't available yet, say so explicitly rather than shipping placeholder text that reads as finished.

If any of the seven checks above surfaces a real gap, fix it before presenting the work — this file is the gate, not a suggestion to note and move past.
