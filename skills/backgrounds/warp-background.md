---
name: warp-background
source: Magic UI
source_url: https://magicui.design/docs/components/warp-background
category: backgrounds
tags: warp, distort, organic, flowing, background
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# WarpBackground

> Warped, distorted flowing organic background with animated mesh-like gradients.

## When to Use
- Hero section backgrounds for creative or AI product pages
- Behind feature grids for visual depth and movement
- CTA sections needing an immersive ambient background
- Portfolio or agency landing page backdrops
- Abstract visual sections between content blocks

## When NOT to Use
- Content-heavy sections where the distortion distracts from reading
- Performance-critical mobile-first pages
- When aurora or particles backgrounds are already providing ambient motion
- Minimal/clean design systems that avoid complex backgrounds

## Pairs Well With
- `gradient-text` - Gradient headings above the warp background
- `animated-content` - Content fading in over the warped backdrop
- `spotlight-card` - Cards with spotlight hover floating above the warp
- `magic-card` - Magic cards layered over the organic background

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content rendered above the background |
| className | string | "" | Additional CSS classes |
| beamSize | number | 250 | Size of the warp beam effect |
| speed | number | 1 | Animation speed multiplier |
| gridColor | string | "#ffffff10" | Color of the grid overlay |
| beamsPerSide | number | 3 | Number of beams per side |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/warp-background"
```

## Usage Example
```jsx
import { WarpBackground } from "@/components/magicui/warp-background";

export function ImmersiveHero() {
  return (
    <WarpBackground
      className="min-h-screen flex items-center justify-center"
      gridColor="rgba(255, 100, 42, 0.08)"
      speed={0.8}
    >
      <div className="text-center z-10">
        <h1 className="font-manrope font-800 text-6xl text-white mb-6">
          Build the{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            impossible
          </span>
        </h1>
        <p className="font-manrope font-400 text-white/60 text-xl mb-10 max-w-lg mx-auto">
          Next-generation SaaS platforms for healthcare, built by Lyfework.
        </p>
        <button className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 px-10 py-4 rounded-[8px] text-lg">
          Explore our work
        </button>
      </div>
    </WarpBackground>
  );
}
```

## Lyfework Customization Notes
- Set `gridColor` to `rgba(255, 100, 42, 0.08)` for a subtle brand-tinted grid
- Use `speed={0.8}` or lower for a calm, professional ambient motion
- Content above the warp needs sufficient contrast — use white text with `text-white`
- Works best as a full-section background (`min-h-screen`) on `#0a0a0a`
- GHL compatible — CSS/SVG-based warp rendering, no WebGL dependency

## Performance Notes
- CSS animation with transforms and filters — moderate GPU usage
- Reduce `beamsPerSide` on mobile for better performance
- Lower `speed` reduces animation complexity
- Consider lazy initialization for below-fold sections
- Test on lower-end devices — warp distortion can be GPU intensive
