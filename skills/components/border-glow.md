---
name: border-glow
source: ReactBits
source_url: https://reactbits.dev/components/border-glow
category: components
tags: border, glow, animated, card, hover, neon, accent
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# BorderGlow

> An animated glowing border effect for cards and containers. A luminous gradient traces the edge of the element, creating a neon-like accent that pulses or follows hover state. Pure CSS animation, no library needed.

## When to Use

- Feature cards or pricing tiers that need a premium "selected" or "popular" state
- CTA containers that need to stand out from surrounding content
- Dashboard panels where active/focused state needs strong visual signaling
- Hero section cards on dark backgrounds where border glow amplifies depth
- Testimonial or case study cards that deserve extra visual weight

## When NOT to Use

- Light/white background layouts where glow washes out
- Dense grids with many items (too many glowing borders creates visual noise)
- Print-oriented or accessibility-first designs where animation is unwanted
- Mobile-heavy layouts where the subtle glow may not register on smaller screens

## Pairs Well With

- `spotlight-card` - Spotlight interior + glowing border for maximum card impact
- `gradient-text` - Glowing border card with a gradient heading inside
- `animated-content` - Scroll-reveal the card, then the border glow activates
- `blur-text` - Blur-in text reveal inside a glow-bordered container

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content inside the bordered container |
| glowColor | string | "#ff642a" | Primary color of the glow effect |
| borderRadius | string | "12px" | Border radius of the container |
| borderWidth | number | 1 | Width of the glowing border in px |
| animated | boolean | true | Whether the glow animates around the border |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/BorderGlow-TS-TW
```

## Usage Example

```jsx
import BorderGlow from '@/components/ui/BorderGlow';
import AnimatedContent from '@/components/ui/AnimatedContent';

function PricingSection() {
  const plans = [
    { name: 'Starter', price: '$497/mo', features: ['5 Automations', 'CRM Setup', 'Email Sequences'] },
    { name: 'Growth', price: '$997/mo', features: ['Unlimited Automations', 'Full CRM', 'AI Chat', 'Pipeline'], popular: true },
    { name: 'Scale', price: '$1,997/mo', features: ['Everything in Growth', 'Dedicated Support', 'Custom Integrations'] },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {plans.map((plan, i) => (
          <AnimatedContent key={i} direction="up" delay={i * 0.15}>
            <BorderGlow
              glowColor={plan.popular ? '#ff642a' : 'rgba(255,255,255,0.1)'}
              animated={plan.popular}
              borderRadius="12px"
              className="p-8 bg-white/[0.03] h-full"
            >
              {plan.popular && (
                <span className="text-xs font-bold uppercase tracking-wider text-[#ff642a]">Most Popular</span>
              )}
              <h3 className="mt-2 text-xl font-bold text-white font-[Manrope]">{plan.name}</h3>
              <p className="mt-1 text-3xl font-extrabold text-white">{plan.price}</p>
              <ul className="mt-6 space-y-3">
                {plan.features.map((f, j) => (
                  <li key={j} className="text-sm text-gray-400 flex items-center gap-2">
                    <span className="text-[#ff642a]">&#10003;</span> {f}
                  </li>
                ))}
              </ul>
            </BorderGlow>
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default glow color: `#ff642a` (Lyfework brand orange) for primary cards, `rgba(255,255,255,0.08)` for secondary
- Use `animated={true}` only on the featured/popular card to draw focus; static glow on others
- Card background should pair with `lyf-glass` class for frosted glass interior
- Border radius: `12px` for cards, `16px` for hero-level panels
- Fully GHL-compatible since it relies only on CSS animations and gradients
- For client builds, swap `glowColor` to match their brand accent

## Performance Notes

- Pure CSS animation using `@keyframes` and `conic-gradient` -- zero JS overhead
- No animation library dependency, works everywhere
- Glow uses pseudo-elements with `filter: blur()` for the soft edge
- Works on all modern browsers including Safari
- Degrades gracefully to a solid border on older browsers
