---
name: pixel-snow
source: ReactBits
source_url: https://reactbits.dev/backgrounds/pixel-snow
category: backgrounds
tags: background, pixel, snow, falling, particles, winter, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# PixelSnow

> Falling pixel-art snow particles that drift down the screen, creating a calm, ambient winter/digital effect. Works as a seasonal overlay or a subtle ambient particle background.

## When to Use

- Seasonal winter/holiday themed landing pages
- Ambient background for calm, quiet sections
- Behind "coming soon" or waiting states for gentle visual activity
- Portfolio or creative pages going for a digital-art aesthetic
- Overlay on any dark section for ambient particle movement

## When NOT to Use

- Summer, tropical, or warm-themed pages (thematic mismatch)
- Year-round professional pages where seasonal theming feels out of place
- Behind dense content or forms (falling particles distract from input)
- Sections with other particle effects (visual clutter)

## Pairs Well With

- `blur-text` - Text revealing through falling snow creates a serene entrance
- `animated-content` - Content appearing through the snowfall feels natural
- `spotlight-card` - Cards collecting "snow" at their tops for a playful touch
- `gradient-text` - Cool-toned gradient text complements the winter aesthetic

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| flakeCount | number | 50 | Number of snow particles |
| flakeColor | string | "#ffffff" | Color of the snow pixels |
| flakeSize | number | 3 | Size of each snow pixel |
| speed | number | 1.0 | Fall speed of the snow |
| wind | number | 0 | Horizontal drift amount (-1 to 1) |
| opacity | number | 0.6 | Opacity of the snow particles |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PixelSnow-TS-TW
```

## Usage Example

```jsx
import PixelSnow from '@/components/ui/PixelSnow';
import BlurText from '@/components/ui/BlurText';

function SeasonalHero() {
  return (
    <section className="relative min-h-[70vh] flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <PixelSnow
          flakeCount={40}
          flakeColor="rgba(255,255,255,0.7)"
          flakeSize={2}
          speed={0.8}
          wind={0.1}
          opacity={0.5}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Season's Greetings"
          delay={150}
          animateBy="words"
          className="text-4xl md:text-6xl font-bold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 font-[Manrope]">
          Wishing you warmth, growth, and unstoppable momentum.
        </p>
        <button className="mt-8 px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]">
          Unwrap Your Offer
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- For Lyfework holiday campaigns: white flakes over #0a0a0a with brand CTA buttons
- For client holiday builds: match flake color to their brand palette at 50-70% opacity
- `flakeCount` of 30-50 looks ambient. Above 80 starts looking like a blizzard.
- `wind` of 0.05-0.15 adds natural lateral drift. Above 0.3 looks like a storm.
- GHL: replicate with CSS keyframe animations on small absolute-positioned elements
- Only deploy seasonally or on explicitly themed pages, never as a permanent background

## Performance Notes

- Lightweight CSS animation on individual particle elements
- Each flake is a small DOM element with transform animation
- Keep `flakeCount` under 60 on mobile for smooth performance
- The animation is purely CSS-driven, no requestAnimationFrame overhead
- SSR-compatible, flakes render in starting positions and fall on client
