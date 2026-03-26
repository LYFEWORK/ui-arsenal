---
name: comet-card
source: Aceternity UI
source_url: https://ui.aceternity.com/components/comet-card
category: components
tags: card, comet, glow, border, trail, animation, css
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# CometCard

> Card with animated comet streak/trail effect along the border, creating a dynamic glowing trail animation.

## When to Use
- Highlighting premium features or pricing tiers
- Drawing attention to CTA cards on dark landing pages
- Creating featured case study or portfolio cards
- Emphasizing key statistics or metric cards
- Building eye-catching announcement or new feature cards

## When NOT to Use
- On light backgrounds where the glow trail is barely visible
- For content-dense card grids where animation distracts
- When the page already has heavy border animations elsewhere

## Pairs Well With
- `spotlight-card` - Combine comet trail with spotlight glow for layered effects
- `gradient-text` - Use gradient headings inside comet cards
- `count-up` - Animate numbers inside the featured card
- `particles` - Add background particles behind the card section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Card content |
| className | string | - | Additional classes for the card |
| gradientSize | number | 200 | Size of the comet glow in pixels |
| gradientColor | string | "#ff642a" | Color of the comet trail |

## Installation
```bash
npx aceternity-ui@latest add comet-card
```

## Usage Example
```jsx
import { CometCard } from "@/components/ui/comet-card";

export function FeaturedPlan() {
  return (
    <section className="bg-[#0a0a0a] py-24 flex justify-center">
      <CometCard className="lyf-glass rounded-[12px] p-8 max-w-sm">
        <span className="text-xs font-[Manrope] font-700 uppercase tracking-wider bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Most Popular
        </span>
        <h3 className="font-[Manrope] font-800 text-3xl text-white mt-2">Growth Plan</h3>
        <p className="font-[Manrope] font-400 text-neutral-400 mt-3">
          Everything you need to scale your clinic with AI-powered automation.
        </p>
        <div className="mt-6">
          <span className="font-[Manrope] font-800 text-4xl text-white">$297</span>
          <span className="text-neutral-500 font-[Manrope] font-400">/month</span>
        </div>
        <button className="mt-8 w-full bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 py-3 rounded-[8px]">
          Get Started
        </button>
      </CometCard>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `gradientColor` to `#ff642a` to match Lyfework brand gradient start color
- Apply `lyf-glass` class for frosted background effect on the #0a0a0a dark theme
- Use `rounded-[12px]` for card containers, `rounded-[8px]` for buttons
- Manrope 800 for pricing/headings, 700 for CTAs, 400 for descriptions
- Pure CSS animation means zero JS overhead and full GHL iframe compatibility

## Performance Notes
- Pure CSS animation using `@keyframes` and `conic-gradient`, no JavaScript
- Zero dependency component, smallest bundle footprint in the arsenal
- Animation uses `will-change: transform` for GPU compositing
- Single pseudo-element for the comet trail, minimal DOM overhead
- Works on all modern browsers including Safari 15+
