---
name: prismatic-burst
source: ReactBits
source_url: https://reactbits.dev/backgrounds/prismatic-burst
category: backgrounds
tags: background, prismatic, burst, rays, spectrum, dramatic, energy
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# PrismaticBurst

> An intense burst of prismatic light rays radiating outward with spectral color separation. The high-energy sibling of Prism, designed for explosive visual impact.

## When to Use

- Product launch hero sections for maximum dramatic impact
- Event or festival landing pages with a celebration theme
- Creative agency "showcase" or "reel" sections
- Achievement pages or year-in-review hero sections
- One-time campaign pages where visual fireworks are appropriate

## When NOT to Use

- Any standard client site (too dramatic for everyday use)
- Professional or conservative brand pages
- Pages with more than one animated background component
- Mobile-primary experiences (rendering intensity)
- Accessibility-critical pages (color intensity and motion)

## Pairs Well With

- `blur-text` - Bold text emerging from the burst center is the ultimate dramatic reveal
- `gradient-text` - Spectral gradient text radiating with the burst
- `count-up` - Achievement numbers at the center of the burst
- `animated-content` - Content appearing after the burst settles

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| rayCount | number | 24 | Number of prismatic rays |
| colors | string[] | ["#ff0080","#ff8c00","#40e0d0","#8a2be2"] | Spectral colors for the rays |
| intensity | number | 0.7 | Brightness of the burst (0-1) |
| speed | number | 0.5 | Rotation speed of the burst |
| origin | object | { x: "50%", y: "50%" } | Burst center point |
| pulse | boolean | true | Whether the burst pulses in intensity |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PrismaticBurst-TS-TW
```

## Usage Example

```jsx
import PrismaticBurst from '@/components/ui/PrismaticBurst';
import BlurText from '@/components/ui/BlurText';

function AnniversaryHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <PrismaticBurst
          rayCount={20}
          colors={['#ff642a', '#ff0301', '#ffffff', '#ff642a']}
          intensity={0.4}
          speed={0.2}
          origin={{ x: '50%', y: '50%' }}
          pulse={true}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="5 YEARS OF BUILDING"
          delay={200}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-xl text-gray-200 font-[Manrope]">
          Half a decade of infrastructure that refuses to quit.
        </p>
        <button className="mt-10 px-10 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg font-[Manrope]">
          Celebrate With Us
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework burst: `['#ff642a', '#ff0301', '#ffffff', '#ff642a']` for a warm spectral explosion
- Keep `intensity` at 0.3-0.5 to avoid washing out the content
- `speed` of 0.1-0.3 for a majestic rotation. Above 0.5 becomes a disco ball.
- The `pulse` effect should breathe slowly (3-5 second cycle) for a premium feel
- Only use for Lyfework milestones, launches, or special campaign pages
- GHL: not recommended. The ray rendering and pulsing are too complex for CSS-only replication.
- Layer `bg-black/40` between the burst and text for reliable readability

## Performance Notes

- Uses CSS `conic-gradient` with multiple color stops and rotation animation
- More rendering cost than simple gradients due to the ray count and pulse animation
- Reduce `rayCount` on mobile and consider disabling `pulse`
- The pulsing animation uses `opacity` transitions which are GPU-friendly
- SSR-compatible, renders a static burst pattern and animates on client
