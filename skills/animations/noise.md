---
name: noise
source: ReactBits
source_url: https://reactbits.dev/animations/noise
category: animations
tags: noise, grain, texture, film, overlay, aesthetic
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Noise

> A film grain / noise texture overlay that adds analog warmth and depth to any section. Subtle animated static that prevents flat digital backgrounds from feeling sterile.

## When to Use

- Over dark hero backgrounds to add texture and depth
- Full-page overlay at very low opacity for premium feel
- Over gradient backgrounds to reduce banding
- Any dark section that feels too clean and flat
- Combined with other backgrounds (Aurora, Particles) as a finishing layer

## When NOT to Use

- Light backgrounds (noise is barely visible and just looks dirty)
- Over photography or imagery (noise degrades image quality perception)
- At high opacity (should be nearly invisible, felt not seen)

## Pairs Well With

- `aurora` - Aurora + noise overlay = premium atmospheric hero
- `particles` - Particles + noise for textured tech backgrounds
- `beams` - Beams + noise for cinematic sections
- Every dark background benefits from a noise layer

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| opacity | number | 0.05 | Noise visibility (0-1) |
| speed | number | 8 | Grain animation speed in fps |
| patternSize | number | 150 | Noise pattern tile size |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Noise-TS-TW
```

## Usage Example

```jsx
import Aurora from '@/components/ui/Aurora';
import Noise from '@/components/ui/Noise';

function TexturedHero() {
  return (
    <section className="relative min-h-screen overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Aurora colorStops={['#1a0a2e', '#ff642a', '#ff0301']} />
      </div>
      <div className="absolute inset-0 z-[1]">
        <Noise opacity={0.04} speed={8} />
      </div>
      <div className="relative z-10">{/* Content */}</div>
    </section>
  );
}
```

## Lyfework Customization Notes

- `opacity` of 0.03-0.06. Above 0.08 it becomes visible as grain. It should be felt, not seen.
- Layer ABOVE the background but BELOW the content (z-index between them)
- Use on every dark hero section as a standard finishing touch
- Works in GHL (CSS background-image with SVG noise filter or canvas)
- Add `pointer-events: none` so it doesn't block clicks

## Performance Notes

- Can be CSS-only (SVG filter) or Canvas-based
- CSS approach: zero JavaScript, negligible cost
- Canvas approach: low cost, renders once then tiles
- No performance concerns on any device
