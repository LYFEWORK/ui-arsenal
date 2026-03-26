---
name: button-shine
source: Luxe
source_url: https://www.luxeui.com/ui/button-shine
category: components
tags: button, shine, sweep, hover, glossy, cta
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# ButtonShine

> Button with an animated light shine sweep that glides across on hover, creating a polished glass-like effect.

## When to Use
- Primary CTAs on landing pages where visual polish drives conversion
- Pricing cards to highlight the recommended plan button
- Dark-themed sections where the shine effect contrasts beautifully
- SaaS hero sections for "Get Started" or "Try Free" buttons
- Portfolio project cards for "View Project" actions

## When NOT to Use
- Text-only or ghost button contexts where shine looks out of place
- Light backgrounds where the shine effect is barely visible
- Minimalist designs that intentionally avoid decorative effects
- Inline text buttons where the sweep animation is distracting

## Pairs Well With
- `blur-text` - shine button beneath blur-reveal heading creates a polished reveal sequence
- `spotlight-card` - shine button inside spotlight card doubles down on light-based interactions
- `gradient-text` - gradient heading paired with shine CTA for hero consistency
- `tilted-card` - shine button on a tilted card for portfolio project actions

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Button content |
| className | string | — | Additional CSS classes |
| shineColor | string | "rgba(255,255,255,0.3)" | Color of the shine sweep |
| duration | number | 0.6 | Duration of shine animation in seconds |
| variant | "default" \| "outline" | "default" | Button style variant |
| size | "sm" \| "md" \| "lg" | "md" | Button size preset |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/button-shine"
```

## Usage Example
```jsx
import { ButtonShine } from "@/components/ui/button-shine";

export function PricingCTA() {
  return (
    <div className="lyf-glass rounded-[12px] p-8 text-center space-y-4 bg-[#0a0a0a]/80">
      <h3 className="font-manrope font-800 text-2xl text-white">Pro Plan</h3>
      <p className="text-gray-400 font-manrope font-400">Everything you need to scale</p>
      <ButtonShine
        className="w-full rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white py-3"
        shineColor="rgba(255,255,255,0.25)"
      >
        Start Free Trial
      </ButtonShine>
    </div>
  );
}
```

## Lyfework Customization Notes
- Use `shineColor="rgba(255,255,255,0.25)"` on gradient backgrounds for subtlety
- Apply `rounded-[8px]` for Lyfework button radius standard
- On `lyf-glass` cards, the shine effect reinforces the glass aesthetic
- Works in GHL embed — pure CSS animation, no JS runtime needed
- Pair with `font-manrope font-700` for brand-consistent button text
- On `#0a0a0a` backgrounds, the shine sweep is maximally visible

## Performance Notes
- Pure CSS pseudo-element animation — zero JavaScript overhead
- No framer-motion dependency — lightest possible button animation
- Uses `will-change: transform` for GPU-accelerated sweep
- Animation only triggers on hover — no idle CPU usage
- Safe for pages with many shine buttons — no cumulative performance impact
