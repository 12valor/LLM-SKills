---
name: no-ai-slop-ui
description: >
  Enforces human-crafted, distinctive UI design by detecting and eliminating
  all patterns that make an interface look AI-generated. Use this skill
  whenever building or reviewing ANY frontend interface — React components,
  HTML pages, dashboards, landing pages, design systems, or any visual UI.
  This skill MUST be consulted before writing a single line of UI code.
  Trigger on: "build a UI", "create a component", "design a page", "make a
  dashboard", "landing page", "web app", "frontend", "style this", "make it
  look good", or any UI-adjacent request.
---

# No AI Slop UI

This skill ensures every UI generated has the **intentionality, specificity,
and character of a human designer** — not the statistical average of a
language model trained on Dribbble trends.

Before writing any UI code, run through the full checklist below and commit
to explicit, non-default answers for every dimension.

---

## Step 1 — Identify Context & Commit to a Design Direction

Answer these before touching code:

1. **Who is this for?** (developer tool, consumer app, luxury brand, kids product, etc.)
2. **What's the emotional register?** (tense/urgent, calm/clinical, playful/warm, cold/authoritative)
3. **What's the one thing someone should remember?** The single most striking visual choice.
4. **What aesthetic school am I drawing from?** Pick one and name it. Examples:
   - Swiss International Typographic Style (grids, Helvetica, rational)
   - Brutalism (raw HTML energy, bold borders, intentional ugliness)
   - Editorial / Magazine (large typographic hierarchies, asymmetric columns)
   - Art Deco (geometric ornament, gold/black, symmetry with flair)
   - Japandi (negative space, muted clay tones, restrained elegance)
   - Memphis Design (primary colors, geometric shapes, maximalist pattern)
   - Industrial / Bauhaus (function-first, mechanical precision, primary palette)
   - 90s Web / Retro Digital (nostalgia without irony, pixel borders, dithering)
   - Organic / Biomorphic (rounded everything, botanical palettes, soft motion)

If you can't name the school, you don't have a direction yet. **Pick one.**

---

## Step 2 — The AI Slop Blacklist

These are **banned** unless explicitly requested by the user. If you find yourself
reaching for any of these, stop and make a different choice.

### 🚫 Banned Color Choices
- Purple-to-blue gradients (the #1 AI tell)
- Any gradient that goes purple → indigo → blue on white background
- "Brand blue" (#3B82F6 / Tailwind `blue-500`) as a default primary
- Teal + purple duotones
- Soft pastel void backgrounds (pale lavender, baby blue, near-white gray)
- Gray-900 background + white text + one accent color with zero texture

**Do instead**: Commit to an unexpected palette. Warm ochres, deep burgundy,
forest green, near-black navy, burnt sienna, chalk white + ink. Reference a
specific artistic movement or real-world material for color inspiration.

### 🚫 Banned Typography
- Inter as body font (too safe, everywhere)
- Roboto, Arial, system-ui as default choices
- Space Grotesk as "interesting alternative" (overused)
- One font for everything (no typographic contrast)
- Font sizes that increase by uniform increments (16, 20, 24, 32 — boring)

**Do instead**: Pair a distinctive display font with a refined body font.
Use Google Fonts or system font stacks with personality. Examples of good
pairings:
- Playfair Display + Source Serif 4 (editorial gravitas)
- Syne + DM Mono (technical editorial)
- Fraunces + Atkinson Hyperlegible (humanist tension)
- Bebas Neue + IBM Plex Sans (industrial clarity)
- Cabinet Grotesk + Lora (contemporary magazine)
Scale should feel deliberately chosen: e.g., a massive 96px display size +
14px body creates tension. Uniform scales create boredom.

### 🚫 Banned Layout Patterns
- Hero section: centered headline + subheadline + one CTA button (default)
- Three-column feature grid: icon → bold title → one-line description
- "Trusted by X companies" logo bar as section 2
- Top-nav → hero → features → testimonials → CTA → footer (in exactly that order)
- Cards with identical border-radius, shadow, and padding throughout
- Everything center-aligned on desktop

**Do instead**: Break the grid intentionally. Use asymmetric layouts.
Let type run full-bleed. Overlap elements. Use horizontal scrolling sections.
Try a single-column editorial layout instead of a grid. Use negative space
actively, not as filler.

### 🚫 Banned Visual Effects
- Glassmorphism cards (`backdrop-blur` + `bg-white/10` + soft border)
- 3D illustrated humans in impossible poses with glowing orbs
- Blob SVGs as background decoration
- Lottie-style floating animation on hero images
- Soft drop shadows on everything (`shadow-lg` on every card)
- Linear gradient overlays on hero images (dark-to-transparent bottom)

**Do instead**: Use texture (CSS noise, grain overlay). Use hard shadows
(offset box-shadow with no blur for brutalist feel). Use real photography
or no illustration at all. Use geometric shapes with purpose. Use borders
instead of shadows.

### 🚫 Banned Code Patterns
- `rounded-lg` on every single element uniformly
- `p-4 gap-4 m-4` as universal spacing (no rhythm)
- Tailwind `gray-*` scale for everything neutral
- Unstyled shadcn/ui components with zero customization
- `className="flex items-center justify-between"` as every container
- Pure utility-class soup with zero custom CSS or CSS variables

**Do instead**: Define a custom spacing scale as CSS variables. Mix
`rounded-none` with `rounded-full` for contrast. Write actual custom CSS
for at least one signature effect per component. Use CSS custom properties
for your design tokens.

---

## Step 3 — Mandatory Design Tokens

Before coding, define these explicitly in your component or stylesheet.
Do NOT rely on Tailwind defaults — override them with intention:

```css
:root {
  /* Colors — name them semantically, not by value */
  --color-ink: /* your darkest */;
  --color-paper: /* your lightest */;
  --color-accent: /* your one punchy color */;
  --color-mid: /* your mid-tone */;

  /* Typography — choose explicitly */
  --font-display: /* your headline font */;
  --font-body: /* your reading font */;
  --font-mono: /* if needed */;

  /* Scale — define your own, don't use Tailwind's */
  --space-xs: ;
  --space-sm: ;
  --space-md: ;
  --space-lg: ;
  --space-xl: ;
  --space-2xl: ;

  /* One signature effect */
  --shadow-hard: 4px 4px 0px var(--color-ink); /* e.g., brutalist */
  --radius-soft: 2px; /* e.g., minimal */
}
```

---

## Step 4 — Motion & Interaction

AI tools produce motion that is:
- Fade-in on scroll for every element equally
- `transition-all duration-300 ease-in-out` everywhere
- Hover: scale up slightly + shadow grows

**Do instead**: Give motion a point of view. Choose ONE:
- **Mechanical**: Snappy easing (`cubic-bezier(0.77, 0, 0.175, 1)`), sharp transitions, no spring
- **Organic**: Spring physics, overshoots, breathes in/out
- **Editorial**: No animation on content — only UI affordances animate
- **Theatrical**: Exaggerated entrance animations, dramatic reveals
- **Glitch/Broken**: Intentional stutter, offset reveals, CSS clip-path reveals

Animate purposefully. One well-orchestrated entrance sequence > scattered
hover effects on every card.

---

## Step 5 — Copy & Content

Don't use:
- "The easiest way to [generic action]" as headlines
- "Powerful, seamless, robust" in feature descriptions
- "Trusted by thousands of companies worldwide"
- Feature sections where all three descriptions are the same length

**Do instead**: Write specific, concrete copy. Even placeholder text should
feel like it was written for this exact product.

---

## Step 6 — Final Check

Before delivering, answer:
- [ ] Does this look like it could have come from a UI kit? (if yes → revise)
- [ ] Could I name the aesthetic school? (if no → revise)
- [ ] Is there at least ONE thing a designer would describe as "unexpected"?
- [ ] Are the colors, fonts, and spacing choices all deliberate — not defaults?
- [ ] Is there any glassmorphism, purple gradient, or Inter? (if yes → revise)

---

## Reference Files

For deeper examples and anti-pattern specifics, see:
- `references/color-palettes.md` — Non-AI color palettes by aesthetic school
- `references/font-pairings.md` — Vetted non-generic font pairings
- `references/layout-patterns.md` — Human-feeling layout archetypes
