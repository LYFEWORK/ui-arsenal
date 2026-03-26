---
name: sticker-peel
source: ReactBits
source_url: https://reactbits.dev/animations/sticker-peel
category: animations
tags: sticker, peel, reveal, hover, playful, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# StickerPeel

> A sticker peel-off reveal animation that lifts a cover element like peeling a sticker, revealing content underneath on hover or click. Playful, memorable, and great for reveals.

## When to Use

- Pricing reveals where the price peels open on hover ("peel to see the price")
- Before/after showcases where hovering peels away the "before" to show "after"
- Coupon or discount code reveals on promotional landing pages
- Team member cards where the sticker peels to show the bio or fun fact
- Easter eggs or hidden content that rewards curious visitors

## When NOT to Use

- Critical content that must always be visible (peeling hides information)
- Dense data layouts where interactive reveals slow down scanning
- Mobile-first UX where peel gestures don't translate well from hover
- Accessibility-sensitive pages where hidden-by-default content creates issues

## Pairs Well With

- `tilted-card` - Tilt the card container while the sticker peels for a physical-object feel
- `glare-hover` - Glare on the sticker surface before it peels adds a glossy print quality
- `animated-content` - Scroll-reveal the sticker card, then let users peel on hover
- `click-spark` - Spark effect when the peel completes for a satisfying micro-interaction

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content revealed after peel |
| stickerContent | ReactNode | required | Content shown on the sticker surface |
| trigger | "hover" \| "click" | "hover" | What triggers the peel animation |
| peelDirection | "top-right" \| "top-left" \| "bottom-right" \| "bottom-left" | "top-right" | Corner from which the peel starts |
| peelAmount | number | 0.7 | How far the sticker peels (0-1) |
| duration | number | 0.6 | Peel animation duration in seconds |
| shadow | boolean | true | Show shadow under the peeling sticker |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/StickerPeel-TS-TW
```

## Usage Example

```jsx
import StickerPeel from '@/components/ui/StickerPeel';

function PricingReveal() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-8 font-[Manrope]">
      <h2 className="text-3xl font-bold text-white text-center mb-16">
        Pricing
      </h2>
      <div className="max-w-sm mx-auto">
        <StickerPeel
          trigger="hover"
          peelDirection="top-right"
          peelAmount={0.65}
          duration={0.5}
          stickerContent={
            <div className="lyf-glass p-10 rounded-[12px] text-center h-full flex items-center justify-center">
              <p className="text-xl font-bold text-white">
                Hover to reveal pricing
              </p>
            </div>
          }
        >
          <div className="bg-gradient-to-br from-[#ff642a] to-[#ff0301] p-10 rounded-[12px] text-center">
            <p className="text-sm uppercase tracking-wider text-white/80">
              Starting at
            </p>
            <p className="text-5xl font-bold text-white mt-2">$2,500</p>
            <p className="text-white/70 mt-2">per project</p>
            <button className="mt-6 px-8 py-3 rounded-[8px] bg-white text-[#ff642a] font-bold">
              Get Quote
            </button>
          </div>
        </StickerPeel>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- The sticker surface should use `lyf-glass` styling; the revealed content uses the brand gradient `from-[#ff642a] to-[#ff0301]`.
- Keep `peelAmount` at 0.6-0.75 so some of the sticker remains visible as a visual cue.
- Use `rounded-[12px]` on both the sticker and revealed content for consistent card radius.
- The `shadow` prop adds a realistic drop shadow under the peeling corner; keep enabled on `#0a0a0a` for depth.
- GHL embeds: hover events work inside iframes, but test on GHL mobile preview where hover converts to tap.
- Manrope bold on the sticker text ensures readability at the standard weight hierarchy.

## Performance Notes

- framer-motion handles the peel transform with `rotateX`/`rotateY` and `perspective`
- Shadow is a CSS `box-shadow` that animates with the peel -- GPU composited
- Only 2 DOM layers: sticker surface and revealed content, very lightweight
- Bundle size: ~2KB on top of framer-motion
- The peel uses `transform-origin` set to the chosen corner for natural fold physics
