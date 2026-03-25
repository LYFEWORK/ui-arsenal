---
name: waves
source: ReactBits
source_url: https://reactbits.dev/backgrounds/waves
category: backgrounds
tags: background, waves, ocean, flowing, SVG, ambient, organic
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Waves

> Animated SVG wave layers that flow across the bottom or top of a section. Multiple wave layers with different speeds create parallax depth. Organic, calming aesthetic.

## When to Use

- Section dividers between dark and light sections
- Footer backgrounds that flow into the bottom of the page
- Health, wellness, or spa client websites
- Sections that need gentle movement without the intensity of Aurora or Particles
- CTA sections with a calming, inviting feel

## When NOT to Use

- Full-page backgrounds (waves work best as section accents)
- Tech/hacker aesthetics (too soft)
- More than 2 wave sections per page
- Behind dense content (waves can interfere with readability at intersections)

## Pairs Well With

- `animated-content` - Content reveals above the wave layer
- `blur-text` - Headline above flowing waves
- `count-up` - Stats section with waves gently flowing underneath
- `fade-content` - Soft fade-in content matches the soft wave aesthetic

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| lineColor | string | "rgba(255,100,42,0.2)" | Wave stroke color |
| backgroundColor | string | "transparent" | Background behind waves |
| waveSpeedX | number | 0.02 | Horizontal wave speed |
| waveSpeedY | number | 0.01 | Vertical wave speed |
| waveAmpX | number | 40 | Horizontal wave amplitude |
| waveAmpY | number | 20 | Vertical wave amplitude |
| layers | number | 3 | Number of wave layers |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Waves-TS-TW
```

## Usage Example

```jsx
import Waves from '@/components/ui/Waves';

function CTASection() {
  return (
    <section className="relative py-32 bg-[#0a0a0a]">
      <div className="absolute bottom-0 left-0 right-0 h-40">
        <Waves lineColor="rgba(255,100,42,0.15)" layers={3} waveSpeedX={0.015} />
      </div>
      <div className="relative z-10 text-center">
        <h2 className="text-4xl font-extrabold text-white">Ready to Build?</h2>
        <button className="mt-8 px-8 py-4 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
          Book Your Install
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Wave color: `rgba(255,100,42,0.12)` for Lyfework. Very subtle.
- `layers` of 2-4. More layers = more depth but more visual activity.
- Position waves at section bottom with `absolute bottom-0` and fixed height (120-200px)
- Great for healthcare/wellness clients where Particles feels too clinical
- Works in GHL (SVG animation with CSS)

## Performance Notes

- SVG-based animation, very lightweight
- CSS animations on path elements
- No JavaScript computation
- Works on all devices including mobile
