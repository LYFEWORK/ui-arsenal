---
name: hero-color-panels
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/hero-color-panels
category: backgrounds
tags: hero, color, panels, blocks, background, layout
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# HeroColorPanels

> Multi-panel color block hero background with animated panel transitions.

## When to Use
- Landing pages needing bold, segmented color blocking
- Portfolio sites showcasing multiple service categories visually
- SaaS product pages with distinct feature color-coding
- Creative agency homepages with strong visual identity
- Campaign pages requiring eye-catching above-the-fold impact

## When NOT to Use
- Minimal or text-focused landing pages where panels add clutter
- Sites with heavy imagery that conflicts with color blocks
- Single-purpose squeeze pages where simplicity converts better

## Pairs Well With
- `aurora` - Aurora glow layered within panels creates depth
- `gradient-text` - Gradient headings complement panel color scheme
- `spotlight-card` - Spotlight cards placed over panels for feature highlights
- `dock` - Floating dock navigation over panel hero section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| panels | { color: string; width?: string }[] | [] | Panel definitions with colors and widths |
| direction | 'horizontal' \| 'vertical' | 'horizontal' | Panel layout direction |
| animated | boolean | true | Enable panel entrance animations |
| duration | number | 0.8 | Animation duration in seconds |
| gap | number | 0 | Gap between panels in pixels |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/hero-color-panels"
```

## Usage Example
```jsx
import { HeroColorPanels } from "@/components/ui/hero-color-panels";

export function SaaSHero() {
  return (
    <section className="relative min-h-screen">
      <HeroColorPanels
        panels={[
          { color: "#0a0a0a", width: "30%" },
          { color: "#1a0a05", width: "40%" },
          { color: "#ff642a", width: "30%" },
        ]}
        direction="horizontal"
        animated={true}
        duration={1.0}
      />
      <div className="relative z-10 flex items-center justify-center min-h-screen">
        <div className="lyf-glass rounded-[12px] p-10 max-w-2xl text-center">
          <h1 className="font-manrope font-800 text-5xl text-white">
            One Platform. Every Channel.
          </h1>
          <p className="font-manrope font-400 text-white/60 mt-4">
            Unify your marketing, sales, and delivery workflows.
          </p>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use brand palette: #0a0a0a as base, #ff642a and #ff0301 as accent panels
- Apply `lyf-glass` cards over panels to maintain readability
- Manrope 700/800 headings pop against solid color blocks
- Set gap={0} for seamless panel joins on dark backgrounds
- Panels work inside GHL funnels as full-width section backgrounds

## Performance Notes
- Pure CSS-driven panels with optional Framer Motion entrance
- Zero JavaScript overhead in static mode
- Animation uses CSS transforms only -- GPU accelerated
- Panel count has negligible performance impact (DOM nodes only)
- Fully SSR-compatible with no hydration mismatch risk
