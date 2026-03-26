---
name: plasma
source: ReactBits
source_url: https://reactbits.dev/backgrounds/plasma
category: backgrounds
tags: background, plasma, fluid, lava, organic, animated, vibrant
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Plasma

> An animated plasma/lava-lamp fluid effect with vibrant, shifting color blobs. Creates a retro-futuristic, organic background that pulses with life and energy.

## When to Use

- Creative agency or studio hero sections for bold visual impact
- Music, entertainment, or nightlife event landing pages
- Behind pricing sections where you want a vibrant, energetic backdrop
- Portfolio sections showcasing creative or experimental work
- Retro-themed landing pages with a modern twist

## When NOT to Use

- Corporate or professional service sites (too vibrant and playful)
- Medical, legal, or finance pages (distractingly colorful)
- Behind text-heavy content (the shifting colors hurt readability)
- Pages that require fast load and minimal GPU usage

## Pairs Well With

- `blur-text` - Text revealing over the plasma creates a vivid, energetic hero
- `gradient-text` - Gradient text picking up the plasma's color palette for cohesion
- `animated-content` - Content fading in over the shifting plasma feels dynamic
- `spotlight-card` - Cards over plasma with glass styling create a nightclub dashboard look

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#ff0080","#7928ca","#0070f3"] | Color palette for the plasma blobs |
| speed | number | 0.5 | Speed of the plasma movement |
| blobCount | number | 4 | Number of overlapping plasma blobs |
| blur | number | 60 | Blur amount for the soft blob edges |
| scale | number | 1.0 | Scale of the plasma pattern |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Plasma-TS-TW
```

## Usage Example

```jsx
import Plasma from '@/components/ui/Plasma';
import BlurText from '@/components/ui/BlurText';

function CreativeAgencyHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0 opacity-50">
        <Plasma
          colors={['#ff642a', '#ff0301', '#1a0a2e', '#ff642a']}
          speed={0.3}
          blobCount={4}
          blur={80}
          scale={1.2}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Where Ideas Ignite."
          delay={150}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-200 max-w-xl mx-auto font-[Manrope]">
          Creative execution that sets your brand on fire.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework plasma: `['#ff642a', '#ff0301', '#1a0a2e', '#ff642a']` at 40-60% opacity
- Keep `speed` at 0.2-0.4 for a lava-lamp feel. Above 0.6 gets frenetic.
- `blur` of 60-100 keeps the blobs soft. Below 40 shows hard edges which breaks the effect.
- Wrap the plasma in `opacity-40` to `opacity-60` to keep it ambient, not overwhelming
- For GHL: approximate with multiple blurred, animated gradient circles using CSS animations
- Layer a `bg-black/30` overlay between plasma and text if readability is a concern

## Performance Notes

- Uses CSS filter blur on animated gradient elements
- `blobCount` directly impacts performance. Keep at 3-5 for smooth animation.
- The blur filter is GPU-accelerated but still has cost at large sizes
- Reduce `blur` and `blobCount` on mobile devices
- SSR-compatible, renders a static gradient fallback and animates on client
