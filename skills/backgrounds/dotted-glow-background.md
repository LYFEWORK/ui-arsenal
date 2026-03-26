---
name: dotted-glow-background
source: Aceternity UI
source_url: https://ui.aceternity.com/components/dotted-glow-background
category: backgrounds
tags: dots, glow, radial, background, pattern, accent, subtle
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# DottedGlowBackground

> Dotted pattern background with a radial glow accent, creating depth with a grid of dots and a central luminous highlight.

## When to Use
- Feature sections with structured dot grid texture
- Card section backgrounds with radial glow focal point
- Hero sections with subtle tech-forward grid aesthetic
- CTA sections with glowing accent behind content
- About or team sections with ambient background structure

## When NOT to Use
- On light-themed pages where dots and glow are invisible
- When competing with other grid/pattern backgrounds
- For hero sections that need clean, uncluttered backgrounds

## Pairs Well With
- `spotlight-card` - Cards floating over the dotted glow grid
- `gradient-text` - Gradient headings centered over the glow
- `animated-content` - Content stagger on the dotted background
- `count-up` - Animated stats with glow emphasis behind them

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the background |
| className | string | - | Classes for the container |
| dotColor | string | "rgba(255,255,255,0.1)" | Color of the dot pattern |
| glowColor | string | "#ff642a" | Color of the radial glow accent |
| glowSize | string | "40%" | Size of the glow area |

## Installation
```bash
npx aceternity-ui@latest add dotted-glow-background
```

## Usage Example
```jsx
import { DottedGlowBackground } from "@/components/ui/dotted-glow-background";

export function StatsSection() {
  return (
    <DottedGlowBackground className="bg-[#0a0a0a] py-24 px-6" glowColor="#ff642a">
      <div className="max-w-6xl mx-auto text-center relative z-10">
        <h2 className="font-[Manrope] font-800 text-4xl text-white mb-16">
          By the <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Numbers</span>
        </h2>
        <div className="grid grid-cols-2 md:grid-cols-4 gap-8">
          <div>
            <p className="font-[Manrope] font-800 text-4xl text-white">150+</p>
            <p className="font-[Manrope] font-400 text-neutral-400 mt-2">Projects</p>
          </div>
          <div>
            <p className="font-[Manrope] font-800 text-4xl text-white">98%</p>
            <p className="font-[Manrope] font-400 text-neutral-400 mt-2">Client Satisfaction</p>
          </div>
        </div>
      </div>
    </DottedGlowBackground>
  );
}
```

## Lyfework Customization Notes
- Set `glowColor` to `#ff642a` for brand-colored radial glow
- Dots at `rgba(255,255,255,0.1)` provide subtle grid on #0a0a0a
- Content uses `relative z-10` to sit above background layers
- Manrope 800 for stats and headings, 400 for labels
- Pure CSS; fully GHL compatible without any JavaScript dependencies

## Performance Notes
- Dot pattern is a CSS `radial-gradient` repeated via `background-size`, zero DOM cost
- Glow is a single `radial-gradient` overlay, GPU-composited
- No JavaScript, no animation frames, no ongoing computation
- Combined background layers render as a single paint operation
- Works on all browsers including Safari without fallback
