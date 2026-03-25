---
name: lightning
source: ReactBits
source_url: https://reactbits.dev/backgrounds/lightning
category: backgrounds
tags: background, lightning, electric, energy, dramatic, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Lightning

> Animated lightning bolts that arc across a dark background. Electric, high-energy effect. Bolts randomly spawn and fade with realistic branching.

## When to Use

- High-energy launch or announcement pages
- Gaming, esports, or entertainment brand hero sections
- "Power" or "energy" themed product pages
- Section backgrounds for dramatic emphasis on a key message
- Event countdown pages

## When NOT to Use

- Calm, professional, or minimal brand aesthetics
- Medical or wellness verticals (lightning = anxiety, not calm)
- Pages with other animated backgrounds
- Frequent viewing pages (lightning gets old fast)

## Pairs Well With

- `text-scramble` - Text decoding over lightning for electric reveal
- `blur-text` - Headline appears between lightning strikes
- `gradient-text` - Electric blue/white gradient text over lightning

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| boltColor | string | "rgba(255,255,255,0.8)" | Lightning bolt color |
| frequency | number | 3 | Average bolts per second |
| branchDepth | number | 3 | Branch complexity |
| fadeSpeed | number | 0.5 | Bolt fade duration in seconds |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Lightning-TS-TW
```

## Lyfework Customization Notes

- Bolt color: white or `rgba(255,100,42,0.8)` for Lyfework orange lightning
- `frequency` of 1-3 bolts per second. Above 5 is overwhelming.
- Tier 3. One per site. Only for very specific builds.
- Not for GHL (Canvas-based rendering)
- Add a dark overlay to ensure text readability

## Performance Notes

- Canvas 2D rendering
- Random generation per frame for active bolts only
- Low CPU cost between strikes
- Works on mobile but reduce frequency
