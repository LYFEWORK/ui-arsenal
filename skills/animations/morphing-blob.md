---
name: morphing-blob
source: ReactBits
source_url: https://reactbits.dev/animations/morphing-blob
category: animations
tags: blob, morph, organic, shape, ambient, decorative, svg
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# MorphingBlob

> An SVG blob shape that continuously morphs between organic forms. Smooth, ambient shape-shifting. Used as a decorative element or behind content.

## When to Use

- Background decorative element behind cards or text
- Hero section accent shape
- Behind team photos or avatars as an organic frame
- Loading states or ambient page decorations
- Wellness, creative, or organic brand aesthetics

## When NOT to Use

- As a primary background (too small, use Aurora or Waves instead)
- Technical or structured brand aesthetics
- More than 2-3 blobs per page
- Over complex layouts (blobs add visual noise)

## Pairs Well With

- `blur-text` - Headline with morphing blob accent behind key word
- `fade-content` - Blob fades in alongside content
- `gradient-text` - Gradient text with matching gradient blob
- `aurora` - Blob accent within an aurora hero section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#ff642a", "#ff0301"] | Gradient fill colors |
| size | number | 300 | Blob diameter in px |
| speed | number | 5 | Morph cycle duration in seconds |
| blur | number | 0 | Blur amount in px (for glow effect) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MorphingBlob-TS-TW
```

## Lyfework Customization Notes

- Colors: `['#ff642a', '#ff0301']` for Lyfework gradient blob
- `blur` of 40-80px creates a soft glow behind the blob
- `speed` of 4-8 seconds for ambient. Slower = more meditative.
- Position with `absolute` and offset from center for asymmetry
- Works in GHL (SVG animation with CSS)

## Performance Notes

- SVG path animation, GPU accelerated
- Zero JavaScript needed (CSS keyframe animation on SVG path)
- Negligible performance cost
- Works on all devices
