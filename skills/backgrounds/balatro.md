---
name: balatro
source: ReactBits
source_url: https://reactbits.dev/backgrounds/balatro
category: backgrounds
tags: background, psychedelic, stripes, warp, retro, game, dramatic
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Balatro

> A psychedelic warped stripe background inspired by the card game Balatro, creating hypnotic distorted color bands that pulse and shift. Best for bold hero sections and experimental landing pages.

## When to Use

- Hero backgrounds on experimental or creative portfolio pages
- Game-themed or entertainment product landing pages
- Bold launch pages that need to grab attention immediately
- Background for countdown timers or event reveal sections
- Creative agency portfolio hero sections

## When NOT to Use

- Corporate or medical/clinic client sites (too chaotic for professional tone)
- Behind any dense text content (readability will be destroyed)
- E-commerce product pages (distracts from the product)
- Accessibility-critical pages (motion and color intensity are extreme)

## Pairs Well With

- `blur-text` - Bold headline over the warped stripes creates an intense focal point
- `gradient-text` - Gradient text that echoes the stripe colors ties the composition together
- `animated-content` - Staggered fade-in of content elements over the chaotic background
- `count-up` - Animated numbers over Balatro for game/stats-themed sections

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#ff0000","#0000ff","#00ff00"] | Array of stripe colors |
| speed | number | 1.0 | Animation speed multiplier |
| warpIntensity | number | 1.0 | How much the stripes distort (0-2) |
| stripeWidth | number | 20 | Width of each stripe band in pixels |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Balatro-TS-TW
```

## Usage Example

```jsx
import Balatro from '@/components/ui/Balatro';
import BlurText from '@/components/ui/BlurText';

function CreativeHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Balatro
          colors={['#ff642a', '#ff0301', '#1a0a2e', '#0a0a0a']}
          speed={0.6}
          warpIntensity={1.2}
          stripeWidth={25}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Break the Mold."
          delay={150}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-xl mx-auto font-[Manrope]">
          Creative builds for brands that refuse to blend in.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework stripe palette: `['#ff642a', '#ff0301', '#1a0a2e', '#0a0a0a']` to blend brand gradient into dark base
- Keep `warpIntensity` at 0.8-1.2 for Lyfework builds. Above 1.5 becomes nauseating.
- Reduce `speed` to 0.4-0.6 for a more premium, less chaotic feel
- Always layer a `bg-black/40` overlay between Balatro and text content for readability
- For GHL: embed in a full-width custom HTML block. Test on GHL preview since the canvas can clip unexpectedly.
- Only use for internal Lyfework brand pages or creative client builds, never for medical/professional clients

## Performance Notes

- Uses canvas/WebGL rendering which can be GPU-intensive
- Not recommended for mobile devices, consider a static fallback gradient
- Set `speed` to 0 on `prefers-reduced-motion` to show a static stripe pattern
- Can cause frame drops on older hardware when combined with other animated components
- Lazy-load the component so it only initializes when scrolled into view
