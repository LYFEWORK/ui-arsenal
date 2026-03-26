---
name: hexagon-background
source: Animate UI
source_url: https://animate-ui.com/docs/components/backgrounds/hexagon-background
category: backgrounds
tags: hexagon, grid, pattern, geometric, background, tech
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# HexagonBackground

> Animated hexagonal grid pattern background with hover illumination and subtle pulse effects on individual cells.

## When to Use
- Tech or engineering-themed landing pages
- SaaS product pages with a structured, systematic aesthetic
- Data or analytics dashboards needing a tech-forward background
- Security or infrastructure product pages
- Feature grid sections where hex cells echo the grid layout

## When NOT to Use
- Organic, wellness, or lifestyle brand sites where geometric patterns feel cold
- Content-heavy reading pages where the grid distracts
- Mobile layouts where the hexagons are too small to appreciate
- Sites with a rounded, soft design language

## Pairs Well With
- `spotlight-card` - spotlight cards on top of hex grid create a layered tech aesthetic
- `gradient-text` - gradient heading over geometric hex background
- `number-ticker` - metric counters styled to fit within hex cells
- `blur-text` - text reveals over the structured hex pattern

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| cellSize | number | 40 | Size of each hexagon in pixels |
| gap | number | 2 | Gap between hexagons |
| color | string | "rgba(255,255,255,0.05)" | Hexagon fill color |
| hoverColor | string | "rgba(255,100,42,0.15)" | Hexagon color on hover |
| animated | boolean | true | Enable pulse animation |
| className | string | — | Container CSS classes |
| strokeColor | string | "rgba(255,255,255,0.08)" | Hexagon border color |
| interactive | boolean | true | Enable hover illumination |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/hexagon-background"
```

## Usage Example
```jsx
import { HexagonBackground } from "@/components/ui/hexagon-background";

export function InfrastructureHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <HexagonBackground
        cellSize={50}
        color="rgba(255,255,255,0.03)"
        hoverColor="rgba(255,100,42,0.12)"
        strokeColor="rgba(255,255,255,0.06)"
        className="absolute inset-0"
      />
      <div className="relative z-10 text-center space-y-6 max-w-3xl px-6">
        <h1 className="font-manrope font-800 text-5xl text-white">
          Enterprise-Grade Infrastructure
        </h1>
        <p className="font-manrope font-400 text-gray-400 text-lg">
          Built for scale. Designed for reliability. Secured by default.
        </p>
        <button className="px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white">
          Explore Architecture
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Hover color: `"rgba(255,100,42,0.12)"` for brand-tinted hexagon illumination
- Base hex color: `"rgba(255,255,255,0.03)"` for barely-visible structure on `#0a0a0a`
- Stroke: `"rgba(255,255,255,0.06)"` for subtle grid lines
- Content: `relative z-10` layered above the hex background
- GHL compatible — SVG/CSS grid rendering, no JS conflicts
- Use `cellSize={50}` for desktop, consider larger cells on mobile for visibility

## Performance Notes
- SVG-based rendering — resolution-independent, sharp on all displays
- Hover detection uses CSS `:hover` on SVG elements — no JS event listeners
- Pulse animation is CSS keyframes — no JavaScript animation loop
- Grid is drawn once on mount — not recalculated per frame
- Large viewports may have 200+ hex cells — still performant due to SVG batching
