---
name: background-texture
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/background-texture
category: backgrounds
tags: texture, background, noise, grain, pattern, surface
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# BackgroundTexture

> Customizable background texture patterns including noise, grain, dots, and crosshatch overlays.

## When to Use
- Adding subtle surface texture to flat dark backgrounds
- Creating visual depth without heavy assets or animations
- Portfolio and creative sites needing tactile visual quality
- Layering under content sections for premium feel
- GHL funnel pages needing low-cost visual polish

## When NOT to Use
- Over photographic or video backgrounds where texture adds noise
- Ultra-minimal designs where any texture is unwanted
- When performance budget cannot accommodate a texture overlay div

## Pairs Well With
- `aurora` - Texture over aurora creates organic, layered atmosphere
- `spotlight-card` - Textured background makes spotlight effect more pronounced
- `gradient-text` - Gradient text over textured surface adds tactile contrast
- `marquee` - Scrolling marquee over textured background section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| pattern | 'noise' \| 'grain' \| 'dots' \| 'crosshatch' \| 'lines' | 'noise' | Texture pattern type |
| opacity | number | 0.15 | Texture overlay opacity |
| color | string | '#ffffff' | Texture color |
| scale | number | 1 | Pattern scale multiplier |
| blend | string | 'overlay' | CSS mix-blend-mode |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/background-texture"
```

## Usage Example
```jsx
import { BackgroundTexture } from "@/components/ui/background-texture";

export function TexturedSection() {
  return (
    <section className="relative bg-[#0a0a0a] py-24 px-6">
      <BackgroundTexture
        pattern="grain"
        opacity={0.08}
        color="#ffffff"
        blend="overlay"
        className="absolute inset-0 pointer-events-none"
      />
      <div className="relative z-10 max-w-5xl mx-auto">
        <h2 className="font-manrope font-700 text-4xl text-white text-center">
          Why Clients Choose Lyfework
        </h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6 mt-12">
          {/* Feature cards with lyf-glass */}
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use pattern="grain" with opacity={0.05-0.10} on #0a0a0a for subtle film grain
- White texture color with overlay blend creates natural depth on dark backgrounds
- Apply `pointer-events-none` to prevent texture from blocking interactions
- Pairs perfectly with lyf-glass cards for frosted glass over textured surface
- Safe for GHL pages -- lightweight CSS/SVG pattern with no JS dependency

## Performance Notes
- SVG-based patterns are resolution-independent and tiny in file size
- Noise pattern uses a single inline SVG filter -- no external assets
- pointer-events-none ensures zero interaction cost
- No JavaScript at runtime; pattern is pure CSS/SVG
- Works perfectly with SSR, no hydration needed
