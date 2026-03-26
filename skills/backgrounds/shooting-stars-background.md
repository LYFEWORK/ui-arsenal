---
name: shooting-stars-background
source: Aceternity UI
source_url: https://ui.aceternity.com/components/shooting-stars-background
category: backgrounds
tags: shooting-stars, meteor, background, animated, cosmic, trail
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# ShootingStarsBackground

> Animated shooting stars that streak across the background at random intervals, creating a dynamic cosmic atmosphere.

## When to Use
- Hero sections with celestial or aspirational themes
- CTA sections with subtle ambient motion
- Testimonial or review sections with cosmic backdrop
- Event countdown or launch announcement pages
- Portfolio headers with dramatic night-sky energy

## When NOT to Use
- On bright/light themed pages where stars are invisible
- When the page already has heavy foreground animation
- For medical or legal pages requiring conservative design

## Pairs Well With
- `glowing-stars-background` - Static stars + shooting stars for full night sky
- `gradient-text` - Gradient headings over the starfield
- `blur-text` - Text fades in while stars streak past
- `animated-content` - Content animates on the cosmic backdrop

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the stars |
| className | string | - | Classes for the container |
| starColor | string | "#fff" | Color of the shooting stars |
| trailColor | string | "#ff642a" | Color of the star trail |
| frequency | number | 3000 | Milliseconds between star appearances |

## Installation
```bash
npx aceternity-ui@latest add shooting-stars-background
```

## Usage Example
```jsx
import { ShootingStars, StarsBackground } from "@/components/ui/shooting-stars";

export function LaunchHero() {
  return (
    <section className="bg-[#0a0a0a] min-h-[600px] flex items-center justify-center relative overflow-hidden">
      <StarsBackground />
      <ShootingStars />
      <div className="text-center relative z-10 px-6">
        <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
          Launch Your{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Digital Presence
          </span>
        </h1>
        <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6 max-w-xl mx-auto">
          Clinic websites that look otherworldly and perform exceptionally.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Trail color set to `#ff642a` for brand-colored star streaks
- Section uses #0a0a0a with `overflow: hidden` to contain star animation
- Content at `z-10` for proper layering above star elements
- Manrope 800 for headline, 400 for subtext with gradient keyword highlights
- Zero dependencies; works in any GHL iframe or embed context

## Performance Notes
- Shooting stars use CSS `@keyframes` with `translateX/Y` and `opacity`, GPU-only
- Each star is a single DOM element with gradient trail via `linear-gradient` background
- Random spawn timing prevents synchronized animation patterns
- Maximum 3-5 active stars at once prevents DOM buildup
- Stars are removed from DOM after animation completes, no memory leak
