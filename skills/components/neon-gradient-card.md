---
name: neon-gradient-card
source: Magic UI
source_url: https://magicui.design/docs/components/neon-gradient-card
category: components
tags: card, neon, gradient, glow, border
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# NeonGradientCard

> Card with an animated neon gradient border glow that shifts colors continuously.

## When to Use
- Featured or "most popular" pricing cards
- Highlight cards that need to stand out from a grid
- Call-to-action sections with premium visual treatment
- Testimonial spotlight cards
- New feature announcement cards

## When NOT to Use
- When all cards in a grid should look equal (use magic-card instead)
- Light-themed designs where neon glow looks out of place
- Minimalist designs that avoid animated borders
- Dense content layouts where the glow distracts from readability

## Pairs Well With
- `gradient-text` - Gradient heading inside the neon card
- `animated-content` - Fade in the neon card on scroll
- `shimmer-button` - Shimmer CTA inside the featured card
- `particles` - Particle background behind the card section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| className | string | "" | Additional CSS classes |
| borderSize | number | 5 | Width of the neon border in pixels |
| borderRadius | number | 20 | Border radius of the card |
| neonColors | object | {firstColor: "#ff00aa", secondColor: "#00FFF1"} | Start and end gradient colors |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/neon-gradient-card"
```

## Usage Example
```jsx
import { NeonGradientCard } from "@/components/magicui/neon-gradient-card";

export function FeaturedPlan() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <div className="mx-auto max-w-sm">
        <NeonGradientCard
          borderRadius={12}
          neonColors={{ firstColor: "#ff642a", secondColor: "#ff0301" }}
          className="p-8 text-center"
        >
          <span className="font-manrope font-700 text-sm uppercase tracking-wider bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Most Popular
          </span>
          <h3 className="font-manrope font-800 text-3xl text-white mt-4 mb-2">Pro Plan</h3>
          <p className="font-manrope font-400 text-white/60 mb-6">Everything your clinic needs to grow.</p>
          <p className="font-manrope font-800 text-5xl text-white mb-8">
            $99<span className="text-lg font-400 text-white/40">/mo</span>
          </p>
          <button className="w-full bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 py-3 rounded-[8px]">
            Start free trial
          </button>
        </NeonGradientCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `neonColors` to `{ firstColor: "#ff642a", secondColor: "#ff0301" }` for brand gradient glow
- Use `borderRadius={12}` to match the 12px card convention
- Background inside the card should remain `#0a0a0a` or dark for contrast
- Use Manrope font-800 for pricing, font-700 for labels, font-400 for descriptions
- GHL compatible — CSS animation with no JS framework conflicts

## Performance Notes
- Neon glow uses CSS `@keyframes` animation — runs on GPU
- Single card with animated border has negligible performance cost
- Avoid using more than 2-3 neon cards simultaneously to prevent visual overload
- Animation runs continuously — consider `prefers-reduced-motion` media query
- No JavaScript animation loop — purely CSS driven
