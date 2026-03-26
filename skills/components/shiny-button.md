---
name: shiny-button
source: Magic UI
source_url: https://magicui.design/docs/components/shiny-button
category: components
tags: button, shiny, glossy, animated, cta
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# ShinyButton

> Button with a glossy animated shine effect that sweeps across on hover, creating a polished metallic feel.

## When to Use
- Premium CTA buttons for high-end product pages
- "Upgrade" or "Go Pro" buttons in pricing sections
- Hero section primary action buttons
- Portfolio contact buttons with polished aesthetic
- App download or signup buttons

## When NOT to Use
- Flat/minimal design systems that avoid glossy effects
- Multiple shiny buttons in the same section
- When shimmer-button is already being used (similar effect)
- Low-contrast contexts where the shine is invisible

## Pairs Well With
- `gradient-text` - Gradient heading above the shiny CTA
- `neon-gradient-card` - Shiny button inside a neon-bordered card
- `animated-content` - Animate the button into view
- `click-spark` - Spark particles on click for extra polish

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Button label content |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/shiny-button"
```

## Usage Example
```jsx
import { ShinyButton } from "@/components/magicui/shiny-button";

export function UpgradePrompt() {
  return (
    <section className="bg-[#0a0a0a] py-24 text-center">
      <h2 className="font-manrope font-800 text-3xl text-white mb-4">
        Unlock{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          premium features
        </span>
      </h2>
      <p className="font-manrope font-400 text-white/60 mb-10 max-w-md mx-auto">
        Advanced analytics, priority support, and unlimited patient records.
      </p>
      <ShinyButton className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 px-10 py-4 rounded-[8px] text-lg">
        Upgrade to Pro
      </ShinyButton>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` for brand gradient background
- Use `rounded-[8px]` for button border-radius convention
- Manrope font-700 for button text weight
- Shine effect is most visible on gradient or solid-color backgrounds
- GHL compatible — CSS-driven shine with no Web Component dependencies

## Performance Notes
- Hover-triggered animation — no continuous CPU usage
- CSS pseudo-element with `transform` animation — GPU composited
- No JavaScript event loop or animation frame usage
- Shine effect is a single diagonal sweep — lightweight
- Falls back gracefully on touch devices (no hover state)
