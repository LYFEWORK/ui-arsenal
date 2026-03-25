---
name: crosshair
source: ReactBits
source_url: https://reactbits.dev/animations/crosshair
category: animations
tags: cursor, crosshair, target, precision, interactive
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Crosshair

> Adds a crosshair overlay that follows the cursor. Horizontal and vertical lines extend across the full viewport intersecting at the mouse position.

## When to Use

- Creative/design agency portfolio sites
- Interactive data or map interfaces
- Photography or art gallery sites where precision matters
- Landing pages for precision-focused brands (engineering, architecture)
- Showcase builds that need a unique cursor experience

## When NOT to Use

- Standard business sites (confuses users who think it's a UI bug)
- Form-heavy pages (crosshair over inputs is disorienting)
- Mobile (no cursor)
- Sites with other cursor effects (splash, blob)

## Pairs Well With

- `grid-motion` - Crosshair navigating a grid of images
- `galaxy` - Crosshair over starfield for a targeting aesthetic
- `split-text` - Text reveals at the crosshair intersection

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "rgba(255,255,255,0.15)" | Line color |
| lineWidth | number | 1 | Line thickness in px |
| showCoordinates | boolean | false | Display cursor X/Y coordinates |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Crosshair-TS-TW
```

## Lyfework Customization Notes

- Line color: `rgba(255,100,42,0.1)` for subtle Lyfework brand tint
- `lineWidth` of 1px. Anything thicker looks heavy.
- `showCoordinates` only for developer/tech audiences
- Desktop only. No mobile fallback needed, it just doesn't render.

## Performance Notes

- Pure CSS positioned elements following mouse events
- requestAnimationFrame for smooth tracking
- Negligible performance cost
