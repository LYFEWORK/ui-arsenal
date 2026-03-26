---
name: globe
source: Magic UI
source_url: https://magicui.design/docs/components/globe
category: components
tags: globe, 3d, earth, interactive, cobe
dependencies: cobe
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Globe

> Interactive 3D rotating globe rendered on canvas, perfect for showcasing global reach or server locations.

## When to Use
- Hero sections demonstrating global SaaS reach
- "Available worldwide" feature sections
- Server or CDN location visualizations
- International clinic network showcases
- Premium landing page visual anchors

## When NOT to Use
- Mobile-first designs where 3D performance is a concern
- Pages requiring fast LCP — canvas rendering delays paint
- When a simpler dotted-map would communicate the same message
- Low-end device targets where WebGL may not be available

## Pairs Well With
- `particles` - Subtle star-field particles behind the globe
- `aurora` - Aurora glow effect beneath the globe
- `gradient-text` - "Global reach" heading with brand gradient
- `count-up` - Animated country/user count stats beside the globe

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| className | string | "" | Additional CSS classes |
| config | object | {} | Cobe globe configuration object |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/globe"
```

## Usage Example
```jsx
import { Globe } from "@/components/magicui/globe";

export function GlobalReachHero() {
  return (
    <section className="relative bg-[#0a0a0a] py-24 overflow-hidden">
      <div className="mx-auto max-w-6xl flex flex-col lg:flex-row items-center gap-12 px-6">
        <div className="flex-1 text-center lg:text-left">
          <h1 className="font-manrope font-800 text-5xl text-white mb-6">
            Your clinic,{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              everywhere
            </span>
          </h1>
          <p className="font-manrope font-400 text-white/60 text-lg max-w-md">
            Lyfework powers patient scheduling across 30+ countries with sub-100ms response times.
          </p>
        </div>
        <div className="flex-1 relative aspect-square max-w-lg">
          <Globe className="w-full h-full" />
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Configure cobe marker colors to use `#ff642a` for location pins
- Globe base color should be dark (matching `#0a0a0a`) with subtle grid lines
- Glow color can use a muted version of the brand orange for ambient light
- Place on dark backgrounds only — the canvas transparent edges blend with `#0a0a0a`
- GHL note: Canvas element renders fine in GHL embeds, but test on target funnels

## Performance Notes
- Uses `cobe` library which renders on HTML Canvas via WebGL
- Runs a requestAnimationFrame loop — adds ~2-5% CPU on desktop
- Disable or reduce quality on mobile with media queries
- Lazy-load the component and only initialize when in viewport
- Consider `will-change: transform` on the container for GPU compositing
