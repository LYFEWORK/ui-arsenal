---
name: shift-card
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/shift-card
category: components
tags: card, shift, hover, reveal, animated, transition
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ShiftCard

> Card that shifts and reveals additional detail content on hover with smooth transform animation.

## When to Use
- Feature cards revealing detailed specs on hover
- Portfolio cards shifting to show project details
- Team member cards revealing bios and contact info
- Product cards with hover-reveal pricing or CTAs
- Any card needing layered content with hover interaction

## When NOT to Use
- Mobile-first designs where hover is unavailable (provide fallback)
- Cards where all content must be immediately visible
- Accessibility-critical contexts without keyboard alternatives
- Dense card grids where shift animation causes layout issues

## Pairs Well With
- `animated-content` - Staggered entrance of shift card grid
- `gradient-text` - Gradient titles on shift cards
- `shimmer-button` - Shimmer CTA revealed on card shift
- `spotlight-card` - Spotlight effect combined with shift reveal

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| front | ReactNode | - | Default visible content |
| back | ReactNode | - | Content revealed on shift |
| direction | 'up' \| 'down' \| 'left' \| 'right' | 'up' | Shift direction |
| distance | number | 20 | Shift distance in pixels |
| duration | number | 0.3 | Transition duration in seconds |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/shift-card"
```

## Usage Example
```jsx
import { ShiftCard } from "@/components/ui/shift-card";

export function TeamGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-5xl mx-auto">
        <ShiftCard
          direction="up"
          distance={16}
          className="lyf-glass rounded-[12px] overflow-hidden"
          front={
            <div className="p-6">
              <h3 className="font-manrope font-700 text-xl text-white">Dr. Alex Rivera</h3>
              <p className="font-manrope font-400 text-white/60 mt-1">Lead Practitioner</p>
            </div>
          }
          back={
            <div className="px-6 pb-6">
              <p className="font-manrope font-400 text-white/50 text-sm">
                15+ years in integrative medicine. Harvard Medical School graduate.
              </p>
              <button className="mt-3 text-[#ff642a] font-manrope font-700 text-sm">
                View Profile →
              </button>
            </div>
          }
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Card container: lyf-glass, 12px radius, border-white/10 on #0a0a0a
- Front content: Manrope 700 name, 400 role in white/60
- Back content: Manrope 400 bio in white/50, brand orange link
- Use direction="up" to shift card content upward revealing details
- GHL compatible for team and service card sections

## Performance Notes
- Framer Motion transform animation is GPU-accelerated
- Only opacity and transform are animated (no layout recalculation)
- Back content is rendered but hidden via overflow: hidden
- Hover detection uses CSS :hover (no JS event listeners per frame)
- Smooth 60fps transitions on all modern devices
