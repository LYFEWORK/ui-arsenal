---
name: liquid-button
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/liquid-button
category: components
tags: button, liquid, fluid, morphing, blob, creative
dependencies: framer-motion
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# LiquidButton

> Button with a liquid/fluid morphing animation that makes the button shape organically deform on hover like a living blob.

## When to Use
- Creative agency or studio portfolio landing pages
- Experimental hero sections where the button IS the visual statement
- Art-directed microsites or campaign pages
- Game or entertainment sites with playful, non-corporate aesthetics
- Feature showcases where each interaction should feel unique

## When NOT to Use
- Corporate or healthcare sites where professionalism is paramount
- Forms and functional UI where button shape clarity matters
- Pages with many buttons — liquid effect on multiple buttons is chaotic
- Mobile layouts where the morphing effect is hard to see at small sizes
- Accessibility-focused contexts where shape changes may confuse users

## Pairs Well With
- `aurora` - liquid button floating over aurora background for surreal hero sections
- `particles` - liquid button amid particles for a cosmic, fluid aesthetic
- `gradient-text` - gradient heading with liquid CTA underneath for creative impact
- `cursor-follow` - custom liquid cursor paired with liquid button for full fluid UX

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Button content |
| className | string | — | Additional CSS classes |
| liquidColor | string | — | Primary liquid color |
| intensity | number | 0.5 | Morphing intensity (0-1) |
| speed | number | 1 | Animation speed multiplier |
| onClick | () => void | — | Click handler |
| disabled | boolean | false | Disable liquid effect |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/liquid-button"
```

## Usage Example
```jsx
import { LiquidButton } from "@/components/ui/liquid-button";

export function CreativeHero() {
  return (
    <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <div className="text-center space-y-10">
        <h1 className="font-manrope font-800 text-7xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          We Build Different
        </h1>
        <LiquidButton
          className="px-10 py-5 font-manrope font-700 text-white text-xl"
          liquidColor="#ff642a"
          intensity={0.6}
        >
          See Our Work
        </LiquidButton>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `liquidColor` to `"#ff642a"` for brand orange liquid effect
- Use `font-manrope font-700` for button text within the liquid shape
- Best on `#0a0a0a` backgrounds where the liquid blob edges are most visible
- Reserve for single-use hero CTAs — do not place multiple liquid buttons on one page
- GHL compatibility: works but the SVG filter effect may clip in some iframe configs
- Reduce `intensity` to 0.3 for a more subtle, professional liquid wobble

## Performance Notes
- Uses SVG filters (feTurbulence/feDisplacementMap) — moderate GPU load
- Limit to one liquid button per viewport for optimal performance
- Animation runs continuously on hover — returns to static on mouse leave
- SVG filter rendering can vary across browsers — test in Safari
- Consider using IntersectionObserver to disable animation when off-screen
