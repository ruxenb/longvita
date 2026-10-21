---
version: "alpha"
name: "Organic / Biomorphic"
description: "Organic / Biomorphic visual system, translated from the Claude Artisan catalog for use in digital products. Flowing curves and asymmetric blobs; Soft natural palettes"
colors:
  primary: "#476429"
  primary-soft: "#6f8f4e"
  background: "#f6f1e7"
  surface: "#ffffff"
  text: "#2f3b2a"
  text-muted: "#5c6b53"
  border-control: "#74796c"
  accent: "#d98b5f"
  on-primary: "#ffffff"
  on-surface: "#2f3b2a"
  on-accent: "#2f3b2a"
typography:
  h1:
    fontFamily: "'Fraunces', Georgia, serif"
    fontSize: "4rem"
    fontWeight: "700"
    lineHeight: "1.05"
  body-md:
    fontFamily: "'Quicksand', 'Nunito', system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: "400"
    lineHeight: "1.6"
  label-caps:
    fontFamily: "'Quicksand', 'Nunito', system-ui, sans-serif"
    fontSize: "0.75rem"
    fontWeight: "600"
    letterSpacing: "0.06em"
rounded:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  full: "9999px"
spacing:
  sm: "8px"
  md: "16px"
  lg: "32px"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.md}"
    padding: "16px"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    rounded: "{rounded.md}"
    borderColor: "{colors.border-control}"
    padding: "16px"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.md}"
    padding: "16px"
  page:
    backgroundColor: "{colors.background}"
    textColor: "{colors.text}"
    padding: "16px"
---
## Overview

Organic / Biomorphic visual system, translated from the Claude Artisan catalog for use in digital products. Flowing curves and asymmetric blobs; Soft natural palettes

- **Category:** minimal-organic
- **Era:** 2018–present
- **Origin:** Reaction to rigid grids; nature-derived forms.
- **Reference:** Wellness/beauty brand sites; many 2020s landing pages.
- **Structural base:** hero, superfície, conteúdo e grade responsiva

**Defining traits:**
- Warm organic palette with editorial hierarchy
- Natural imagery and restrained biomorphic accents
- Fluid, hand-tuned layouts with clear task priority
- Reduced rounding: geometry supports hierarchy instead of decorating every element

## Colors

- **bg** — #f6f1e7
- **surface** — #ffffff
- **surface-strong** — #eee6d6
- **border/decorative** — #dccdb0
- **border/control** — #74796c
- **text** — #2f3b2a
- **text-muted** — #5c6b53
- **primary/action** — #476429
- **primary/soft** — #6f8f4e
- **accent** — #d98b5f
- **clay** — #e7c9a9

Contrast pairs used for interactive UI:
- White on `#476429`: 6.72:1, suitable for normal-size button labels.
- `#74796C` against `#F6F1E7`: 3.97:1, suitable for functional control boundaries.
- `#6F8F4E` remains a soft brand green and must not carry normal-size white text.

## Typography

- Display: 'Fraunces', Georgia, serif
- Body: 'Quicksand', 'Nunito', system-ui, sans-serif
- Mono: ui-monospace, monospace

## Layout

- hero, superfície, conteúdo e grade responsiva
- Use a responsive grid and preserve content hierarchy.
- Collapse columns below 768px without horizontal overflow.

## Elevation & Depth

- Level 0 is the default; prefer border, spacing and typography over shadow.
- Level 1 is reserved for cards or actions that must separate from the canvas.
- Level 2 is reserved for dialogs and true overlays.

## Shapes

- Radius scale: 4px, 8px, 12px, 16px, full.
- Use 8–12px for controls, 12px for standard cards, and 16px for large dialogs or special surfaces.
- Full/pill radius is limited to status chips and segmented selection; it is not a default button or card shape.

## Components

- Buttons keep visible focus and predictable pressed/disabled/loading states; standard radius is 12px.
- Cards use 12px by default and rely on spacing/dividers instead of excessive nested containers.
- Forms expose persistent labels, textual errors, functional `#74796C` boundaries and keyboard focus.
- All interactive hit areas remain at least 48x48dp.

## Do's and Don'ts

- Do: follow the tokens and the structural composition.
- Do: maintain WCAG AA contrast and `prefers-reduced-motion`.
- Avoid: using the style as decoration without functional hierarchy.
