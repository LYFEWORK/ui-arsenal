---
name: hero-dithering
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/hero-dithering
category: backgrounds
tags: hero, dithering, gradient, retro, pixel, background
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# HeroDithering

> Dithered gradient hero background with retro pixel pattern effect for textured, nostalgic visuals.

## When to Use
- Landing page hero sections needing a unique retro-modern aesthetic
- Portfolio or creative agency sites where texture adds personality
- SaaS product pages that want to stand out from smooth gradient competitors
- Event or campaign pages with a stylized visual identity
- Dark-mode hero sections where dithering adds subtle depth

## When NOT to Use
- Clean corporate or medical sites requiring polished minimalism
- Image-heavy layouts where dithering competes with photography
- Mobile-first designs where pixel patterns may alias badly on small screens

## Pairs Well With
- `gradient-text` - Dithered background with gradient text creates cohesive retro-modern hero
- `blur-text` - Blur reveal text over dithered background adds dramatic entrance
- `shimmer-button` - CTA shimmer stands out against matte dithered texture
- `particles` - Sparse particles over dithered gradient add layered depth

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ['#ff642a', '#ff0301'] | Gradient color stops for dithering |
| intensity | number | 0.5 | Dithering intensity (0-1) |
| pattern | 'ordered' \| 'floyd-steinberg' \| 'atkinson' | 'ordered' | Dithering algorithm |
| resolution | number | 4 | Pixel size for dither pattern |
| className | string | '' | Additional CSS classes |
| animate | boolean | false | Whether to animate the gradient shift |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/hero-dithering"
```

## Usage Example
```jsx
import { HeroDithering } from "@/components/ui/hero-dithering";

export function ClinicHero() {
  return (
    <section className="relative min-h-screen">
      <HeroDithering
        colors={["#0a0a0a", "#ff642a", "#ff0301"]}
        intensity={0.4}
        pattern="ordered"
        resolution={3}
        className="absolute inset-0"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen px-6">
        <h1 className="font-manrope font-800 text-5xl text-white">
          Transform Your Practice
        </h1>
        <p className="font-manrope font-400 text-lg text-white/70 mt-4 max-w-xl text-center">
          Modern patient experiences powered by Lyfework
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `colors={["#0a0a0a", "#ff642a", "#ff0301"]}` to match brand gradient on dark base
- Apply Manrope 800 for hero headings over dithered backgrounds for contrast
- Combine with `lyf-glass` overlays for content cards sitting on top
- Lower `resolution` to 2-3 for sharper dithering on Retina displays
- Test GHL embed iframes over dithered sections for z-index stacking

## Performance Notes
- Dithering is computed once on mount via canvas; no ongoing GPU cost
- Pattern resolution directly affects canvas pixel count -- keep resolution >= 3 on mobile
- Static mode has zero runtime overhead after initial render
- Animate mode uses requestAnimationFrame; disable on low-power devices
- SSR-safe: canvas renders client-side only via useEffect
