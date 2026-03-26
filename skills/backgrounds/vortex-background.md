---
name: vortex-background
source: Aceternity UI
source_url: https://ui.aceternity.com/components/vortex-background
category: backgrounds
tags: vortex, spiral, swirl, background, animated, dramatic, canvas
dependencies: none
variants: both
license: Free for commercial use
tier: 3
added: 2026-03-25
---

# VortexBackground

> Swirling vortex or spiral animated background with particles being drawn into a central point, creating dramatic visual pull.

## When to Use
- Dramatic hero sections for product launches
- AI or data processing visualizations showing convergence
- CTA sections pulling user attention toward the center
- Event or conference pages with high-energy aesthetics
- Premium feature showcases needing maximum visual impact

## When NOT to Use
- On pages where motion sensitivity is a concern
- For subtle or minimal brand aesthetics
- When the page already has heavy animation elsewhere
- On mobile devices where canvas performance may suffer

## Pairs Well With
- `gradient-text` - Gradient headline at the vortex center
- `blur-text` - Text materializes from the vortex center
- `floating-navbar` - Transparent nav above the vortex hero
- `animated-content` - Content emerges from the vortex on scroll

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered at the vortex center |
| className | string | - | Classes for the container |
| particleCount | number | 200 | Number of vortex particles |
| baseSpeed | number | 0.01 | Rotation speed of the vortex |
| rangeSpeed | number | 1.5 | Speed variation range |
| baseRadius | number | 0 | Starting radius for particles |
| rangeRadius | number | 200 | Radius variation range |

## Installation
```bash
npx aceternity-ui@latest add vortex-background
```

## Usage Example
```jsx
import { Vortex } from "@/components/ui/vortex";

export function DramaticHero() {
  return (
    <section className="bg-[#0a0a0a] min-h-screen relative overflow-hidden">
      <Vortex
        particleCount={150}
        className="flex items-center justify-center min-h-screen"
      >
        <div className="text-center relative z-10 px-6">
          <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
            Everything Converges{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Here
            </span>
          </h1>
          <p className="font-[Manrope] font-400 text-neutral-300 text-xl mt-6 max-w-xl mx-auto">
            The intersection of AI, design, and healthcare innovation.
          </p>
          <button className="mt-10 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px] text-lg">
            Enter the Vortex
          </button>
        </div>
      </Vortex>
    </section>
  );
}
```

## Lyfework Customization Notes
- Particle color can include brand orange `#ff642a` for warm vortex tones
- Background base is #0a0a0a for maximum particle visibility
- Content centered at `z-10` with Manrope 800 headline, 400 subtext
- CTA uses gradient `from-[#ff642a] to-[#ff0301]` with `rounded-[8px]`
- Test canvas rendering performance in GHL iframe before deploying

## Performance Notes
- Canvas-based rendering using 2D context with requestAnimationFrame loop
- 150-200 particles is the visual sweet spot without GPU strain
- Tier 3 complexity; reserve for primary hero sections only
- Reduce `particleCount` on mobile (100 or less) for smooth 30fps+
- Canvas pauses when tab is inactive or section is off-screen
- GPU memory scales with canvas size; avoid full-viewport on retina without size limits
