---
name: star-border
source: ReactBits
source_url: https://reactbits.dev/animations/star-border
category: animations
tags: border, animated, glow, rotating, star, accent, button, card
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# StarBorder

> An animated border with a glowing dot that travels around the element's perimeter. Creates a "scanning" or "loading" effect on any element's border. Pure CSS.

## When to Use

- CTA buttons that need extra attention
- Featured or "recommended" cards in a pricing grid
- Input fields or containers during loading/processing states
- Badges or tags that need to feel alive
- Any element where a static border should feel dynamic

## When NOT to Use

- Every element on the page (loses impact immediately)
- Dense grids where many borders would animate at once
- Elements with rounded corners less than 8px (border animation gets choppy)

## Pairs Well With

- `glow-card` - StarBorder on the featured card, regular cards without
- `spotlight-card` - StarBorder on the CTA inside a spotlight card
- `magnet` - Magnetic CTA button with a traveling border animation
- `click-spark` - Border animates + spark on click for maximum CTA impact

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element to wrap |
| color | string | "#ff642a" | Border glow color |
| speed | number | 3 | Animation loop duration in seconds |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/StarBorder-TS-TW
```

## Usage Example

```jsx
import StarBorder from '@/components/ui/StarBorder';

function FeaturedCTA() {
  return (
    <StarBorder color="#ff642a" speed={4}>
      <button className="px-10 py-5 rounded-xl bg-black/50 text-white font-bold text-lg backdrop-blur-sm">
        Book Your Install
      </button>
    </StarBorder>
  );
}
```

## Lyfework Customization Notes

- Color: `#ff642a` for Lyfework. Client accent color for client builds.
- `speed` of 3-5 seconds for a calm orbit. Below 2s feels frantic.
- Use on ONE CTA or ONE featured card per section. Not multiple.
- Pairs well with transparent/glass button backgrounds
- Works in GHL (pure CSS with conic-gradient animation)

## Performance Notes

- Pure CSS, zero JavaScript
- Uses `conic-gradient` and CSS animation
- Negligible performance cost
- Works on all modern browsers
