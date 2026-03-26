---
name: fractal-grid
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/fractal-grid
category: backgrounds
tags: fractal, grid, animated, pattern, generative, background
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# FractalGrid

> Animated fractal pattern grid background with recursive geometric subdivisions.

## When to Use
- Tech-forward SaaS hero sections conveying algorithmic precision
- Developer tool or API product pages emphasizing computation
- Creative coding portfolios demonstrating generative art skills
- Conference or hackathon sites with technical visual identity
- Dark-themed landing pages needing mesmerizing background motion

## When NOT to Use
- Healthcare or clinic sites where organic/warm aesthetics are preferred
- Mobile-first pages where complex animation drains battery
- Content-heavy pages where background competes with readability
- Sites targeting older browsers without CSS animation support

## Pairs Well With
- `particles` - Particles floating over fractal grid creates layered tech aesthetic
- `number-ticker` - Animated stats over fractal grid emphasize data-driven narrative
- `blur-text` - Blur-reveal text entrance over fractal grid adds drama
- `gradient-text` - Gradient headings over geometric patterns create visual harmony

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| depth | number | 4 | Fractal recursion depth (1-6) |
| color | string | '#ffffff' | Grid line color |
| opacity | number | 0.1 | Line opacity |
| speed | number | 1 | Animation speed multiplier |
| cellSize | number | 100 | Base cell size in pixels |
| animated | boolean | true | Enable subdivision animation |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/fractal-grid"
```

## Usage Example
```jsx
import { FractalGrid } from "@/components/ui/fractal-grid";

export function DevToolHero() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      <FractalGrid
        depth={4}
        color="#ff642a"
        opacity={0.08}
        speed={0.5}
        cellSize={120}
        className="absolute inset-0"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen px-6">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Build at Scale
        </h1>
        <p className="font-manrope font-400 text-white/60 mt-4 max-w-lg text-center">
          APIs that grow with your business.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use brand orange #ff642a at very low opacity (0.05-0.10) for subtle brand-colored grid
- Keep depth at 3-4 to balance visual complexity with performance on #0a0a0a
- Manrope 800 headings need sufficient contrast -- keep grid opacity low
- Not ideal for GHL embeds due to animation complexity
- Combine with `lyf-glass` overlays for content cards

## Performance Notes
- Depth has exponential impact on DOM nodes (depth 5 = 1024+ elements)
- Keep depth <= 4 on mobile devices
- CSS transform animations are GPU-accelerated
- Use IntersectionObserver to pause when off-screen
- Static mode (animated={false}) has near-zero runtime cost
