---
name: beams
source: ReactBits
source_url: https://reactbits.dev/backgrounds/beams
category: backgrounds
tags: background, beams, light, rays, animated, ambient, premium
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Beams

> Animated light beams that sweep across a dark background. Creates a dramatic, cinematic feel. More directional and structured than Aurora, less technical than Particles.

## When to Use

- Hero sections where Aurora feels too soft and Particles too technical
- Product launch or announcement pages that need dramatic energy
- "Coming soon" or waitlist pages
- Dark-themed sections that need movement without distraction
- Testimonial or social proof sections for visual weight

## When NOT to Use

- Light-themed pages (beams need dark contrast)
- Pages already using Aurora or Particles (one animated background per page)
- Behind forms or dense UI (beams can distract from inputs)
- Content-heavy sections where readability is priority

## Pairs Well With

- `blur-text` - Dramatic beam sweep behind blur-revealing headline
- `split-text` - Text reveals as beams sweep across
- `count-up` - Stats section with subtle beams behind the numbers
- `spotlight-card` - Cards with beam background for a cohesive dark section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| beamColor | string | "rgba(255,100,42,0.15)" | Color of the light beams |
| beamCount | number | 3 | Number of beams |
| speed | number | 1 | Animation speed |
| angle | number | 45 | Beam angle in degrees |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Beams-TS-TW
```

## Usage Example

```jsx
import Beams from '@/components/ui/Beams';
import BlurText from '@/components/ui/BlurText';

function AnnouncementHero() {
  return (
    <section className="relative min-h-[60vh] flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <Beams
          beamColor="rgba(255,100,42,0.1)"
          beamCount={4}
          speed={0.8}
          angle={35}
        />
      </div>
      <div className="relative z-10 text-center">
        <BlurText
          text="Something Big Is Coming."
          delay={120}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Beam color for Lyfework: `rgba(255,100,42,0.08)` (very subtle brand orange)
- For client builds: their brand accent at 5-12% opacity
- `beamCount` of 2-4 is ideal. More than 5 gets cluttered.
- `speed` of 0.5-1.0 for ambient. Keep it slow.
- Beams work best at angles between 25-50 degrees
- Always set parent to `overflow-hidden` and dark background
- For GHL: CSS-only implementation works fine in HTML sections

## Performance Notes

- Pure CSS animation (transforms and opacity)
- No JavaScript computation during animation
- Extremely lightweight, safe for any device
- No layout impact, purely decorative
