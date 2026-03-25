---
name: grid-distortion
source: ReactBits
source_url: https://reactbits.dev/backgrounds/grid-distortion
category: backgrounds
tags: background, grid, distortion, warp, mouse, interactive, WebGL
dependencies: three.js
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# GridDistortion

> A flat grid that warps and distorts where the mouse hovers. Creates a fabric-stretching effect on a wireframe grid. Interactive, responsive to cursor position.

## When to Use

- Tech or engineering brand hero sections
- Interactive portfolio backgrounds
- Creative agency showcase builds
- Sections where the interaction IS the visual (no competing content)
- Builds targeting developer or designer audiences

## When NOT to Use

- Content-heavy sections (distortion distracts from reading)
- Mobile-first builds (no cursor interaction)
- Standard business sites
- Combined with other cursor effects

## Pairs Well With

- `blur-text` - Headline over distorting grid
- `crosshair` - Crosshair cursor + grid distortion
- `text-scramble` - Tech text over warping grid

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| gridSize | number | 30 | Grid cell count |
| lineColor | string | "rgba(255,255,255,0.1)" | Grid line color |
| distortionStrength | number | 50 | Warp intensity on hover |
| smoothing | number | 0.3 | Warp recovery speed |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GridDistortion-TS-TW
```

## Lyfework Customization Notes

- Line color: `rgba(255,100,42,0.06)` for Lyfework tint
- Tier 3 showcase. Use for Lyfework portfolio or creative client builds.
- `distortionStrength` of 30-60 for controlled warp. Above 80 gets wild.
- Not for GHL (Three.js required)
- Desktop only

## Performance Notes

- Three.js WebGL rendering
- Heavy dependency (~150kb)
- Only justify if this is the hero visual
- Smooth on modern hardware, laggy on older devices
