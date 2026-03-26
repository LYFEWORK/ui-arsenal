---
name: glowing-stars-background
source: Aceternity UI
source_url: https://ui.aceternity.com/components/glowing-stars-background
category: backgrounds
tags: stars, glow, night, sky, background, animated, cosmic
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# GlowingStarsBackground

> Night sky background with animated glowing stars that pulse and shimmer, creating a cosmic atmospheric effect.

## When to Use
- Hero sections for AI or space-themed products
- Premium feature sections with celestial atmosphere
- About pages with aspirational "reach for the stars" messaging
- Testimonial sections with dreamy night-sky feel
- Event or launch pages with cosmic energy

## When NOT to Use
- On daytime/bright themed pages
- When the brand has no alignment with cosmic/tech aesthetics
- For medical or clinical sites where professionalism is priority

## Pairs Well With
- `gradient-text` - Gradient headings over the star field
- `blur-text` - Text entrance animation against the starry backdrop
- `particles` - Combine stars with floating particles for layered depth
- `animated-content` - Content fades in over the night sky

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the stars |
| className | string | - | Classes for the container |
| starCount | number | 50 | Number of stars to render |

## Installation
```bash
npx aceternity-ui@latest add glowing-stars-background
```

## Usage Example
```jsx
import { GlowingStarsBackgroundCard } from "@/components/ui/glowing-stars";

export function VisionSection() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-md mx-auto">
        <GlowingStarsBackgroundCard className="rounded-[12px]">
          <div className="p-8">
            <h3 className="font-[Manrope] font-800 text-2xl text-white">Our Vision</h3>
            <p className="font-[Manrope] font-400 text-neutral-400 mt-3">
              Building the future of healthcare technology, one pixel at a time.
            </p>
            <button className="mt-6 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-6 py-2 rounded-[8px]">
              Learn More
            </button>
          </div>
        </GlowingStarsBackgroundCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Star glow can be tinted with brand orange `#ff642a` for warm cosmic feel
- Card uses `rounded-[12px]` on #0a0a0a background
- Manrope 800 for card titles, 700 for CTA, 400 for descriptions
- CTA uses gradient `from-[#ff642a] to-[#ff0301]` with `rounded-[8px]`
- Zero JS dependencies; works in GHL without build configuration

## Performance Notes
- Stars are CSS-only elements with `@keyframes` opacity pulsing
- Each star is a small DOM element; 50 stars is the sweet spot for visual density
- Animations use `opacity` transitions only, GPU-composited
- No canvas or WebGL; pure DOM rendering for broad compatibility
- Staggered animation delays prevent synchronized pulsing for natural feel
