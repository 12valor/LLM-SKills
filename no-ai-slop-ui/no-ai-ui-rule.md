# Rule: No AI-Looking UI

## Rule Statement

**Never generate UI that exhibits AI-generated ("AI slop") aesthetic patterns.**
Every interface must have a deliberate, named aesthetic direction with specific,
non-default choices for color, typography, layout, and motion.

---

## What This Rule Prohibits

### Color
- Purple-to-blue gradients of any kind
- Default Tailwind `blue-500` / `indigo-500` / `violet-500` as primary colors
- Soft pastel void backgrounds (pale lavender, near-white gray, baby blue)
- Teal + purple duotones
- Gray-900 background + white text + one accent with no texture

### Typography
- Inter, Roboto, Arial, or `system-ui` as the default font choice
- Space Grotesk, Poppins, or Montserrat picked for being "safe but modern"
- Single-font designs with no typographic contrast
- Uniformly scaled type sizes with no tension or hierarchy

### Layout
- Centered hero: large headline + subheadline + single CTA button
- Three-column feature grids: icon → title → one-line description
- "Trusted by X companies" logo bars as mandatory section 2
- Identical top-nav → hero → features → testimonials → CTA → footer sequence
- Every container using `flex items-center justify-between`
- All elements center-aligned on desktop

### Visual Effects
- Glassmorphism: `backdrop-blur` + translucent white cards
- 3D illustrated figures in abstract poses with glowing orbs
- Blob SVGs as background decoration
- `shadow-lg` applied uniformly to every card
- Linear gradient overlays on hero backgrounds (dark-to-transparent)

### Code
- `rounded-lg` on every element without variation
- `p-4 gap-4 m-4` as universal spacing
- Unstyled shadcn/ui components with no visual customization
- Pure Tailwind utility-class soup with zero custom CSS

### Copy
- "The easiest way to [generic verb]" as the hero headline
- "Powerful," "seamless," "robust," "transformative" in feature copy
- Placeholder text that could describe any product in any industry

---

## What This Rule Requires

Before writing any UI code, explicitly commit to and document:

1. **A named aesthetic direction** (e.g., "Swiss brutalism", "warm editorial",
   "industrial Bauhaus") — if you can't name it, you don't have one.

2. **Specific, intentional color palette** — defined as CSS custom properties
   with semantic names, not pulled from Tailwind defaults.

3. **A deliberate font pairing** — two fonts maximum, chosen for contrast and
   character, not safety. At least one must be non-generic.

4. **At least one layout choice that breaks convention** — asymmetry,
   full-bleed type, overlapping elements, or a non-standard section order.

5. **A distinct motion personality** (mechanical, organic, theatrical, none)
   — not `transition-all duration-300 ease-in-out` on everything.

---

## How to Apply This Rule

When you feel yourself reaching for a default choice, ask:
> "Would a senior designer at a respected studio make this exact choice,
> or would they see it as lazy?"

If the answer is "lazy" — change it.

The bar is: **someone should be able to look at this UI and describe its
aesthetic in specific terms**, not just say "it looks professional" or
"it looks like a SaaS product."
