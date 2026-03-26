---
name: silk
source: ReactBits
source_url: https://reactbits.dev/backgrounds/silk
category: backgrounds
tags: background, silk, fabric, smooth, flowing, elegant, luxury
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Silk

> A smooth, silky fabric flowing background that creates an elegant, luxurious sense of draped material. Adds a tactile, premium feel to hero sections and key content areas.

## When to Use

- Luxury brand or high-end product landing pages
- Fashion, beauty, or lifestyle brand hero sections
- Premium service pages (wealth management, concierge, boutique)
- Wedding or event planning site backgrounds
- Behind testimonials from high-profile clients for a premium frame

## When NOT to Use

- Tech or developer-focused pages (silk feels too soft)
- Budget-conscious brand pages where luxury aesthetics send the wrong message
- Behind dense data, tables, or technical content
- Pages with heavy use of geometric or angular design elements (style clash)

## Pairs Well With

- `blur-text` - Text revealing over flowing silk is the definition of luxury
- `gradient-text` - Gradient text in silk tones creates visual harmony
- `animated-content` - Content appearing over the draped fabric feels like an unveiling
- `split-text` - Character-by-character reveal over silk for high-fashion hero sections

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#1a1a2e" | Base color of the silk fabric |
| highlightColor | string | "#ffffff" | Color of the silk highlights/sheen |
| speed | number | 0.3 | Speed of the flowing fabric motion |
| folds | number | 5 | Number of fabric folds/waves |
| sheen | number | 0.3 | Intensity of the silk highlight (0-1) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Silk-TS-TW
```

## Usage Example

```jsx
import Silk from '@/components/ui/Silk';
import BlurText from '@/components/ui/BlurText';

function LuxuryServiceHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <Silk
          color="#0a0a0a"
          highlightColor="#ff642a"
          speed={0.2}
          folds={4}
          sheen={0.2}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Elevated by Design."
          delay={200}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-xl mx-auto font-[Manrope]">
          Premium digital experiences for discerning brands.
        </p>
        <button className="mt-10 px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]">
          Start Your Project
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework silk: `color="#0a0a0a"` with `highlightColor="#ff642a"` for warm brand sheen on dark fabric
- For luxury clients: use deep navy `#0a0a2e` with gold `#d4a574` highlights
- `speed` of 0.15-0.3 feels like real silk in a gentle breeze. Above 0.5 feels like a flag in wind.
- `folds` of 3-5 creates an elegant drape. More than 7 starts looking crumpled.
- `sheen` of 0.15-0.3 is the sweet spot. Above 0.5 the highlight becomes a glare.
- GHL: can be approximated with layered CSS gradients and subtle transform animations
- The silk aesthetic pairs perfectly with thin, elegant Manrope light-weight headings

## Performance Notes

- CSS-based gradient layers with transform animations
- No canvas or WebGL dependency in the base variant
- Canvas variant available for more realistic fabric simulation
- The transform animations are GPU-accelerated, smooth on most devices
- SSR-compatible, renders a static gradient and animates on client
