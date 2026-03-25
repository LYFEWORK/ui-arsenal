---
name: ballpit
source: ReactBits
source_url: https://reactbits.dev/backgrounds/ballpit
category: backgrounds
tags: background, balls, physics, 3d, interactive, playful, three.js
dependencies: three.js, cannon-es
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Ballpit

> 3D physics-based ball pit with realistic collision. Balls bounce, stack, and respond to mouse interaction. Three.js + physics engine. Maximum playful impact.

## When to Use

- Playful brand hero sections (kids, gaming, creative)
- Interactive "about us" or team culture pages
- Product launch pages for fun/casual products
- Showcase builds that need to demonstrate technical capability
- Event or party landing pages

## When NOT to Use

- Professional, corporate, or medical brands
- Mobile-first builds (3D physics is heavy)
- Pages with important content (ball pit is all-consuming visually)
- Performance-sensitive environments

## Pairs Well With

- `blur-text` - Headline floating above a ball pit
- `gradient-text` - Colorful text matching ball colors
- `click-spark` - Sparks when clicking balls

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| ballCount | number | 50 | Number of balls |
| colors | string[] | ["#ff642a","#ff0301","#ffffff"] | Ball colors |
| gravity | number | -9.81 | Physics gravity |
| restitution | number | 0.7 | Bounciness (0-1) |
| mouseInteraction | boolean | true | Balls respond to cursor |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Ballpit-TS-TW
```

## Lyfework Customization Notes

- Tier 3. Creative showcase only.
- Colors: brand-matched balls with white accents
- `ballCount` of 30-60. Above 80 tanks performance.
- Three.js + physics engine is a heavy combo (~250kb+)
- Not for GHL. React + Three.js builds only.
- Desktop focused. Provide a static gradient fallback on mobile.

## Performance Notes

- Three.js + cannon-es physics engine
- Heaviest component in the arsenal
- Requires WebGL + decent GPU
- Reduce ball count aggressively on mobile if supporting it
- Lazy load this component
