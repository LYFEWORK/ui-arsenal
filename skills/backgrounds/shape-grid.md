---
name: shape-grid
source: ReactBits
source_url: https://reactbits.dev/backgrounds/shape-grid
category: backgrounds
tags: background, shapes, grid, geometric, animated, pattern, mosaic
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ShapeGrid

> A grid of animated geometric shapes (circles, squares, triangles) that rotate, scale, or shift in coordinated patterns. Creates a dynamic, mosaic-like background with geometric rhythm.

## When to Use

- Design-forward SaaS landing pages for a modern, geometric aesthetic
- Architecture or design firm portfolio backgrounds
- Feature grid sections where the background pattern echoes the content grid
- Math, science, or education-themed product pages
- Behind pricing or comparison sections for visual structure

## When NOT to Use

- Organic, flowing, or natural-themed pages (geometric shapes feel too rigid)
- Behind photographic content (geometric shapes compete with organic images)
- Very text-heavy sections where the shapes become a distraction
- Sections smaller than 300px height (shapes need room to form a pattern)

## Pairs Well With

- `spotlight-card` - Cards over the shape grid create a design-system cohesive look
- `animated-content` - Content appearing in sync with shape animations
- `gradient-text` - Geometric gradient text over the shape grid reinforces the theme
- `count-up` - Metrics appearing within the geometric pattern

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| shapes | string[] | ["circle","square"] | Shape types: "circle", "square", "triangle", "hexagon" |
| gridSize | number | 60 | Size of each grid cell |
| shapeSize | number | 20 | Size of each shape within its cell |
| color | string | "rgba(255,255,255,0.05)" | Color of the shapes |
| animation | string | "rotate" | Animation type: "rotate", "scale", "fade", "none" |
| speed | number | 0.5 | Animation speed |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ShapeGrid-TS-TW
```

## Usage Example

```jsx
import ShapeGrid from '@/components/ui/ShapeGrid';
import SpotlightCard from '@/components/ui/SpotlightCard';

function DesignServicesSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <ShapeGrid
          shapes={['circle', 'square']}
          gridSize={70}
          shapeSize={16}
          color="rgba(255,100,42,0.05)"
          animation="rotate"
          speed={0.2}
        />
      </div>

      <div className="relative z-10 max-w-6xl mx-auto px-8">
        <h2 className="text-3xl font-bold text-white text-center font-[Manrope]">
          Design Systems That Scale
        </h2>
        <div className="mt-12 grid grid-cols-1 md:grid-cols-3 gap-8">
          <SpotlightCard className="p-8 rounded-2xl">
            <h3 className="text-xl font-bold text-white font-[Manrope]">Brand Identity</h3>
            <p className="mt-3 text-gray-400">Logos, colors, typography, rules.</p>
          </SpotlightCard>
          <SpotlightCard className="p-8 rounded-2xl">
            <h3 className="text-xl font-bold text-white font-[Manrope]">Component Libraries</h3>
            <p className="mt-3 text-gray-400">Reusable, consistent, documented.</p>
          </SpotlightCard>
          <SpotlightCard className="p-8 rounded-2xl">
            <h3 className="text-xl font-bold text-white font-[Manrope]">Implementation</h3>
            <p className="mt-3 text-gray-400">Pixel-perfect builds, every time.</p>
          </SpotlightCard>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework shape color: `rgba(255,100,42,0.05)` for a barely-there brand geometric texture
- Use `['circle', 'square']` for a clean, modern look. Adding `'triangle'` feels more edgy.
- `animation="rotate"` at `speed={0.15-0.25}` is the most elegant. Faster feels jittery.
- `shapeSize` should be roughly 25-35% of `gridSize` for balanced spacing
- GHL: replicate with CSS `background-image` using SVG shape patterns
- For client builds: adjust shape color to their primary at 3-5% opacity

## Performance Notes

- Each shape is a small SVG or CSS element with a simple transform animation
- Many small elements means DOM count can grow. Keep total shapes under 200.
- CSS `transform: rotate()` animations are GPU-accelerated
- Consider reducing grid density on mobile for fewer DOM nodes
- SSR-compatible, renders static shapes and animates on client
