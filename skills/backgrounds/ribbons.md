---
name: ribbons
source: ReactBits
source_url: https://reactbits.dev/backgrounds/ribbons
category: backgrounds
tags: background, ribbons, flowing, 3d, elegant, luxury, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Ribbons

> Flowing 3D ribbon strands that weave across the screen with smooth, organic motion. Creates an elegant, luxury-brand feel. Mouse-interactive.

## When to Use

- Luxury or premium brand hero sections
- Fashion, beauty, or high-end service landing pages
- Wedding, event, or invitation-style pages
- Sections where Aurora is too abstract and you need something more structured
- Alternative to Waves for a more dynamic, 3D feel

## When NOT to Use

- Tech or hacker aesthetics (ribbons feel too elegant)
- Dense content pages (ribbons are visually prominent)
- Multiple animated backgrounds per page
- Performance-sensitive mobile-first builds

## Pairs Well With

- `blur-text` - Elegant text reveal over flowing ribbons
- `gradient-text` - Gradient brand name with ribbons behind
- `fade-content` - Soft content fade matching the gentle ribbon movement
- `glow-card` - Luxury cards over a ribbon background

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| ribbonColor | string | "rgba(255,100,42,0.3)" | Ribbon color |
| ribbonCount | number | 3 | Number of ribbon strands |
| speed | number | 1 | Animation speed |
| thickness | number | 30 | Ribbon width in px |
| mouseInteraction | boolean | true | Ribbons respond to cursor |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Ribbons-TS-TW
```

## Usage Example

```jsx
import Ribbons from '@/components/ui/Ribbons';

function LuxuryHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <Ribbons ribbonColor="rgba(255,100,42,0.15)" ribbonCount={3} speed={0.6} thickness={25} />
      </div>
      <div className="relative z-10 text-center">
        <h1 className="text-6xl font-extrabold text-white">Elevated by Design.</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Ribbon color: `rgba(255,100,42,0.12)` for Lyfework. Very subtle.
- `ribbonCount` of 2-4. More than 5 gets cluttered.
- `speed` of 0.4-0.8 for elegant flow. Above 1.0 feels anxious.
- Great for high-end client verticals: med spas, luxury dental, premium wellness
- Canvas-based, works in GHL with careful iframe testing

## Performance Notes

- Canvas 2D rendering, GPU-friendly
- Mouse interaction uses throttled event listeners
- Lighter than WebGL backgrounds (Aurora, Hyperspeed)
- Works on mobile at reduced ribbon count
