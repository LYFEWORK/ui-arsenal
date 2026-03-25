---
name: comparison-slider
source: ReactBits
source_url: https://reactbits.dev/components/comparison-slider
category: components
tags: comparison, slider, before-after, drag, interactive, images
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ComparisonSlider

> A drag-to-reveal before/after image comparison. Two images overlaid with a draggable divider that slides left-right to reveal each side. The classic "before and after" pattern.

## When to Use

- Before/after website redesign showcases
- Design or renovation project comparisons
- Product or service transformation demonstrations
- Portfolio pieces showing the improvement you delivered
- ClinicOS "before Lyfework vs after Lyfework" sections

## When NOT to Use

- Non-visual comparisons (use a table or tabs instead)
- More than 2 comparison sliders per page
- Images that are very different in composition (alignment matters)
- Mobile layouts where drag area is too narrow

## Pairs Well With

- `animated-content` - Scroll reveal the comparison slider
- `blur-text` - "See the Difference" headline above the slider
- `glow-card` - Comparison slider inside a glowing card frame
- `spotlight-card` - Comparison slider as the hero of a spotlight section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| beforeImage | string | "" | Before image URL |
| afterImage | string | "" | After image URL |
| beforeLabel | string | "Before" | Left side label |
| afterLabel | string | "After" | Right side label |
| startPosition | number | 50 | Initial divider position (0-100) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ComparisonSlider-TS-TW
```

## Lyfework Customization Notes

- Divider line: 2px white with a circular drag handle
- Drag handle: glass background with Lyfework gradient border
- Labels: Manrope 700, small, positioned at top corners
- `startPosition={50}` for equal reveal. Set to 30 to show more "after" by default.
- Perfect for Lyfework portfolio pages showing website transformations
- Works in GHL with vanilla JS drag implementation

## Performance Notes

- Pure CSS clip-path or overflow-based reveal
- Touch-friendly drag on mobile
- Images should be same dimensions for alignment
- Zero animation libraries needed
