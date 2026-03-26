---
name: gravity-stars-background
source: Animate UI
source_url: https://animate-ui.com/docs/components/backgrounds/gravity-stars-background
category: backgrounds
tags: stars, gravity, physics, space, background, interactive
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# GravityStarsBackground

> Star field background with gravity physics where stars are pulled toward the cursor or a gravitational center point.

## When to Use
- Space or tech-themed hero sections for SaaS products
- Interactive portfolio landing pages where cursor engagement matters
- Developer tool sites with cosmic, futuristic aesthetics
- About pages with philosophical or visionary messaging
- Dark-themed sections needing ambient interactive depth

## When NOT to Use
- Light-themed designs where stars on light backgrounds look odd
- Content-heavy pages where star movement distracts from reading
- Mobile layouts where cursor-based gravity has no trigger
- Sites requiring minimal JavaScript execution
- Pages already using another particle-based background

## Pairs Well With
- `particles` - layer gravity stars behind standard floating particles for depth
- `gradient-text` - gradient heading floating above gravitational star field
- `aurora` - combine aurora glow with gravity stars for layered cosmic background
- `spotlight-card` - glass cards floating in a gravitational star field

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| starCount | number | 100 | Number of stars |
| gravity | number | 0.5 | Gravitational pull strength |
| followCursor | boolean | true | Stars gravitate toward cursor |
| starColor | string | "#ffffff" | Star base color |
| starSize | [number, number] | [1, 3] | Min/max star size range |
| className | string | — | Container CSS classes |
| speed | number | 1 | Animation speed multiplier |
| connectionDistance | number | 0 | Draw lines between nearby stars (0 = disabled) |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/gravity-stars-background"
```

## Usage Example
```jsx
import { GravityStarsBackground } from "@/components/ui/gravity-stars-background";

export function SaaSHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <GravityStarsBackground
        starCount={80}
        gravity={0.3}
        followCursor
        starColor="#ffffff"
        starSize={[1, 2.5]}
        className="absolute inset-0"
      />
      <div className="relative z-10 text-center space-y-6 max-w-3xl px-6">
        <h1 className="font-manrope font-800 text-6xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Your Practice, Automated
        </h1>
        <p className="font-manrope font-400 text-gray-400 text-xl">
          AI-powered tools that handle scheduling, follow-ups, and reviews
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Star color: white (`#ffffff`) for maximum contrast on `#0a0a0a`
- Keep `gravity` at 0.3 for a subtle, ambient pull — not too aggressive
- Reduce `starCount` to 50-60 on mobile for performance
- Content must be `relative z-10` to layer above the star canvas
- GHL compatible — canvas rendering works within iframe embeds
- Consider adding a faint `bg-gradient-radial from-[#ff642a]/5 to-transparent` center glow

## Performance Notes
- Canvas-based rendering — all stars drawn in single paint pass
- Gravity calculations use spatial hashing for O(n) efficiency
- RequestAnimationFrame loop with automatic cleanup on unmount
- Mouse listener throttled to reduce calculation frequency
- On mobile, disable cursor following and use center-point gravity instead
