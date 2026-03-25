---
name: glow-card
source: ReactBits
source_url: https://reactbits.dev/components/glow-card
category: components
tags: card, glow, hover, border, neon, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# GlowCard

> A card with a glowing animated border that pulses or shifts color. The glow follows the card edge, creating a neon-sign effect. Pure CSS.

## When to Use

- Pricing cards where you want to highlight the recommended tier
- Feature cards that need to stand out from a grid
- CTA sections or "featured" content blocks
- Dark-themed layouts where a glowing border creates depth
- Any card that needs to feel premium without heavy animation

## When NOT to Use

- Light backgrounds (glow effect is invisible)
- Dense grids with 6+ cards (every card glowing = visual noise)
- Minimalist designs where the glow feels too flashy

## Pairs Well With

- `animated-content` - Scroll reveal into glowing cards
- `count-up` - Stats inside glow cards for a metrics section
- `blur-text` - Glow card as a callout below a blur-revealing headline
- `spotlight-card` - Mix SpotlightCards and one GlowCard to draw attention to a featured item

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| glowColor | string | "#ff642a" | Primary glow color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GlowCard-TS-TW
```

## Usage Example

```jsx
import GlowCard from '@/components/ui/GlowCard';

function PricingHighlight() {
  return (
    <GlowCard glowColor="#ff642a" className="p-10 rounded-2xl text-center">
      <span className="text-sm font-bold text-orange-400 uppercase tracking-wide">Most Popular</span>
      <h3 className="mt-4 text-3xl font-extrabold text-white">$297/mo</h3>
      <p className="mt-2 text-gray-400">Software Plan</p>
      <button className="mt-8 w-full py-3 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
        Get Started
      </button>
    </GlowCard>
  );
}
```

## Lyfework Customization Notes

- Glow color: `#ff642a` for Lyfework. Match client brand accent for client builds.
- Use ONE GlowCard per section to highlight the key item. Not every card.
- Combine with `lyf-glass` background for the card body
- Works perfectly in GHL (pure CSS animation)

## Performance Notes

- Zero JavaScript, pure CSS animations
- Uses `box-shadow` and `border-image` animations
- Negligible performance cost
