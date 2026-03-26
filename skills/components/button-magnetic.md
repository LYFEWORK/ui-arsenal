---
name: button-magnetic
source: Luxe
source_url: https://www.luxeui.com/ui/button-magnetic
category: components
tags: button, magnetic, hover, cursor, interaction, cta
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# ButtonMagnetic

> Button that magnetically attracts toward the cursor on hover, creating an engaging interactive pull effect.

## When to Use
- Hero section CTAs where you want to draw attention and encourage clicks
- Portfolio or agency sites where micro-interactions signal craft quality
- Pricing page action buttons to increase conversion through playful UX
- Any primary action button that benefits from feeling alive and responsive
- Landing pages where cursor engagement increases dwell time

## When NOT to Use
- Form submit buttons where precise click targeting matters
- Mobile-only layouts where hover states are irrelevant
- Dense UI with many adjacent buttons causing magnetic conflicts
- Accessibility-critical flows where unpredictable movement is disorienting

## Pairs Well With
- `shimmer-button` - combine magnetic pull with shimmer for ultimate CTA impact
- `spotlight-card` - magnetic button inside a spotlight card creates cohesive hover experience
- `gradient-text` - pair magnetic button with gradient heading for hero sections
- `aurora` - magnetic buttons floating over aurora background for premium feel

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Button content |
| className | string | — | Additional CSS classes |
| magneticStrength | number | 0.5 | Strength of magnetic pull (0-1) |
| magneticRadius | number | 150 | Pixel radius of magnetic field |
| as | ElementType | "button" | Render as different element |
| onClick | () => void | — | Click handler |
| disabled | boolean | false | Disable magnetic effect and button |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/button-magnetic"
```

## Usage Example
```jsx
import { ButtonMagnetic } from "@/components/ui/button-magnetic";

export function HeroCTA() {
  return (
    <section className="flex items-center justify-center min-h-[60vh] bg-[#0a0a0a]">
      <div className="text-center space-y-6">
        <h1 className="font-manrope font-800 text-5xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Build Your Dream Practice
        </h1>
        <ButtonMagnetic
          className="px-8 py-4 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white"
          magneticStrength={0.4}
        >
          Book a Free Consultation
        </ButtonMagnetic>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `font-manrope font-700` to button text for brand consistency
- Use `rounded-[8px]` for Lyfework button radius standard
- Background should use `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` for primary CTAs
- Reduce `magneticStrength` to 0.3 on pages with multiple magnetic buttons to avoid conflicts
- Works inside GHL funnels — magnetic effect is pure CSS transform, no layout shift
- On `#0a0a0a` dark backgrounds, add subtle white text shadow for depth

## Performance Notes
- Uses CSS transforms only — no layout recalculations triggered
- Magnetic field listener is throttled via requestAnimationFrame
- Event listener auto-cleans on unmount, no memory leak risk
- Minimal JS footprint — only tracking mouse position within radius
- Disable on mobile via media query to avoid unnecessary touch event processing
