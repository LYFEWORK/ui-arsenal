---
name: wobble-card
source: Aceternity UI
source_url: https://ui.aceternity.com/components/wobble-card
category: components
tags: card, wobble, tilt, hover, playful, interactive, physics
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# WobbleCard

> Card with a playful wobble/tilt effect on hover, adding personality and engagement to card-based layouts.

## When to Use
- Feature cards on landing pages that need personality
- Blog post or article cards with playful hover
- Bento grid layouts with interactive wobble on hover
- Team member cards with friendly interaction feel
- Service or pricing cards that benefit from approachable design

## When NOT to Use
- On professional/corporate sites where playfulness is off-brand
- For cards containing complex interactive elements like forms
- When users need precise mouse targeting inside the card

## Pairs Well With
- `tilted-card` - Compare wobble vs tilt for different personality levels
- `gradient-text` - Gradient headings inside wobble cards
- `animated-content` - Entrance animation before wobble becomes active
- `spotlight-card` - Layer subtle spotlight with wobble effect

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Card content |
| className | string | - | Additional classes for the card |
| containerClassName | string | - | Classes for the outer wobble wrapper |

## Installation
```bash
npx aceternity-ui@latest add wobble-card
```

## Usage Example
```jsx
import { WobbleCard } from "@/components/ui/wobble-card";

export function FeatureBento() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6 max-w-6xl mx-auto">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        <WobbleCard containerClassName="col-span-2 bg-gradient-to-br from-[#ff642a]/10 to-[#ff0301]/10 rounded-[12px]">
          <div className="p-8">
            <h3 className="font-[Manrope] font-800 text-2xl text-white">AI-Powered Design System</h3>
            <p className="font-[Manrope] font-400 text-neutral-400 mt-3 max-w-md">
              Our component arsenal lets us ship clinic sites in days, not months.
            </p>
          </div>
        </WobbleCard>
        <WobbleCard containerClassName="bg-[#ff642a]/5 rounded-[12px]">
          <div className="p-8">
            <h3 className="font-[Manrope] font-700 text-xl text-white">GHL Native</h3>
            <p className="font-[Manrope] font-400 text-neutral-400 mt-2 text-sm">
              Built for GoHighLevel from day one.
            </p>
          </div>
        </WobbleCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Card backgrounds use subtle brand gradient tints: `from-[#ff642a]/10 to-[#ff0301]/10`
- Apply `rounded-[12px]` to wobble card containers for design system consistency
- Manrope 800 for primary card titles, 700 for secondary, 400 for descriptions
- Wobble intensity can be tuned; keep it subtle for professional contexts
- Fully GHL compatible as wobble uses CSS transforms with no scroll hijacking

## Performance Notes
- Wobble uses framer-motion spring physics, lightweight per-frame calculation
- Mouse tracking uses passive event listeners for smooth performance
- Transform-only animation is GPU-composited, no layout recalculation
- Works smoothly with 6-9 cards in a grid layout
- Wobble resets smoothly on mouse leave with spring damping
