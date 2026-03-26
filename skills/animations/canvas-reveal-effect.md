---
name: canvas-reveal-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/canvas-reveal-effect
category: animations
tags: canvas, reveal, paint, brush, hover, effect, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# CanvasRevealEffect

> Canvas-based paint/brush reveal effect on hover, where dots or particles expand outward to reveal hidden content.

## When to Use
- Feature cards with dramatic hover-to-reveal interactions
- Service showcases where hovering reveals the value proposition
- Interactive portfolio items with canvas-powered reveals
- CTA sections with engaging hover-triggered revelations
- Skill or capability cards with animated content reveals

## When NOT to Use
- On mobile-only layouts where hover is unavailable
- For accessibility-critical content that must be always visible
- When many canvas instances would compete for GPU resources

## Pairs Well With
- `spotlight-card` - Combine canvas reveal with spotlight glow
- `gradient-text` - Gradient text inside revealed content
- `animated-content` - Card entrance animation before hover activation
- `particles` - Complementary particle effects around canvas cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| animationSpeed | number | 0.4 | Speed of the reveal animation |
| opacities | array | [0.3, 0.3, 0.3, 0.5, 0.5, 0.5, 0.8, 0.8, 0.8, 1] | Opacity steps |
| colors | array | [[0, 255, 255]] | RGB color arrays for dots |
| containerClassName | string | - | Classes for the container |
| dotSize | number | 3 | Size of individual dots |
| showGradient | boolean | true | Show gradient overlay |

## Installation
```bash
npx aceternity-ui@latest add canvas-reveal-effect
```

## Usage Example
```jsx
import { CanvasRevealEffect } from "@/components/ui/canvas-reveal-effect";

export function FeatureReveal() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <div className="lyf-glass rounded-[12px] border border-white/10 p-8 relative group overflow-hidden h-[300px]">
          <div className="relative z-10">
            <h3 className="font-[Manrope] font-700 text-xl text-white">Web Design</h3>
            <p className="font-[Manrope] font-400 text-neutral-400 text-sm mt-2">Custom clinic sites</p>
          </div>
          <CanvasRevealEffect
            animationSpeed={3}
            containerClassName="absolute inset-0 bg-transparent"
            colors={[[255, 100, 42], [255, 3, 1]]}
            dotSize={2}
          />
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Dot colors use RGB values matching brand: `[255, 100, 42]` (#ff642a) and `[255, 3, 1]` (#ff0301)
- Cards use `lyf-glass` with `rounded-[12px]` and `border border-white/10`
- Manrope 700 for card titles, 400 for descriptions on #0a0a0a
- Content must be `z-10` or higher to sit above the canvas layer
- Ensure `overflow: hidden` on card containers for clean canvas bounds

## Performance Notes
- Canvas rendering uses 2D context with requestAnimationFrame loop
- Each canvas instance has its own rendering context; limit to 3-4 per viewport
- Dot animation pauses when component is off-screen via IntersectionObserver
- GPU memory usage scales with canvas size and dot density
- Hover-only activation means zero GPU cost when not interacting
