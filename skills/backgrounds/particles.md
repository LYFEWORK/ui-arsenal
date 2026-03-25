---
name: particles
source: ReactBits
source_url: https://reactbits.dev/backgrounds/particles
category: backgrounds
tags: background, particles, dots, ambient, network, connecting, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Particles

> An animated particle field with floating dots that connect with lines when near each other. The classic premium tech background. Interactive (particles respond to mouse).

## When to Use

- Tech-forward landing pages and SaaS hero sections
- Background for "About" or "Technology" sections
- Full-page backgrounds where Aurora feels too organic and you need something more technical
- Behind stats/metrics sections to reinforce data/technology positioning
- Client builds in tech, healthcare tech, or B2B SaaS verticals

## When NOT to Use

- Lifestyle, wellness, or organic-feeling brands (particles feel too "techy")
- Behind dense content (the connecting lines can interfere with readability)
- Pages that already have another animated background (one per page max)
- Creative/artsy brands where the effect feels overused and expected

## Pairs Well With

- `blur-text` - Particle background with blur-revealing headline
- `split-text` - Technical text reveal over particle field
- `count-up` - Animated stat counters over particles for metrics sections
- `spotlight-card` - Cards floating over a subtle particle background

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| particleCount | number | 50 | Number of particles |
| particleColor | string | "#ffffff" | Color of the dots |
| lineColor | string | "rgba(255,255,255,0.1)" | Color of connecting lines |
| particleSize | number | 2 | Dot radius in pixels |
| speed | number | 1 | Movement speed multiplier |
| connectionDistance | number | 150 | Max distance for line connections |
| mouseInteraction | boolean | true | Particles respond to cursor |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Particles-TS-TW
```

## Usage Example

```jsx
import Particles from '@/components/ui/Particles';

function TechSection() {
  return (
    <section className="relative py-32 overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Particles
          particleCount={40}
          particleColor="rgba(255,100,42,0.6)"
          lineColor="rgba(255,100,42,0.08)"
          particleSize={1.5}
          speed={0.5}
          connectionDistance={120}
          mouseInteraction={true}
        />
      </div>
      <div className="relative z-10 text-center px-8">
        <h2 className="text-4xl font-extrabold text-white">
          Smart Systems. Real Results.
        </h2>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- For Lyfework: use brand orange particles `rgba(255,100,42,0.5)` with very subtle line connections `rgba(255,100,42,0.06)`
- For client builds: use their accent color at 40-60% opacity for dots, 5-10% for lines
- Keep `particleCount` between 30-60. Below 30 feels empty. Above 80 feels busy.
- `speed` of 0.3-0.6 for ambient. Above 1.0 for energetic sections.
- Always set parent container to `position: relative; overflow: hidden;`
- For GHL: the canvas element needs explicit width/height. Set container to 100% width and a fixed or vh-based height.
- On mobile, reduce `particleCount` to 20-30 and disable `mouseInteraction`

## Performance Notes

- Uses HTML5 Canvas (GPU accelerated)
- 50 particles is negligible CPU cost on modern devices
- Above 100 particles, older mobile devices may stutter
- The canvas redraws on requestAnimationFrame, pauses when tab is hidden
- Connection line calculations are O(n^2), keep count reasonable
- SSR: renders empty canvas, populates on client mount
