---
name: retro-grid
source: Magic UI
source_url: https://magicui.design/docs/components/retro-grid
category: backgrounds
tags: grid, retro, perspective, vaporwave, floor
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# RetroGrid

> Perspective vanishing-point retro floor grid with a vaporwave/synthwave aesthetic.

## When to Use
- Hero section backgrounds for tech or AI product landing pages
- "The future" themed sections with retro-futuristic vibes
- Product launch pages with dramatic visual anchors
- Developer tool landing pages with synthwave aesthetic
- CTA sections needing a bold background treatment

## When NOT to Use
- Clean, minimal designs where the grid is too visually heavy
- Medical or corporate sites requiring conservative backgrounds
- Sections with complex content that needs a quiet background
- When the aurora or particles background is already in use

## Pairs Well With
- `gradient-text` - Gradient headings floating above the retro grid
- `animated-content` - Content that fades in above the grid background
- `pulsating-button` - Pulsing CTA button on the grid horizon
- `blur-text` - Blur-reveal heading above the retro grid

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| className | string | "" | Additional CSS classes |
| angle | number | 65 | Perspective tilt angle in degrees |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/retro-grid"
```

## Usage Example
```jsx
import { RetroGrid } from "@/components/magicui/retro-grid";

export function AIProductHero() {
  return (
    <section className="relative bg-[#0a0a0a] py-32 overflow-hidden">
      <RetroGrid className="opacity-50" />
      <div className="relative z-10 text-center">
        <h1 className="font-manrope font-800 text-5xl text-white mb-6">
          The{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            AI-powered
          </span>{" "}
          clinic OS
        </h1>
        <p className="font-manrope font-400 text-white/60 text-lg mb-10 max-w-lg mx-auto">
          Scheduling intelligence that learns and adapts to your practice.
        </p>
        <button className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 px-10 py-4 rounded-[8px] text-lg">
          Get early access
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set grid line color to brand-tinted white (`rgba(255, 100, 42, 0.15)`) for subtle brand presence
- Use `opacity-50` or lower on the grid to keep content readable
- Container must be `relative overflow-hidden` to contain the grid perspective
- Content above the grid needs `relative z-10` to layer correctly
- GHL compatible — pure CSS grid with perspective transform, no JS dependencies

## Performance Notes
- Pure CSS with `linear-gradient` and `perspective` — zero JavaScript overhead
- Grid lines are rendered via CSS repeating gradients — lightweight
- Perspective transform is GPU composited
- No animation by default — static background (add CSS animation if desired)
- No additional DOM elements — renders as a pseudo-element or single div
