---
name: pixel-card
source: ReactBits
source_url: https://reactbits.dev/components/pixel-card
category: components
tags: card, pixel, hover, interactive, glitch, retro, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# PixelCard

> A card that pixelates or dissolves into pixel fragments on hover. Creates a digital glitch aesthetic that feels tech-forward and edgy.

## When to Use

- Tech or SaaS product cards where you want a digital/hacker aesthetic
- Portfolio pieces where the hover transition should feel unexpected
- Feature cards on dark-themed sites that need more edge than SpotlightCard
- "Before/after" or reveal-style card interactions
- Client builds in gaming, crypto, AI, or developer tool verticals

## When NOT to Use

- Clean/minimal brand aesthetics (too busy for elegant designs)
- Medical, legal, or conservative verticals
- Cards with dense text content (pixelation makes text unreadable during transition)
- More than 4-6 cards on screen (effect loses impact)

## Pairs Well With

- `animated-content` - Scroll reveal, then pixel effect activates on hover
- `gradient-text` - Gradient title inside a pixel card
- `click-spark` - Spark on click after pixel hover
- `particles` - Particle background + pixel cards for full tech aesthetic

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| gap | number | 5 | Gap between pixels |
| speed | number | 50 | Pixel animation speed |
| colors | string[] | ["#ff642a"] | Pixel fill colors |
| noFocus | boolean | false | Disable focus outline |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PixelCard-TS-TW
```

## Usage Example

```jsx
import PixelCard from '@/components/ui/PixelCard';

function TechFeatures() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
      <PixelCard gap={6} speed={40} colors={['#ff642a', '#ff0301']}>
        <div className="p-8 text-center">
          <h3 className="text-xl font-bold text-white">AI Engine</h3>
          <p className="mt-3 text-sm text-gray-400">Automated workflows that think ahead.</p>
        </div>
      </PixelCard>
    </div>
  );
}
```

## Lyfework Customization Notes

- Pixel colors: `['#ff642a', '#ff0301']` for Lyfework brand
- `gap` of 4-6 looks clean. Below 3 gets too dense.
- Best on dark backgrounds (#0a0a0a) where pixel colors pop
- Reserve for tech-forward clients. Not appropriate for wellness or medical verticals.
- Works in GHL since it uses Canvas API

## Performance Notes

- Uses HTML5 Canvas for pixel rendering
- Animation only runs on hover (no idle cost)
- Lightweight, no external dependencies
