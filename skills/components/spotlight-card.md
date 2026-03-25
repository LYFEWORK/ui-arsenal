---
name: spotlight-card
source: ReactBits
source_url: https://reactbits.dev/components/spotlight-card
category: components
tags: card, spotlight, hover, glow, mouse-tracking, feature
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# SpotlightCard

> A card with a radial light effect that follows the mouse cursor. Creates a spotlight glow that moves across the card surface on hover. Pure CSS, no animation library needed.

## When to Use

- Feature grids where each card highlights a capability or benefit
- Pricing tables where cards need visual distinction
- Any dark-background card layout that needs ambient interactivity
- Dashboard or settings panels in web apps
- "Why us" or comparison sections

## When NOT to Use

- Light/white background layouts (spotlight effect needs dark to shine)
- Cards with busy backgrounds or images (spotlight gets lost)
- Mobile-only designs (hover doesn't exist, effect is wasted)
- Single card layouts (effect is best appreciated across a grid)

## Pairs Well With

- `animated-content` - Scroll reveal the cards, then spotlight activates on hover
- `gradient-text` - Gradient heading inside a spotlight card for double impact
- `count-up` - Animated numbers inside spotlight cards for stats sections
- `tilted-card` - Use TiltedCard for image cards, SpotlightCard for text/icon cards in the same build

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| spotlightColor | string | "rgba(255,100,42,0.15)" | Color of the spotlight glow |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/SpotlightCard-TS-TW
```

## Usage Example

```jsx
import SpotlightCard from '@/components/ui/SpotlightCard';
import AnimatedContent from '@/components/ui/AnimatedContent';

function WhyUsSection() {
  const reasons = [
    { icon: '⚡', title: 'Fast Implementation', desc: '30-day install. Not 6 months.' },
    { icon: '🔧', title: 'Built to Scale', desc: 'Infrastructure that grows with you.' },
    { icon: '🤖', title: 'AI-Native', desc: 'Automation built in from day one.' },
    { icon: '📊', title: 'Full Visibility', desc: 'Every metric. One dashboard.' },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        {reasons.map((item, i) => (
          <AnimatedContent key={i} direction="up" delay={i * 0.1}>
            <SpotlightCard
              spotlightColor="rgba(255,100,42,0.12)"
              className="p-8 rounded-2xl h-full"
            >
              <span className="text-3xl">{item.icon}</span>
              <h3 className="mt-4 text-lg font-bold text-white">{item.title}</h3>
              <p className="mt-2 text-sm text-gray-400">{item.desc}</p>
            </SpotlightCard>
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default spotlight color for Lyfework: `rgba(255,100,42,0.12)` (brand orange at low opacity)
- For client builds, match the spotlight color to their brand accent at 10-15% opacity
- Card background should be `rgba(255,255,255,0.03)` or `rgba(255,255,255,0.05)` for the glass effect
- Add `border: 1px solid rgba(255,255,255,0.06)` for the Lyfework glass border standard
- Works perfectly in GHL since it's pure CSS with minimal JS for mouse tracking
- Pair with the `lyf-glass` class for consistent Lyfework card styling

## Performance Notes

- Near-zero performance cost (CSS radial-gradient + JS mouse position)
- No animation library dependency
- Mouse tracking uses `requestAnimationFrame` internally
- Works on all modern browsers
- Degrades gracefully on mobile (no spotlight, just the card)
