---
name: rainbow-button
source: Magic UI
source_url: https://magicui.design/docs/components/rainbow-button
category: components
tags: button, rainbow, gradient, border, animation
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# RainbowButton

> Button with an animated rainbow gradient border that continuously shifts through spectrum colors.

## When to Use
- Playful or creative landing page CTAs
- "Try it free" buttons on developer/creative tools
- Special promotion or event action buttons
- Portfolio site contact buttons
- Product launch announcement CTAs

## When NOT to Use
- Corporate or medical sites requiring conservative design
- Multiple buttons in close proximity (rainbow fatigue)
- Contexts where brand-specific colors must dominate
- Accessibility-critical interfaces (color-dependent feedback)

## Pairs Well With
- `gradient-text` - Rainbow heading paired with rainbow button
- `sparkles-text` - Sparkle text label above the rainbow CTA
- `confetti` - Trigger confetti on rainbow button click
- `animated-content` - Reveal the button with scroll animation

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Button label content |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/rainbow-button"
```

## Usage Example
```jsx
import { RainbowButton } from "@/components/magicui/rainbow-button";

export function LaunchCTA() {
  return (
    <section className="bg-[#0a0a0a] py-24 text-center">
      <h2 className="font-manrope font-800 text-4xl text-white mb-6">
        Something{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          amazing
        </span>{" "}
        is coming
      </h2>
      <p className="font-manrope font-400 text-white/60 mb-10">
        Be the first to experience our next-gen AI scheduling platform.
      </p>
      <RainbowButton className="font-manrope font-700 px-8 py-4 rounded-[8px] text-lg">
        Join the waitlist
      </RainbowButton>
    </section>
  );
}
```

## Lyfework Customization Notes
- Rainbow effect works best on `#0a0a0a` dark backgrounds
- Apply `rounded-[8px]` for button border-radius convention
- Use Manrope font-700 for button text
- Use sparingly — reserve for special moments, not standard CTAs
- GHL compatible — pure CSS gradient animation, no JS runtime

## Performance Notes
- CSS `@keyframes` with `background-position` animation — GPU friendly
- Gradient uses `background-size: 200%` for smooth scrolling effect
- Single button instance has negligible performance impact
- Animation runs continuously — respect `prefers-reduced-motion`
- No JavaScript event listeners or animation frames required
