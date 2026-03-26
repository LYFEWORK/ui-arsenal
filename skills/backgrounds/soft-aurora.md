---
name: soft-aurora
source: ReactBits
source_url: https://reactbits.dev/backgrounds/soft-aurora
category: backgrounds
tags: background, aurora, soft, gradient, ambient, subtle, hero
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# SoftAurora

> A softer, subtler version of the aurora background with gentler color transitions and reduced motion. The "everyday" aurora that works on any page without overwhelming the content.

## When to Use

- Hero sections on any page type where aurora would be too intense
- SaaS, agency, portfolio, and clinic site backgrounds
- Behind pricing, feature, or testimonial sections for ambient depth
- Full-page backgrounds for professional landing pages
- Anywhere you would use aurora but need 50% less visual intensity

## When NOT to Use

- Pages that need a bold, dramatic statement (use the full Aurora instead)
- Light-themed designs (still built for dark backgrounds)
- Sections that already have enough visual complexity

## Pairs Well With

- `blur-text` - The classic combo, with softer aurora keeping text more readable
- `spotlight-card` - Cards over soft aurora create a polished, premium layout
- `animated-content` - Content fading in over the gentle glow feels natural
- `gradient-text` - Gradient text that echoes the aurora palette for color harmony

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colorStops | string[] | ["#1a1a2e","#4a2060","#1a1a2e"] | Gradient color stops |
| blend | number | 0.3 | Blend intensity (0-1), lower than standard aurora |
| amplitude | number | 0.5 | Wave amplitude, lower for softer motion |
| speed | number | 0.3 | Animation speed, slower for ambient feel |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/SoftAurora-TS-TW
```

## Usage Example

```jsx
import SoftAurora from '@/components/ui/SoftAurora';
import BlurText from '@/components/ui/BlurText';

function ClinicHero() {
  return (
    <section className="relative min-h-[80vh] flex items-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <SoftAurora
          colorStops={['#0a0a0a', '#1a0a2e', '#ff642a15', '#0a0a0a']}
          blend={0.25}
          amplitude={0.4}
          speed={0.25}
        />
      </div>

      <div className="relative z-10 max-w-4xl mx-auto px-8">
        <BlurText
          text="Your Health, Our Priority."
          delay={150}
          animateBy="words"
          className="text-4xl md:text-6xl font-bold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-2xl font-[Manrope]">
          Comprehensive care with a modern, personal approach.
        </p>
        <div className="mt-8 flex gap-4">
          <a
            href="#booking"
            className="px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]"
          >
            Book Appointment
          </a>
          <a
            href="#services"
            className="px-8 py-4 rounded-xl bg-white/10 backdrop-blur-md border border-white/20 text-white font-bold font-[Manrope]"
          >
            Our Services
          </a>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework soft aurora: `['#0a0a0a', '#1a0a2e', '#ff642a15', '#0a0a0a']` (brand at 8% opacity)
- This is the default background recommendation for all clinic and professional client builds
- `blend` of 0.2-0.3 and `amplitude` of 0.3-0.5 keep it ambient without competing with content
- `speed` of 0.2-0.3 is barely perceptible motion, which is the goal
- Pairs with both gradient CTA buttons and `lyf-glass` secondary buttons
- GHL: works the same as standard aurora in GHL custom HTML blocks
- The safest, most versatile animated background in the entire arsenal

## Performance Notes

- Same rendering engine as Aurora but with reduced parameters
- Lower amplitude and speed mean fewer animation frames needed
- Lighter on GPU than the full Aurora component
- Respects `prefers-reduced-motion` and falls back to a static gradient
- SSR-compatible, renders a static gradient and animates on client
- Safe for all devices including older mobile hardware
