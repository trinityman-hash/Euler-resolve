# Anti-Slop: Visual and Layout Patterns

This is a mandatory, not optional, pass — run it against the actual output before calling any web/product visual work finished. Each item names the pattern, why it keeps showing up as an AI-generated default, and the fix. As stated in the skill's scope note: these are the specific, currently-overused defaults as of 2026, not permanent bans. Every item on this list is allowed — *if it's a stated decision.* The failure mode this file exists to catch is one of these landing in the output because it was the path of least resistance, not because anyone chose it.

For every item below, you must be able to say "not present" or "present, because [specific reason tied to this brief]." Skipping items is not an option.

### 1. Purple-to-blue gradient hero background
**Pattern**: a diagonal or radial gradient sweeping from violet/purple into blue, used as the default hero/page background. **Why it happens**: it's the single most statistically common hero treatment in modern SaaS training data — safe, inoffensive, and requires no actual brand-color decision. It is now the single most-cited visual signature of AI-generated design. **Fix**: derive any hero treatment from the real brand hue as a tonal gradient (same hue, varying lightness/chroma — see `color-systems-for-web.md`), or use no gradient at all. A flat, deliberate surface with strong typographic hierarchy is not a weaker choice.

### 2. Glassmorphism as the default background treatment
**Pattern**: frosted/blurred translucent panels (`backdrop-filter: blur(...)`) applied to entire page sections or as the default card treatment, rather than to isolated elements that genuinely need to float above changing content. **Why it happens**: it reads as "modern" cheaply and requires no layout decision. **Fix**: reserve blur/translucency for elements that actually sit above shifting content — a persistent nav bar, a modal, a floating toolbar. Default content surfaces should be a solid, deliberately-chosen flat color from the token system.

### 3. Bento grid used as unmotivated default structure
**Pattern**: content forced into a mosaic of variously-sized boxes regardless of whether the items actually differ in importance or data density. **Why it happens**: it's become the reflexive "modern SaaS" layout convention, applied whether or not the content has the size/importance variance that a bento layout is supposed to encode. **Fix**: bento layout is a hierarchy tool (see `euler-resolve`'s hierarchy-encoding principle) — only justified when items genuinely differ in importance. Equal-importance content should get equal-sized cards, or a simpler list/table.

### 4. Floating cards with a generic soft drop shadow, applied to everything
**Pattern**: `box-shadow: 0 4px 6px rgba(0,0,0,0.1)` (or equivalent) reflexively applied to any rectangular surface. **Why it happens**: it's a one-line way to make a flat box look "designed." **Fix**: shadows are a depth cue — reserve them for elements genuinely floating above content (modals, dropdowns, dragged items, popovers). Resting content surfaces at rest should be distinguished with a border or a background-tone step from the neutral scale, not a simulated elevation they don't actually have.

### 5. Icon-in-a-rounded-square + heading + one sentence, times three or four
**Pattern**: the default "why choose us" feature grid — identical-format cards regardless of whether the features are actually parallel in importance or explanation depth. **Why it happens**: it's the fastest way to fill a section with something that looks structured. **Fix**: only use identical-card format when the items are genuinely symmetric; if one feature needs more explanation than the others, forcing it into the same card format hides that instead of communicating it.

### 6. Generic "trusted by" logo strip directly under the hero
**Pattern**: a faded row of company logos, often mismatched in visual weight/style, placed immediately below the hero as a reflexive default. **Fix**: if social proof is real and load-bearing for this brief, give it the same hierarchy discipline as anything else — don't default to a logo row just because it's convention.

### 7. Testimonial carousel with generic praise
**Pattern**: stock headshot, name, title, and a one-sentence quote that could apply to any product ("This tool changed how we work"). **Fix**: a real testimonial is specific — a number, a named before/after, a concrete outcome. A generic quote in this slot is a placeholder that shipped.

### 8. Decorative gradient "blob" or mesh shapes with no relationship to content
**Pattern**: soft abstract gradient shapes scattered in page backgrounds purely as texture, unconnected to brand shape language or the actual focal point. **Fix**: cross-reference `euler-resolve`'s anti-pattern for under-filled space without intent — decoration needs a job (guiding the eye, establishing a brand shape language) or it should be removed.

### 9. Symmetric, center-everything layout applied to inherently asymmetric content
**Pattern**: a hero with a product screenshot or asymmetric visual forced into perfect center alignment purely by default. **Fix**: cross-reference `euler-resolve`'s dead-center-gravity anti-pattern — centering is fine when it's the deliberate choice, not when it's the only option considered.

### 10. Uniform scroll-triggered fade-up on every section, no variation
**Pattern**: every element fades and slides in on scroll with identical timing and easing — "motion for motion's sake." **Why it happens**: it's a one-line addition (or a default in a UI library) that makes a static page feel "alive" with zero design thought. **Fix**: motion should communicate state or direct attention to one specific thing per view; uniform fade-everything reads as templated rather than polished, and on `prefers-reduced-motion` or lower-end devices it's pure cost with no signal. Respect `prefers-reduced-motion` unconditionally, not as an afterthought.

### 11. One single border-radius value applied to every element regardless of role or size
**Pattern**: buttons, cards, images, and avatars all sharing one `border-radius` value — the "everything is a squircle" default. **Fix**: radius should scale with element size and follow a deliberate system (small controls get small radii; large surfaces get larger radii or none) rather than one global value copy-pasted everywhere.

### 12. Generic AI-illustration or stock-photo decoration disconnected from the actual product
**Pattern**: soft-gradient 3D blob illustrations, generic faceless "diverse team" stock photography, or other decoration with no connection to what the product actually is. **Fix**: real screenshots of the actual product, or a genuinely commissioned and distinctive illustration style, beat generic decoration every time — cross-reference `euler-resolve`'s "trend applied without function" anti-pattern.
