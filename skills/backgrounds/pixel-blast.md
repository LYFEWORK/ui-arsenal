---
name: pixel-blast
source: ReactBits
source_url: https://reactbits.dev/backgrounds/pixel-blast
category: backgrounds
tags: background, pixel, blast, explode, dramatic, canvas, energy
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# PixelBlast

> An exploding pixel burst background effect where pixels scatter outward from a focal point. Creates high-energy, explosive visual impact for launches and dramatic reveals.

## When to Use

- Product launch hero sections for maximum visual impact
- Game or entertainment product pages
- Event countdown reveals where the blast triggers at zero
- Creative agency portfolio "impact" sections
- Interactive sections where click/tap triggers the blast

## When NOT to Use

- Professional or corporate client sites (too chaotic)
- Medical, legal, or finance pages (completely wrong tone)
- Content-heavy sections (impossible to read over exploding pixels)
- Mobile-primary experiences (canvas performance concerns)
- Accessibility-critical pages (motion is extreme)

## Pairs Well With

- `blur-text` - Text emerging from the pixel blast is a dramatic reveal
- `count-up` - Countdown hitting zero and triggering a pixel blast
- `gradient-text` - Bold gradient text as the focal point of the explosion
- `animated-content` - Content appearing after the blast settles

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| pixelCount | number | 500 | Number of pixels in the explosion |
| colors | string[] | ["#ff0000","#ffaa00","#ffffff"] | Colors of the pixels |
| speed | number | 1.0 | Speed of the explosion |
| origin | object | { x: "50%", y: "50%" } | Origin point of the blast |
| trigger | string | "onView" | Trigger: "onView", "onClick", "onLoad" |
| respawn | boolean | false | Whether pixels reform and blast again |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PixelBlast-TS-TW
```

## Usage Example

```jsx
import PixelBlast from '@/components/ui/PixelBlast';
import GradientText from '@/components/ui/GradientText';

function LaunchReveal() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <PixelBlast
          pixelCount={400}
          colors={['#ff642a', '#ff0301', '#ffffff', '#0a0a0a']}
          speed={0.8}
          origin={{ x: '50%', y: '50%' }}
          trigger="onView"
          respawn={false}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <GradientText
          colors={['#ff642a', '#ff0301']}
          className="text-5xl md:text-8xl font-extrabold font-[Manrope]"
        >
          LAUNCHED.
        </GradientText>
        <p className="mt-6 text-lg text-gray-300 font-[Manrope]">
          The future of business infrastructure is live.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework blast colors: `['#ff642a', '#ff0301', '#ffffff', '#0a0a0a']` for brand-aligned explosion
- Use `trigger="onView"` for scroll-triggered blasts, `trigger="onClick"` for interactive moments
- `pixelCount` of 300-500 looks impactful. Above 800 causes performance issues.
- Set `respawn={false}` for a one-time reveal effect. `respawn={true}` for a looping background.
- For GHL: not recommended. Canvas particle systems require a proper React render context.
- Only use for Lyfework brand pages or special campaign builds. Never for standard client sites.

## Performance Notes

- Canvas-based particle system with requestAnimationFrame loop
- GPU-intensive with high pixel counts, always provide a static fallback
- Reduce `pixelCount` to 200-300 on mobile or disable entirely
- One-time blast (`respawn={false}`) is lighter since the animation loop stops after settling
- Not SSR-compatible, renders a blank canvas on server, initializes on client
- Consider intersection observer to only run when visible
