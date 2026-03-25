---
name: threads
source: ReactBits
source_url: https://reactbits.dev/backgrounds/threads
category: backgrounds
tags: background, threads, lines, weave, fabric, elegant, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Threads

> Thin animated lines that weave and flow across the background like fabric threads or silk strands. More structured than Ribbons, more elegant than Particles.

## When to Use

- Fashion, textile, or luxury brand pages
- Elegant section backgrounds for premium service businesses
- Behind testimonial sections for visual texture
- Abstract backgrounds that need movement without heavy visuals
- Alternative to Particles for brands where dots feel too techy

## When NOT to Use

- Behind dense content (lines can interfere with text)
- Bright/light backgrounds (threads need dark contrast)
- Combined with Ribbons or Particles (visual conflict)
- Heavy image layouts

## Pairs Well With

- `blur-text` - Elegant text over flowing threads
- `fade-content` - Soft content entrance matching thread elegance
- `glow-card` - Premium card over a threaded background
- `noise` - Noise overlay adds depth to the thread texture

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| threadColor | string | "rgba(255,255,255,0.06)" | Thread line color |
| threadCount | number | 20 | Number of thread lines |
| speed | number | 1 | Movement speed |
| amplitude | number | 50 | Wave amplitude of threads |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Threads-TS-TW
```

## Lyfework Customization Notes

- Thread color: `rgba(255,100,42,0.04)` for barely-there Lyfework tint
- `threadCount` of 15-30. Too few looks empty. Too many looks like static.
- `speed` of 0.5-1.0 for gentle flow
- Great for med spa and luxury dental client builds
- Canvas-based, works in GHL with careful testing

## Performance Notes

- Canvas 2D line rendering
- Low CPU cost for smooth curve calculations
- Works on mobile with reduced thread count
