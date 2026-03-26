---
name: electric-border
source: ReactBits
source_url: https://reactbits.dev/animations/electric-border
category: animations
tags: border, electric, energy, animated, card, wrapper, neon
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ElectricBorder

> An animated crackling electric border effect that wraps any element, perfect for highlighting premium cards, CTAs, or featured content with high-energy visual emphasis.

## When to Use

- Featured pricing tier or "most popular" plan card to draw the eye
- CTA buttons that need maximum visual urgency
- Contest or limited-time offer cards where energy communicates scarcity
- Hero section feature cards on tech or gaming-oriented sites
- Wrapping testimonial cards from high-profile clients

## When NOT to Use

- Calm, wellness, or medical brand pages where electric energy conflicts with the tone
- Multiple elements on the same page (one electric border is impactful, five is chaos)
- Small elements like tags or badges where the effect is too busy at small scale
- Print-oriented or minimal designs where subtlety is the goal

## Pairs Well With

- `spotlight-card` - Electric border on the outside, spotlight glow on the inside
- `gradient-text` - Brand gradient headline inside an electric-bordered card
- `animated-content` - Scroll-reveal the electric card for maximum impact on entry
- `click-spark` - Electric border + spark on click creates a full energy theme

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to wrap with the electric border |
| color | string | "#ff642a" | Primary color of the electric arcs |
| secondaryColor | string | "#ff0301" | Secondary arc color for variation |
| intensity | number | 0.7 | Arc brightness and density (0-1) |
| speed | number | 1.5 | Animation cycle speed in seconds |
| borderRadius | number | 12 | Border radius in pixels |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ElectricBorder-TS-TW
```

## Usage Example

```jsx
import ElectricBorder from '@/components/ui/ElectricBorder';

function FeaturedPlan() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-8 font-[Manrope]">
      <div className="max-w-md mx-auto">
        <ElectricBorder
          color="#ff642a"
          secondaryColor="#ff0301"
          intensity={0.6}
          borderRadius={16}
        >
          <div className="lyf-glass p-10 rounded-[16px] text-center">
            <span className="text-sm font-semibold uppercase tracking-wider text-[#ff642a]">
              Most Popular
            </span>
            <h3 className="mt-4 text-3xl font-bold text-white">Growth Plan</h3>
            <p className="mt-2 text-gray-400">Everything you need to scale.</p>
            <p className="mt-6 text-5xl font-bold text-white">
              $149<span className="text-lg text-gray-500">/mo</span>
            </p>
            <button className="mt-8 w-full py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
              Get Started
            </button>
          </div>
        </ElectricBorder>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default `color="#ff642a"` and `secondaryColor="#ff0301"` matches the Lyfework brand gradient perfectly.
- Use `borderRadius={16}` for feature cards, `borderRadius={12}` for standard cards, `borderRadius={8}` for buttons.
- Lower `intensity` to 0.4-0.5 for professional/clinic sites; keep 0.7+ for SaaS and gaming.
- The inner card should use `lyf-glass` with matching `rounded-[16px]` so the glass effect fills the electric frame.
- On `#0a0a0a` backgrounds the electric arcs pop without additional contrast adjustments.
- GHL compatibility: the SVG-based arcs render fine in iframes but test the animation loop on GHL mobile preview.

## Performance Notes

- Built with CSS animations and SVG filters -- no JS animation loop
- Uses `filter: blur()` for the glow which triggers GPU compositing
- Keep to 1-2 instances per page; each creates its own compositing layer
- Bundle size: ~3KB (SVG paths + CSS keyframes)
- On low-power mobile devices, the blur filter can cause frame drops; consider reducing intensity
