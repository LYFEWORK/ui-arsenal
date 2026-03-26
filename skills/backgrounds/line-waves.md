---
name: line-waves
source: ReactBits
source_url: https://reactbits.dev/backgrounds/line-waves
category: backgrounds
tags: background, lines, waves, flowing, svg, organic, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# LineWaves

> Animated wavy lines flowing across the background in organic, undulating patterns. A clean, versatile ambient background that works across nearly any page type.

## When to Use

- Hero sections on SaaS, agency, or portfolio sites for ambient motion
- Section backgrounds on long-scroll landing pages
- Behind feature grids to add organic movement without distraction
- Professional service page backgrounds (clinic, consulting, finance)
- Footer or above-footer sections for a soft visual transition

## When NOT to Use

- Sections that already have wavy dividers or SVG wave separators (visual conflict)
- Behind audio/music-related content where the "sound wave" association may confuse
- Very small containers where the wave pattern gets compressed

## Pairs Well With

- `animated-content` - Content fading in over flowing waves feels seamless and natural
- `spotlight-card` - Cards over line waves create a clean, professional layered look
- `blur-text` - Text revealing over the organic wave motion adds polish
- `split-text` - GSAP text animation over waves for scroll-triggered hero reveals

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| lineCount | number | 5 | Number of wave lines |
| lineColor | string | "rgba(255,255,255,0.1)" | Color of the wave lines |
| amplitude | number | 30 | Height of the wave peaks in pixels |
| frequency | number | 0.02 | Wave frequency (tightness of the curves) |
| speed | number | 0.5 | Animation speed of the flowing motion |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LineWaves-TS-TW
```

## Usage Example

```jsx
import LineWaves from '@/components/ui/LineWaves';
import AnimatedContent from '@/components/ui/AnimatedContent';

function FeatureSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <LineWaves
          lineCount={4}
          lineColor="rgba(255,100,42,0.08)"
          amplitude={25}
          frequency={0.015}
          speed={0.3}
        />
      </div>

      <div className="relative z-10 max-w-6xl mx-auto px-8">
        <AnimatedContent direction="up" delay={200}>
          <h2 className="text-3xl md:text-4xl font-bold text-white text-center font-[Manrope]">
            Everything You Need, Nothing You Don't
          </h2>
        </AnimatedContent>

        <div className="mt-16 grid grid-cols-1 md:grid-cols-3 gap-8">
          {/* Feature cards */}
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework wave color: `rgba(255,100,42,0.08)` for a barely-visible brand warmth
- For clinic sites: `rgba(255,255,255,0.05)` keeps waves neutral and professional
- `lineCount` of 3-5 is the sweet spot. More than 7 starts looking like a music visualizer.
- `speed` of 0.2-0.4 feels ambient and premium. Above 0.6 feels restless.
- `amplitude` of 20-35px works for most section heights. Scale up for taller sections.
- GHL: use inline SVG with CSS keyframe animations for the wave path morphing
- Pairs perfectly with Manrope headings and `rounded-2xl` card borders

## Performance Notes

- SVG path-based animation, lightweight and resolution-independent
- No canvas or WebGL dependency
- Each wave line is a single SVG `<path>` element animated via CSS or requestAnimationFrame
- Safe for all devices including mobile
- SSR-compatible, renders static wave paths and animates on client
