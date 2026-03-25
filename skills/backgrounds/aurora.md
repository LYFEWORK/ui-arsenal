---
name: aurora
source: ReactBits
source_url: https://reactbits.dev/backgrounds/aurora
category: backgrounds
tags: background, aurora, gradient, animated, hero, ambient, webgl
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Aurora

> An animated aurora borealis background effect with flowing, organic gradient colors. Creates an immersive, premium ambient backdrop for hero sections and full-page layouts.

## When to Use

- Hero section backgrounds on landing pages (primary use case)
- Full-page backgrounds for "above the fold" content
- Behind pricing sections or key conversion areas to add visual weight
- Dark-themed pages that need atmospheric depth without being flat
- Event or launch pages that need to feel special

## When NOT to Use

- Behind dense text content (too distracting for reading)
- As a background for every section on a page (overuse kills impact)
- Light-themed designs (Aurora is built for dark backgrounds)
- Pages with heavy image content already (visual competition)
- Mobile-only experiences where battery is a concern

## Pairs Well With

- `blur-text` - The signature combo. Aurora background + BlurText headline = instant premium hero.
- `gradient-text` - Aurora behind gradient text creates color harmony
- `split-text` - GSAP text reveal over aurora for scroll-based hero
- `animated-content` - Fade in CTA buttons and supporting text over aurora

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colorStops | string[] | ["#3A1C71","#D76D77","#FFAF7B"] | Gradient color stops for the aurora |
| blend | number | 0.5 | Blend intensity (0-1) |
| amplitude | number | 1.0 | Wave amplitude of the aurora movement |
| speed | number | 0.5 | Animation speed |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Aurora-TS-TW
```

## Usage Example

```jsx
import Aurora from '@/components/ui/Aurora';
import BlurText from '@/components/ui/BlurText';

function Hero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      {/* Aurora fills the background */}
      <div className="absolute inset-0 z-0">
        <Aurora
          colorStops={['#1a0a2e', '#ff642a', '#ff0301']}
          blend={0.4}
          amplitude={0.8}
          speed={0.4}
        />
      </div>

      {/* Content sits on top */}
      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Infrastructure That Moves."
          delay={150}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white"
        />
        <p className="mt-6 text-xl text-gray-300 max-w-2xl mx-auto">
          We build operating systems for businesses that refuse to stay still.
        </p>
        <button className="mt-10 px-8 py-4 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg">
          Book Your Install
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework aurora colors: `['#1a0a2e', '#ff642a', '#ff0301']` (deep purple into brand gradient)
- For client builds: use their brand colors at reduced saturation. Dark base + 2 accent colors.
- `speed` of 0.3-0.5 feels premium and ambient. Above 0.7 feels restless.
- `amplitude` of 0.6-1.0 is the sweet spot. Below 0.5 looks too static.
- `blend` of 0.3-0.5 keeps it subtle. Above 0.7 becomes overpowering.
- Always add `overflow-hidden` to the aurora container to prevent bleed
- For GHL builds: place in a full-width HTML element. The canvas renders within its container bounds. Test that the GHL section doesn't clip the canvas.
- Add a dark overlay (`bg-black/30`) between aurora and text if text readability is an issue

## Performance Notes

- Uses CSS animations by default (no WebGL in the base version)
- Canvas-based variant available for more complex aurora patterns
- Performant on desktop, test mobile carefully (some older devices struggle)
- Consider reducing amplitude and speed on mobile via media query
- The component respects `prefers-reduced-motion` media query
- SSR compatible (renders a static gradient, animates on client)
