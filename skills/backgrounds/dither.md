---
name: dither
source: ReactBits
source_url: https://reactbits.dev/backgrounds/dither
category: backgrounds
tags: background, dither, pattern, retro, gradient, texture, pixel
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Dither

> A dithered gradient/pattern background that creates a retro pixel-art texture effect. Adds tactile, nostalgic depth to sections that need a raw, editorial aesthetic.

## When to Use

- Retro or editorial-themed portfolio pages
- Creative agency landing pages that want a raw, textured feel
- Background for testimonial sections where a subtle texture beats flat color
- Design-forward SaaS pages targeting creative professionals
- Behind feature grids to add visual interest without distraction

## When NOT to Use

- Clean, minimal corporate or medical sites (conflicts with polished aesthetic)
- Behind product photography or UI screenshots (texture competes with detail)
- Small card backgrounds where the dither pattern becomes mud
- Mobile-first designs where the pixel pattern may not render clearly

## Pairs Well With

- `split-text` - Text revealing over a dithered background has an editorial magazine feel
- `gradient-text` - Gradient text over dither creates an interesting texture contrast
- `spotlight-card` - Cards with spotlight hover over dithered sections feel elevated
- `blur-text` - Blur reveal text over the textured background adds depth to the reveal

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#000000","#333333"] | Colors for the dither gradient |
| pattern | string | "bayer" | Dither algorithm: "bayer", "floyd-steinberg", "ordered" |
| scale | number | 2 | Pixel scale of the dither pattern |
| intensity | number | 0.5 | How pronounced the dither effect is (0-1) |
| animated | boolean | false | Whether the dither pattern shifts over time |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Dither-TS-TW
```

## Usage Example

```jsx
import Dither from '@/components/ui/Dither';
import SplitText from '@/components/ui/SplitText';

function PortfolioHeader() {
  return (
    <section className="relative py-32 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <Dither
          colors={['#0a0a0a', '#ff642a', '#ff0301']}
          pattern="bayer"
          scale={3}
          intensity={0.4}
        />
      </div>

      <div className="relative z-10 max-w-4xl mx-auto px-8 text-center">
        <SplitText
          text="Selected Works"
          className="text-5xl md:text-7xl font-bold text-white font-[Manrope]"
          delay={80}
        />
        <p className="mt-6 text-gray-400 text-lg font-[Manrope]">
          A curated collection of builds that moved the needle.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework dither palette: `['#0a0a0a', '#ff642a', '#ff0301']` for a dark base fading into brand
- Keep `intensity` at 0.3-0.5 to maintain subtlety. Above 0.7 the texture overwhelms.
- `scale` of 2-4 works best on desktop. On mobile, bump to 3-5 so the pattern doesn't become noise.
- For client builds, use their primary color at 20-30% intensity over `#0a0a0a` for a tasteful texture
- GHL: render as an SVG pattern or CSS background-image. The dither pattern can be baked as a static image for GHL compatibility.
- Combine with Manrope bold headings for that editorial, design-forward look

## Performance Notes

- Canvas-based rendering for the dither algorithm
- Static dither (non-animated) has zero ongoing performance cost after initial render
- Animated dither is lightweight but adds per-frame computation
- Consider pre-rendering the dither as a static image for production builds
- SSR: renders a solid fallback color, dither generates on client
