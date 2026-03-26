---
name: hero-static-radial
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/hero-static-radial
category: backgrounds
tags: hero, radial, gradient, static, background, lightweight
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# HeroStaticRadial

> Static radial gradient hero background with customizable center, colors, and spread.

## When to Use
- Any hero section needing a clean, performant gradient background
- Clinic and healthcare landing pages with professional aesthetics
- SaaS above-the-fold sections as a reliable default background
- GHL funnel pages where zero-JS backgrounds are essential
- Mobile-first pages requiring minimal overhead

## When NOT to Use
- When dynamic or interactive backgrounds are specifically requested
- Situations requiring texture, pattern, or imagery
- Pages that already have sufficient visual complexity

## Pairs Well With
- `blur-text` - Text reveal animations pop over static radial gradients
- `particles` - Sparse particles over radial gradient add depth without weight
- `spotlight-card` - Spotlight cards sitting on radial gradient hero
- `animated-content` - Animated entrance of content over clean gradient base

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ['#ff642a', '#0a0a0a'] | Radial gradient color stops |
| center | string | '50% 40%' | CSS position of gradient center |
| size | string | 'ellipse at center' | CSS radial-gradient size/shape |
| opacity | number | 1 | Background opacity |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/hero-static-radial"
```

## Usage Example
```jsx
import { HeroStaticRadial } from "@/components/ui/hero-static-radial";

export function ClinicLanding() {
  return (
    <section className="relative min-h-screen">
      <HeroStaticRadial
        colors={["#ff642a20", "#0a0a0a"]}
        center="50% 30%"
        className="absolute inset-0"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen px-6">
        <h1 className="font-manrope font-800 text-5xl text-white text-center">
          Your Health. Our Priority.
        </h1>
        <p className="font-manrope font-400 text-white/60 mt-4 max-w-lg text-center">
          Book your appointment online in seconds.
        </p>
        <button className="mt-8 px-8 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white">
          Book Now
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `colors={["#ff642a20", "#0a0a0a"]}` for subtle brand glow on dark base
- Pure CSS -- zero JavaScript, perfect for GHL funnel embeds
- Manrope 800 headings with brand gradient buttons pair naturally
- Adjust center to "50% 30%" to position glow behind hero heading
- Works seamlessly with 12px card radius and `lyf-glass` overlays

## Performance Notes
- Zero JavaScript -- pure CSS radial-gradient
- No repaints, no layout shifts, no hydration cost
- Renders identically on SSR and client
- Lighthouse performance impact: effectively zero
- Works on every browser and device including IE11 with fallback
