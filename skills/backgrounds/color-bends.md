---
name: color-bends
source: ReactBits
source_url: https://reactbits.dev/backgrounds/color-bends
category: backgrounds
tags: background, color, bends, gradient, curved, bands, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ColorBends

> Bent and curved color gradient bands that create smooth, flowing color transitions across the background. Ideal for ambient section dividers and mid-page visual breaks.

## When to Use

- Section dividers between content blocks on long-scroll pages
- Behind pricing or feature comparison sections to add depth
- Portfolio section backgrounds to differentiate project showcases
- Ambient backgrounds for testimonial or quote sections
- Mid-page visual breaks on SaaS landing pages

## When NOT to Use

- As a primary hero background (too subtle for a main focal point)
- Behind dense data tables or form-heavy sections
- When the page already has many gradient elements (visual clutter)
- Light-themed pages where the color bends may lack contrast

## Pairs Well With

- `split-text` - Text reveal animation over the flowing color bends adds polish
- `spotlight-card` - Spotlight cards over color bends create a layered depth effect
- `animated-content` - Content fading in over the bends feels natural and fluid
- `gradient-text` - Match gradient text colors to the bend palette for cohesion

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#6366f1","#8b5cf6","#d946ef"] | Array of colors for the bent gradient bands |
| bendAmount | number | 50 | How much the bands curve (0-100) |
| speed | number | 0.5 | Animation speed of the flowing motion |
| direction | string | "horizontal" | Direction of the bends: "horizontal" or "vertical" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ColorBends-TS-TW
```

## Usage Example

```jsx
import ColorBends from '@/components/ui/ColorBends';
import AnimatedContent from '@/components/ui/AnimatedContent';

function PricingSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0 opacity-40">
        <ColorBends
          colors={['#ff642a', '#ff0301', '#1a0a2e']}
          bendAmount={60}
          speed={0.3}
          direction="horizontal"
        />
      </div>

      <div className="relative z-10 max-w-6xl mx-auto px-8">
        <AnimatedContent direction="up" delay={200}>
          <h2 className="text-4xl font-bold text-white text-center font-[Manrope]">
            Simple, Transparent Pricing
          </h2>
          <p className="mt-4 text-gray-400 text-center max-w-2xl mx-auto">
            No hidden fees. No surprises. Just results.
          </p>
        </AnimatedContent>
        {/* Pricing cards here */}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework palette: `['#ff642a', '#ff0301', '#1a0a2e']` for brand-aligned bends
- Keep opacity at 30-50% (`opacity-30` to `opacity-50`) so bends stay ambient, not dominant
- `bendAmount` of 40-70 works best. Below 30 looks too flat, above 80 gets chaotic.
- For client clinic sites, use softer brand-adjacent colors at low opacity
- GHL: wrap in a full-width HTML section with `overflow: hidden` to prevent color bleed
- Pair with Manrope headings and the standard `rounded-2xl` card radius for visual consistency

## Performance Notes

- Pure CSS gradient animation, very lightweight
- No canvas or WebGL dependency, performs well on all devices
- Multiple overlapping bends increase paint complexity, limit to 3-4 colors
- Safe for mobile and low-powered devices
- SSR-compatible, renders static gradient then animates on hydration
