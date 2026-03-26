---
name: grainient
source: ReactBits
source_url: https://reactbits.dev/backgrounds/grainient
category: backgrounds
tags: background, gradient, grain, noise, texture, ambient, subtle
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Grainient

> A gradient background with a film grain/noise texture overlay, combining smooth color transitions with organic texture. The most versatile "elevated flat background" in the arsenal.

## When to Use

- Hero sections on any page type for a premium, textured feel
- Full-page backgrounds for SaaS, portfolio, and agency sites
- Behind pricing or feature sections to add depth without animation
- Any section where a flat color feels too plain but animation is overkill
- Clinic and professional client sites where subtlety is essential

## When NOT to Use

- Behind high-detail photography (grain texture competes with photo noise)
- Sections where the grain may be mistaken for compression artifacts
- Print-oriented designs where the grain won't translate

## Pairs Well With

- `blur-text` - Blur text over a grainy gradient is an instantly premium combo
- `spotlight-card` - Spotlight cards over grainient create a polished, elevated layout
- `animated-content` - Content fading in over the textured gradient feels natural
- `gradient-text` - Match the gradient text colors to the grainient palette

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#0a0a0a","#1a1a2e"] | Gradient color stops |
| grainIntensity | number | 0.15 | How visible the grain texture is (0-1) |
| grainSize | number | 1 | Scale of the grain particles |
| angle | number | 135 | Gradient angle in degrees |
| animated | boolean | false | Whether the gradient subtly shifts over time |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Grainient-TS-TW
```

## Usage Example

```jsx
import Grainient from '@/components/ui/Grainient';
import BlurText from '@/components/ui/BlurText';

function ClinicHero() {
  return (
    <section className="relative min-h-[80vh] flex items-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Grainient
          colors={['#0a0a0a', '#1a0a1e', '#0a0a0a']}
          grainIntensity={0.12}
          grainSize={1}
          angle={160}
        />
      </div>

      <div className="relative z-10 max-w-4xl mx-auto px-8">
        <BlurText
          text="Modern Care. Timeless Trust."
          delay={150}
          animateBy="words"
          className="text-4xl md:text-6xl font-bold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-2xl font-[Manrope]">
          Experience healthcare redesigned for the way you live.
        </p>
        <a
          href="#booking"
          className="mt-8 inline-block px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]"
        >
          Schedule Your Visit
        </a>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework grainient: `['#0a0a0a', '#1a0a1e', '#0a0a0a']` for a subtle dark-to-purple-to-dark sweep
- For brand-forward pages: `['#0a0a0a', '#ff642a20', '#0a0a0a']` (brand color at 12% opacity)
- `grainIntensity` of 0.08-0.15 is the sweet spot. Above 0.25 looks like a dirty screen.
- This is the safest background for any client build, always looks polished
- GHL: the grain can be applied as a CSS `background-image` using an SVG noise filter
- Use with Manrope font and the standard `rounded-2xl` radius for visual consistency

## Performance Notes

- The grain is typically an SVG filter or CSS noise pattern, extremely lightweight
- No canvas or WebGL dependency
- Static grainient has zero ongoing performance cost
- Animated variant uses subtle CSS transitions, negligible impact
- SSR-compatible, renders the gradient immediately with grain applied on client
