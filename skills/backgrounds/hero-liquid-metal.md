---
name: hero-liquid-metal
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/hero-liquid-metal
category: backgrounds
tags: hero, liquid, metal, chrome, 3d, background, premium
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# HeroLiquidMetal

> Liquid metal flowing hero background effect with chrome-like reflections and organic movement.

## When to Use
- Premium SaaS or luxury brand hero sections
- Product launch pages requiring high-impact visuals
- Portfolio sites showcasing cutting-edge design capability
- Dark-themed landing pages where metallic sheen adds sophistication
- Creative agency homepages pushing visual boundaries

## When NOT to Use
- Performance-sensitive mobile-first sites
- Medical or clinical sites requiring approachable, warm aesthetics
- Pages with tight performance budgets (Lighthouse-critical)
- Low-end device target audiences

## Pairs Well With
- `aurora` - Aurora glow behind liquid metal creates ethereal depth
- `gradient-text` - Chrome text over liquid metal doubles the premium feel
- `shimmer-button` - Metallic shimmer CTA complements liquid metal theme
- `tilted-card` - Tilted cards with glass effect over liquid metal background

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | '#c0c0c0' | Base metal color |
| speed | number | 0.5 | Flow animation speed |
| distortion | number | 0.3 | Surface distortion intensity |
| reflectivity | number | 0.8 | Chrome reflection strength |
| resolution | number | 512 | Shader texture resolution |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/hero-liquid-metal"
```

## Usage Example
```jsx
import { HeroLiquidMetal } from "@/components/ui/hero-liquid-metal";

export function PremiumHero() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      <HeroLiquidMetal
        color="#ff642a"
        speed={0.3}
        distortion={0.25}
        reflectivity={0.7}
        resolution={512}
        className="absolute inset-0 opacity-80"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen">
        <h1 className="font-manrope font-800 text-7xl text-white drop-shadow-2xl">
          Liquid Precision
        </h1>
        <p className="font-manrope font-400 text-white/70 mt-6 max-w-md text-center">
          Premium digital experiences that flow naturally.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Tint metal with brand orange #ff642a for warm chrome effect on #0a0a0a
- Reduce resolution to 256 on mobile for performance
- Manrope 800 with drop-shadow ensures readability over reflective surface
- Not recommended for GHL funnel pages due to WebGL requirements
- Combine with `lyf-glass` overlays for content sections above the fold

## Performance Notes
- WebGL/shader-based -- requires GPU acceleration
- Resolution prop has quadratic impact on performance (512 vs 1024 is 4x)
- Drops to static fallback on devices without WebGL support
- Use IntersectionObserver to pause when off-screen
- Budget 15-25ms per frame on mid-range devices at resolution 512
