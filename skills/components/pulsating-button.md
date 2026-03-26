---
name: pulsating-button
source: Magic UI
source_url: https://magicui.design/docs/components/pulsating-button
category: components
tags: button, pulse, glow, cta, animation
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# PulsatingButton

> Button with a continuous pulsing glow ring animation that draws attention to primary actions.

## When to Use
- Primary CTA buttons in hero sections
- "Book now" buttons on clinic landing pages
- Time-sensitive action buttons (limited offer, live event)
- Single most important action on a page
- Sticky bottom bar CTA buttons on mobile

## When NOT to Use
- Secondary or tertiary actions that should not compete for attention
- Multiple buttons in a group (pulsing on all is overwhelming)
- Forms with multiple submit buttons
- Disabled or inactive states

## Pairs Well With
- `gradient-text` - Gradient heading above the pulsating CTA
- `animated-content` - Fade in the button with the hero section
- `aurora` - Aurora background behind the CTA area
- `click-spark` - Add spark effect on click for layered feedback

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Button label content |
| className | string | "" | Additional CSS classes |
| pulseColor | string | "#0096ff" | Color of the pulse ring |
| duration | string | "1.5s" | Pulse animation duration |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/pulsating-button"
```

## Usage Example
```jsx
import { PulsatingButton } from "@/components/magicui/pulsating-button";

export function HeroCTA() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <h1 className="font-manrope font-800 text-5xl text-white mb-6">
        The future of{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          clinic management
        </span>
      </h1>
      <p className="font-manrope font-400 text-white/60 text-lg mb-10 max-w-lg mx-auto">
        Automate scheduling, reduce no-shows, and grow your practice.
      </p>
      <PulsatingButton
        pulseColor="#ff642a"
        className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 px-8 py-4 rounded-[8px] text-lg"
      >
        Get started free
      </PulsatingButton>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `pulseColor="#ff642a"` to match the brand orange
- Apply `rounded-[8px]` for button border-radius convention
- Use Manrope font-700 for button text
- Background gradient `from-[#ff642a] to-[#ff0301]` for the button fill
- GHL compatible — CSS keyframe animation, no Shadow DOM or Web Components

## Performance Notes
- CSS `@keyframes` animation — zero JavaScript overhead
- Pulse uses `box-shadow` animation which is GPU composited
- Single pulsating button per page is ideal — multiple compete for attention
- Respects `prefers-reduced-motion` when implemented with media query
- No layout shift — pulse ring expands beyond the button boundary via pseudo-element
