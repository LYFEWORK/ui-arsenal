---
name: canvas-fractal-grid
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/canvas-fractal-grid
category: backgrounds
tags: canvas, fractal, grid, animated, webgl, background, generative
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# CanvasFractalGrid

> Canvas-rendered fractal grid animation with higher performance than DOM-based version.

## When to Use
- Same use cases as FractalGrid but requiring higher depth or smoother animation
- Tech product pages where fractal depth > 4 is desired
- Full-screen background animations needing consistent 60fps
- Interactive generative backgrounds responding to scroll or mouse
- High-resolution displays where DOM-based grids cause jank

## When NOT to Use
- Pages requiring SSR-rendered backgrounds (canvas is client-only)
- Low-end mobile devices without hardware-accelerated canvas
- GHL embedded pages where canvas may have rendering conflicts
- Sites prioritizing smallest possible JS bundle

## Pairs Well With
- `aurora` - Aurora glow behind canvas fractal creates sci-fi atmosphere
- `spotlight-card` - Spotlight cards floating over animated fractal canvas
- `shimmer-button` - Shimmer CTA draws attention over mesmerizing background
- `animated-content` - Staggered content entrance over fractal animation

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| depth | number | 5 | Fractal recursion depth (1-8) |
| color | string | '#ffffff' | Grid line color |
| opacity | number | 0.1 | Line opacity |
| speed | number | 1 | Animation speed multiplier |
| lineWidth | number | 1 | Grid line width in pixels |
| interactive | boolean | false | Enable mouse interaction |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/canvas-fractal-grid"
```

## Usage Example
```jsx
import { CanvasFractalGrid } from "@/components/ui/canvas-fractal-grid";

export function TechHero() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      <CanvasFractalGrid
        depth={5}
        color="#ff642a"
        opacity={0.06}
        speed={0.3}
        lineWidth={0.5}
        interactive={true}
        className="absolute inset-0"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Infinite Possibilities
        </h1>
        <p className="font-manrope font-400 text-white/50 mt-4">
          Generative technology for the modern web.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Brand orange #ff642a at 0.04-0.08 opacity for subtle grid lines on #0a0a0a
- Canvas renders at device pixel ratio -- crisp on Retina displays
- Manrope 800 with text-shadow for readability over animated canvas
- Prefer this over DOM FractalGrid when depth > 4
- Avoid in GHL pages; use hero-static-radial as fallback

## Performance Notes
- Single canvas element vs DOM FractalGrid's exponential node count
- Handles depth 6-7 smoothly where DOM version struggles at depth 5
- Uses requestAnimationFrame with automatic off-screen pausing
- Interactive mode adds mousemove listener -- throttled to 60fps
- Memory footprint is fixed regardless of depth (no DOM allocation)
