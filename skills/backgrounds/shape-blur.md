---
name: shape-blur
source: ReactBits
source_url: https://reactbits.dev/backgrounds/shape-blur
category: backgrounds
tags: background, shapes, blur, gradient, organic, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ShapeBlur

> Large blurred gradient shapes (circles, blobs) floating and slowly drifting in the background. Like Aurora but with distinct, separate blurred shapes rather than a unified flow.

## When to Use

- Hero backgrounds where Aurora feels too uniform
- Section backgrounds that need colorful depth with distinct shapes
- Creative landing pages with a playful, modern feel
- Behind pricing or feature sections for visual warmth
- Any dark section that needs color accents without being overwhelming

## When NOT to Use

- Behind text-heavy content at high opacity
- Combined with other animated backgrounds
- Light themes (shapes need dark contrast to glow)
- Minimal/corporate designs where shapes feel too casual

## Pairs Well With

- `blur-text` - Text reveal over drifting blurred shapes
- `spotlight-card` - Cards floating over colorful shape background
- `noise` - Noise overlay on top of shape blur for premium texture
- `animated-content` - Content reveals over the shapes

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| shapes | ShapeConfig[] | [] | Array of shape definitions |
| speed | number | 0.5 | Drift speed |
| blur | number | 80 | Blur amount in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ShapeBlur-TS-TW
```

## Lyfework Customization Notes

- Shape colors: `#ff642a` at 15% opacity + `#ff0301` at 10% opacity for Lyfework
- `blur` of 60-100px for soft, atmospheric shapes
- 2-4 shapes max. More than 5 gets muddy.
- Position shapes asymmetrically for visual interest
- Works in GHL (CSS blur filter on positioned divs)

## Performance Notes

- CSS only (positioned divs with blur filter)
- GPU accelerated blur
- Gentle CSS animation for drift
- Lightweight on all devices
