---
name: prism
source: ReactBits
source_url: https://reactbits.dev/backgrounds/prism
category: backgrounds
tags: background, prism, rainbow, refraction, light, spectrum, premium
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Prism

> A prismatic light refraction effect that splits light into a subtle rainbow spectrum. Creates a premium, glass-like aesthetic with shifting spectral colors.

## When to Use

- Premium product hero sections for a high-end glass/crystal feel
- Design tool or creative software landing pages
- Portfolio hero sections for photographers or designers
- Behind glass-morphism card layouts for a multi-layered light effect
- SaaS pages targeting design-conscious audiences

## When NOT to Use

- Pages with a strict, limited color palette (the spectrum adds unwanted colors)
- Behind heavy text content (the shifting colors affect readability)
- Dark, moody designs where rainbow tones break the atmosphere
- Client sites with conservative brand guidelines

## Pairs Well With

- `blur-text` - Text emerging through the prismatic light feels like a premium reveal
- `spotlight-card` - Cards with glass styling over prism create a layered light effect
- `gradient-text` - Spectral gradient text matches the prismatic background
- `animated-content` - Content appearing through the light refraction

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| angle | number | 45 | Angle of the light refraction in degrees |
| intensity | number | 0.5 | Brightness of the prismatic effect (0-1) |
| spread | number | 60 | How wide the spectrum spreads |
| animated | boolean | true | Whether the refraction shifts over time |
| position | string | "top-right" | Light source position: "top-left", "top-right", "center" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Prism-TS-TW
```

## Usage Example

```jsx
import Prism from '@/components/ui/Prism';
import SpotlightCard from '@/components/ui/SpotlightCard';

function DesignToolHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <Prism
          angle={40}
          intensity={0.25}
          spread={70}
          animated={true}
          position="top-right"
        />
      </div>

      <div className="relative z-10 max-w-5xl mx-auto px-8 text-center">
        <h1 className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]">
          Design Without Limits
        </h1>
        <p className="mt-6 text-lg text-gray-300 max-w-2xl mx-auto font-[Manrope]">
          Tools that bend light to your creative will.
        </p>
        <div className="mt-12 grid grid-cols-1 md:grid-cols-3 gap-6">
          <SpotlightCard className="p-6 rounded-2xl backdrop-blur-md bg-white/5 border border-white/10">
            <h3 className="text-lg font-bold text-white">Create</h3>
            <p className="mt-2 text-gray-400 text-sm">Build from scratch or templates.</p>
          </SpotlightCard>
          {/* More cards */}
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- The prism naturally introduces rainbow colors, use sparingly to avoid clashing with brand orange
- `intensity` of 0.15-0.3 keeps the spectrum subtle. Above 0.5 becomes a rainbow explosion.
- Position the light source opposite to the content gravity for natural composition
- For Lyfework portfolio: the prism effect showcases design sensibility
- GHL: approximate with a `linear-gradient` using spectral color stops and a CSS rotation animation
- Combine with `lyf-glass` card styling for a full light-refraction aesthetic

## Performance Notes

- CSS gradient animation, very lightweight
- No canvas or WebGL dependency
- The shifting animation uses CSS `hue-rotate` or gradient position transitions
- Safe for all devices and browsers
- SSR-compatible, renders static prismatic gradient and animates on client
