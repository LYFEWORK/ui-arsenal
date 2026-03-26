---
name: magic-rings
source: ReactBits
source_url: https://reactbits.dev/animations/magic-rings
category: animations
tags: rings, circles, pulse, expand, ambient, decorative
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# MagicRings

> Concentric animated rings that expand and pulse outward from a center point, creating a radar-like ambient effect for backgrounds and focal points.

## When to Use

- Behind profile photos or avatars to create a "broadcasting" or "active" visual
- Hero section ambient decoration behind the main heading
- Loading or processing states that feel more branded than a generic spinner
- CTA buttons with a pulsing ring aura to draw attention
- Map pin or location markers to signal a pulsing "we are here" indicator

## When NOT to Use

- Dense content layouts where the rings overlap with readable text
- Multiple instances close together (rings compete and create visual noise)
- E-commerce product grids where rings behind every item is excessive
- Minimalist designs that prioritize negative space

## Pairs Well With

- `particles` - Rings pulsing outward through a particle field creates depth
- `blur-text` - Center a BlurText heading inside the rings for a focal hero treatment
- `gradient-text` - Brand gradient text centered in the ring pulse
- `animated-content` - Trigger ring expansion on scroll entry for dramatic reveal

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| ringCount | number | 4 | Number of concentric rings |
| color | string | "#ff642a" | Ring stroke color |
| maxRadius | number | 200 | Maximum expansion radius in pixels |
| duration | number | 3 | Full expansion cycle duration in seconds |
| strokeWidth | number | 1.5 | Ring border thickness in pixels |
| opacity | number | 0.3 | Starting opacity of each ring |
| stagger | number | 0.6 | Delay between each ring's start in seconds |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MagicRings-TS-TW
```

## Usage Example

```jsx
import MagicRings from '@/components/ui/MagicRings';

function ClinicHero() {
  return (
    <section className="relative bg-[#0a0a0a] min-h-[80vh] flex items-center justify-center font-[Manrope]">
      <div className="absolute inset-0 flex items-center justify-center pointer-events-none">
        <MagicRings
          ringCount={5}
          color="#ff642a"
          maxRadius={300}
          duration={4}
          opacity={0.15}
          strokeWidth={1}
        />
      </div>
      <div className="relative z-10 text-center max-w-2xl px-8">
        <h1 className="text-5xl font-bold text-white leading-tight">
          Your Smile,{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Reimagined
          </span>
        </h1>
        <p className="mt-6 text-lg text-gray-400">
          Modern cosmetic dentistry with a personal touch.
        </p>
        <button className="mt-8 px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
          Book Consultation
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Set `color="#ff642a"` with `opacity={0.15}` for subtle brand-colored rings on `#0a0a0a`.
- For a more dramatic look, increase `opacity` to 0.25 and reduce `ringCount` to 3.
- Position the ring container with `absolute inset-0` and `pointer-events-none` so content layers above.
- Use `rounded-full` on the ring container if placing it behind a circular avatar or logo.
- GHL pages: the SVG rings render correctly in iframes; no special handling needed.
- Ensure content above the rings uses `relative z-10` to stay interactive and readable with Manrope font.

## Performance Notes

- Pure CSS keyframe animation on SVG circles -- no JS runtime
- Each ring uses `opacity` and `scale` transitions which are GPU composited
- The entire component is a single SVG element with `ringCount` circle children
- Very lightweight: ~1.5KB total, zero dependencies
- `will-change: transform, opacity` is applied per ring for smooth animation
