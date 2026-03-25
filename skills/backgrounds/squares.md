---
name: squares
source: ReactBits
source_url: https://reactbits.dev/backgrounds/squares
category: backgrounds
tags: background, squares, grid, geometric, minimal, subtle
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Squares

> A subtle animated grid of squares that pulse, fade, or shift in opacity. The lightest animated background option. Adds just enough texture to prevent flat surfaces without being distracting.

## When to Use

- Section backgrounds where Aurora or Particles are too much
- Behind feature grids or pricing tables for subtle depth
- Light or dark themed sections that need minimal ambient movement
- Professional/corporate builds where flashy backgrounds aren't appropriate
- Default background treatment when you want "something but not too much"

## When NOT to Use

- Hero sections that need impact (squares are too subtle for heroes)
- Creative/portfolio builds that need visual wow-factor
- Over complex imagery (squares blend into nothing)

## Pairs Well With

- `spotlight-card` - Cards over a subtle square grid
- `animated-content` - Content reveals over gently pulsing squares
- `count-up` - Stats section with squares providing texture
- `accordion` - FAQ section with subtle background pattern

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| squareSize | number | 40 | Size of each square in px |
| gridColor | string | "rgba(255,255,255,0.03)" | Square border/fill color |
| speed | number | 1 | Animation speed |
| pattern | "pulse" \| "wave" \| "random" | "pulse" | How squares animate |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Squares-TS-TW
```

## Usage Example

```jsx
import Squares from '@/components/ui/Squares';

function FeatureSection() {
  return (
    <section className="relative py-24 overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Squares squareSize={50} gridColor="rgba(255,255,255,0.025)" pattern="pulse" speed={0.5} />
      </div>
      <div className="relative z-10">{/* Feature cards */}</div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Grid color: `rgba(255,255,255,0.02)` on dark backgrounds. Barely visible.
- `squareSize` of 30-60px depending on section width
- This is the "safe" background choice. Use when unsure.
- Works perfectly in GHL (CSS grid + opacity animations)
- `pattern="pulse"` for calm sections. `"wave"` for slightly more movement.

## Performance Notes

- Pure CSS grid with opacity animations
- Zero JavaScript possible (CSS-only variant)
- Works on all devices, all browsers
- No performance concerns whatsoever
