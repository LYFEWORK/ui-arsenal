---
name: reflective-card
source: ReactBits
source_url: https://reactbits.dev/components/reflective-card
category: components
tags: card, reflective, mirror, shine, premium, hover
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ReflectiveCard

> A card with a reflective, mirror-like surface effect that responds to mouse movement. A diagonal light streak sweeps across the card face on hover, simulating the look of polished glass or holographic foil. Pure CSS with minimal JS.

## When to Use

- Premium pricing or membership cards that need a luxury feel
- VIP or exclusive offer sections where cards must feel special
- Product cards for high-end or luxury brands
- Portfolio highlight cards that need to stand out from a grid
- Any card where a holographic or premium material feel adds value

## When NOT to Use

- Standard content cards where the reflective effect feels excessive
- Light backgrounds where the shine effect is barely visible
- Dense grids with many cards (too many reflections creates visual chaos)
- Accessible designs where motion effects should be minimized

## Pairs Well With

- `gradient-text` - Gradient text inside a reflective card for double luxury
- `border-glow` - Glowing border + reflective surface for maximum premium feel
- `animated-content` - Scroll-reveal reflective cards into view
- `spotlight-card` - Combine spotlight tracking with the reflective shine

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| shineColor | string | "rgba(255,255,255,0.15)" | Color of the reflective shine |
| shineWidth | number | 200 | Width of the shine streak in px |
| speed | number | 0.6 | Shine animation speed (seconds) |
| borderRadius | string | "12px" | Border radius of the card |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ReflectiveCard-TS-TW
```

## Usage Example

```jsx
import ReflectiveCard from '@/components/ui/ReflectiveCard';

function PremiumOfferSection() {
  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="max-w-lg mx-auto">
        <ReflectiveCard
          shineColor="rgba(255,100,42,0.1)"
          borderRadius="16px"
          className="p-10 lyf-glass text-center"
        >
          <span className="text-xs font-bold uppercase tracking-widest text-[#ff642a]">
            Limited Offer
          </span>
          <h2 className="mt-4 text-3xl font-extrabold text-white font-[Manrope]">
            Founding Member Access
          </h2>
          <p className="mt-3 text-gray-400">
            Lock in our lowest rate forever. Full CRM, AI automation, and dedicated support.
          </p>
          <p className="mt-6 text-5xl font-extrabold text-white">
            $497<span className="text-lg text-gray-500 font-normal">/mo</span>
          </p>
          <a
            href="/book"
            className="inline-block mt-8 px-8 py-4 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold rounded-lg hover:opacity-90 transition"
          >
            Claim Your Spot
          </a>
        </ReflectiveCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Shine color: `rgba(255,100,42,0.1)` for a warm, brand-tinted reflection
- Card background: `lyf-glass` with slightly higher opacity (0.06) for a solid feel
- Border radius: `16px` for premium standalone cards, `12px` for grid cards
- Font: `Manrope` 800 for headline, 400 for description
- The reflective streak follows mouse position via CSS `background-position` + JS tracking
- GHL compatible -- pure CSS shine with minimal JS for mouse tracking

## Performance Notes

- Reflective shine uses CSS `linear-gradient` positioned via `background-position`
- Mouse tracking uses `requestAnimationFrame` for smooth 60fps updates
- No animation library needed; CSS transitions handle the shine movement
- `will-change: background-position` hints the browser to optimize repaints
- Degrades gracefully on mobile (no hover, static card appearance)
