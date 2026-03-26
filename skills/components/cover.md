---
name: cover
source: Aceternity UI
source_url: https://ui.aceternity.com/components/cover
category: components
tags: cover, beam, reveal, hover, text, highlight, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# Cover

> Text or element wrapper with an animated beam reveal effect on hover, creating a scanning highlight across content.

## When to Use
- Highlighting key words or phrases in hero headings
- Adding interactive emphasis to pricing numbers or stats
- Creating hover-to-reveal effects on important CTAs
- Drawing attention to featured product names or brand terms
- Adding micro-interactions to section headers

## When NOT to Use
- On large blocks of paragraph text where scanning effect is distracting
- When accessibility requires all content to be immediately visible
- For decorative elements that don't benefit from text emphasis

## Pairs Well With
- `gradient-text` - Combine gradient color with beam reveal for double emphasis
- `blur-text` - Use blur entrance followed by cover beam on hover
- `spotlight-card` - Place cover text inside spotlight cards
- `animated-content` - Sequence cover reveals with content animations

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Text or element to apply the beam effect to |
| className | string | - | Additional classes for the cover wrapper |

## Installation
```bash
npx aceternity-ui@latest add cover
```

## Usage Example
```jsx
import { Cover } from "@/components/ui/cover";

export function HeroHeadline() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-6 text-center">
      <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
        Build websites at{" "}
        <Cover className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          warp speed
        </Cover>
      </h1>
      <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6 max-w-2xl mx-auto">
        AI-powered web design for clinics and SaaS companies that need to ship fast.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent` to the covered text
- Use Manrope 800 for headings where Cover is applied
- Beam color can be customized via CSS custom properties to match brand orange
- Works on #0a0a0a backgrounds; beam glow is most visible on dark surfaces
- GHL compatible as it uses standard DOM elements with CSS transforms

## Performance Notes
- Beam animation uses CSS transforms and opacity, fully GPU-accelerated
- Hover-only trigger means zero performance cost when not interacting
- Minimal DOM footprint: single wrapper element with pseudo-elements
- Animation duration is short (300-500ms), no sustained performance impact
- Safe to use multiple Cover instances on a single page
