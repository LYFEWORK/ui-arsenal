---
name: background-gradient
source: Aceternity UI
source_url: https://ui.aceternity.com/components/background-gradient
category: backgrounds
tags: gradient, background, mesh, animated, subtle, ambient
dependencies: none
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# BackgroundGradient

> Animated mesh gradient background with smooth color transitions, providing ambient visual interest behind content.

## When to Use
- Card or container backgrounds with premium gradient feel
- Hero section backdrops with subtle color movement
- Pricing card highlights with gradient border effect
- CTA section backgrounds with ambient warmth
- Any container needing elevated visual depth

## When NOT to Use
- As a full-page background when content readability is priority
- On very small elements where the gradient is imperceptible
- When the page already has heavy visual effects competing

## Pairs Well With
- `spotlight-card` - Layer gradient background under spotlight cards
- `gradient-text` - Match gradient text colors with background gradient
- `animated-content` - Content fades in over the gradient background
- `blur-text` - Text animation on top of gradient backdrop

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the gradient |
| className | string | - | Classes for the gradient container |
| containerClassName | string | - | Classes for the outer wrapper |
| animate | boolean | true | Whether the gradient animates |

## Installation
```bash
npx aceternity-ui@latest add background-gradient
```

## Usage Example
```jsx
import { BackgroundGradient } from "@/components/ui/background-gradient";

export function PremiumCard() {
  return (
    <section className="bg-[#0a0a0a] py-24 flex justify-center px-6">
      <BackgroundGradient className="rounded-[12px] max-w-sm p-8 bg-[#0a0a0a]">
        <h3 className="font-[Manrope] font-800 text-2xl text-white">Pro Plan</h3>
        <p className="font-[Manrope] font-400 text-neutral-400 mt-3">
          Full-service web design with AI integration and GHL automation.
        </p>
        <div className="mt-6">
          <span className="font-[Manrope] font-800 text-4xl text-white">$497</span>
          <span className="text-neutral-500 font-[Manrope] font-400">/month</span>
        </div>
        <button className="mt-8 w-full bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 py-3 rounded-[8px]">
          Get Started
        </button>
      </BackgroundGradient>
    </section>
  );
}
```

## Lyfework Customization Notes
- Inner card uses `bg-[#0a0a0a]` with gradient showing as animated border glow
- Apply `rounded-[12px]` for consistent card radius across design system
- Gradient colors can be customized to include brand `#ff642a` and `#ff0301`
- Manrope 800 for pricing/titles, 700 for CTA, 400 for descriptions
- Zero dependencies; perfect for GHL embeds with no build step needed

## Performance Notes
- CSS-only gradient animation using `@keyframes` and `background-position`
- Zero JavaScript overhead; animation runs entirely on the GPU
- Single DOM element for the gradient wrapper, minimal footprint
- Animation uses `will-change: background-position` for compositing optimization
- Safe to use on multiple cards simultaneously without performance issues
