---
name: animated-border
source: ReactBits
source_url: https://reactbits.dev/animations/animated-border
category: animations
tags: border, animated, gradient, rotating, card, wrapper
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# AnimatedBorder

> A gradient border that rotates around an element continuously. Different from StarBorder (single dot traveling) - this is a full gradient sweep around the entire perimeter.

## When to Use

- Featured cards or highlighted sections
- CTA containers that need visual weight
- Profile cards or team member highlights
- Testimonial callout boxes
- Any element where a static border should feel dynamic

## When NOT to Use

- Multiple elements with animated borders in the same viewport
- Light backgrounds (gradient border needs dark contrast)
- Small elements like buttons (use StarBorder instead)
- Minimal designs where border animation feels excessive

## Pairs Well With

- `spotlight-card` - Spotlight hover + animated border for premium card
- `blur-text` - Content inside animated border frame
- `glow-card` - Choose one: GlowCard OR AnimatedBorder, not both
- `lyf-glass` - Glass card with animated gradient border

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to wrap |
| colors | string[] | ["#ff642a","#ff0301","#ff642a"] | Gradient colors |
| speed | number | 3 | Rotation speed in seconds |
| borderWidth | number | 2 | Border thickness in px |
| borderRadius | number | 16 | Corner radius in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/AnimatedBorder-TS-TW
```

## Lyfework Customization Notes

- Colors: `['#ff642a','#ff0301','#ff642a']` for Lyfework gradient loop
- `speed` of 2-4s. Faster = more energetic. Slower = more elegant.
- `borderWidth` of 1-2px for subtle. 3-4px for prominent.
- `borderRadius={16}` matches Lyfework glass panel standard
- Works in GHL (CSS conic-gradient animation)

## Performance Notes

- Pure CSS with conic-gradient and rotation
- Zero JavaScript
- Negligible cost
