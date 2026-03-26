---
name: parallax-grid-scroll
source: Aceternity UI
source_url: https://ui.aceternity.com/components/parallax-grid-scroll
category: backgrounds
tags: parallax, grid, scroll, 3d, depth, perspective, background
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# ParallaxGridScroll

> 3D grid background with parallax depth effect on scroll, creating a receding floor/ceiling grid perspective.

## When to Use
- Tech-forward hero sections with cyberpunk/retro grid aesthetic
- AI product pages with "entering the matrix" visual metaphor
- Feature sections needing futuristic depth backdrop
- Developer tool landing pages with technical grid feel
- Gaming or tech event pages with immersive backgrounds

## When NOT to Use
- For clean/minimal brand aesthetics where grids feel too tech-heavy
- On healthcare sites where clinical professionalism is expected
- When scroll performance is critical on low-end devices

## Pairs Well With
- `gradient-text` - Gradient headlines over the parallax grid
- `floating-navbar` - Transparent nav over the grid hero
- `blur-text` - Text entrance as grid scrolls into view
- `particles` - Floating particles above the grid surface

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the grid |
| className | string | - | Classes for the container |
| gridColor | string | "rgba(255,255,255,0.1)" | Grid line color |
| perspective | number | 800 | CSS perspective value |

## Installation
```bash
npx aceternity-ui@latest add parallax-grid-scroll
```

## Usage Example
```jsx
import { ParallaxGridScroll } from "@/components/ui/parallax-grid-scroll";

export function TechHero() {
  return (
    <ParallaxGridScroll className="bg-[#0a0a0a] min-h-screen flex items-center justify-center" gridColor="rgba(255,100,42,0.08)">
      <div className="text-center relative z-10 px-6">
        <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
          The Future of{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Web Design
          </span>
        </h1>
        <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6 max-w-2xl mx-auto">
          AI-powered. Performance-first. Built for growth.
        </p>
        <button className="mt-10 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px]">
          Explore Our Work
        </button>
      </div>
    </ParallaxGridScroll>
  );
}
```

## Lyfework Customization Notes
- Grid color tinted with brand: `rgba(255,100,42,0.08)` for subtle orange grid lines
- Content requires `relative z-10` to float above the grid plane
- #0a0a0a background for the grid to recede into darkness
- Manrope 800 for headline, 700 for CTA, 400 for subtext
- Test parallax scroll behavior in GHL iframe; may need adjusted perspective values

## Performance Notes
- Grid lines are CSS `linear-gradient` repeated patterns, rendered as single background
- Parallax scroll transforms use `useTransform` for efficient per-frame updates
- 3D perspective transform is GPU-composited via `transform: perspective()`
- Single background element means minimal DOM overhead
- Scroll-driven animation pauses when section is out of viewport
