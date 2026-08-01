# Anti-Slop: Typography and Copy

A separate, equally-mandatory pass from the visual/layout checklist — typography and copy-voice failures are just as recognizable as an AI-generated signature as gradient heroes and floating cards, and get missed just as often because they don't look "wrong," they look *safe*. Same rule as the other checklist: for every item, state "not present" or "present, because [specific reason]."

### 1. Giant, bold, center-aligned headline as the unexamined hero default
**Pattern**: two to four words of vague aspiration ("Build faster. Ship smarter.") set enormous and dead-center, with no more thought given to it than "make it big." **Why it happens**: it's the statistically safest hero pattern — it requires no actual information-hierarchy decision beyond size. **Fix**: headline size, weight, and alignment should go through the same hierarchy discipline as anything else (see `euler-resolve`'s hierarchy-encoding principle). A left-aligned headline paired with a genuinely specific supporting subhead often communicates more than a huge centered platitude — treat that as a real alternative to actively weigh, not default away from.

### 2. Inter (or whatever the current default is) used unexamined for the entire type system
**Pattern**: one system/default sans-serif used for display headlines and body copy alike, with no reasoning beyond "it's what shipped by default." **Fix**: a typeface choice should be a decision, even if the decision is "this face is genuinely right here, because X." At minimum, consider pairing a distinct display face for headlines with a body face chosen for reading comfort — or state explicitly why a single face for everything is correct for this specific brief.

### 3. Gradient-fill text on headlines
**Pattern**: headline text itself rendered with a hue-shifting gradient fill as a default "make it pop" treatment. **Why it happens**: cheap to add, reads as "designed" without any actual typographic decision. **Fix**: gradient text reduces legibility (contrast varies across the string, and can fail contrast checks entirely in places) and is one of the most immediately recognizable AI-slop signatures on its own. Solid, high-contrast type reads as more considered, not less.

### 4. Uniform weight hierarchy — size is doing all the work
**Pattern**: headline, subhead, and body all rendered in the same one or two font weights, with only size varying between levels. **Fix**: cross-reference `euler-resolve`'s typographic-hierarchy-collapse anti-pattern — vary weight deliberately alongside size; don't make size carry the entire hierarchy on its own.

### 5. All-caps, letter-spaced "eyebrow" label above every single section
**Pattern**: "OUR FEATURES," "WHY CHOOSE US," and similar micro-labels applied reflexively above every heading in the page. **Fix**: an eyebrow label is a legitimate hierarchy tool used sparingly, on the one or two sections that actually benefit from an extra framing cue. Applied to every section, it stops meaning anything and becomes visual noise.

### 6. Generic marketing copy voice
**Pattern**: breathless, feature-adjacent abstraction — "Empower your team to unlock their full potential," "Seamlessly supercharge your workflow" — that could be pasted onto a competitor's site with zero words changed. **Why it happens**: it's the safest, most inoffensive copy register, the textual equivalent of the purple gradient. **Fix**: specific, concrete, product-true copy beats abstraction — a real number, a real capability, a real constraint. If a sentence could describe ten other products unchanged, it isn't actually saying anything about this one.

### 7. Title Case Applied To Every Heading By Reflex
**Pattern**: every heading title-cased regardless of language convention or brand voice, purely because it "looks more official." **Fix**: sentence case is generally more legible for longer headlines and is the more common convention in mature product design. Title case should be a deliberate brand-voice choice, not an automatic default.

### 8. Feature lists padded to a round number
**Pattern**: exactly 3, 4, or 6 "features" forced to fill a grid, sometimes visibly stretched or duplicated (or padded with a vague "coming soon" box) to hit the round number. **Fix**: let the actual content set the count. A 5-feature product forced into a 2×3 six-box grid with one filler box is a visible tell that the layout was chosen before the content was.
