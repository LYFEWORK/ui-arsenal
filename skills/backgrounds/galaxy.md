---
name: galaxy
source: ReactBits
source_url: https://reactbits.dev/backgrounds/galaxy
category: backgrounds
tags: background, galaxy, stars, space, interactive, WebGL, ambient
dependencies: ogl
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Galaxy

> An interactive star field with twinkling stars, glow effects, and mouse-responsive movement. More ambient and subtle than Hyperspeed. Stars shift and twinkle naturally.

## When to Use

- Hero backgrounds that need atmosphere without overwhelming drama
- "About us" or vision/mission sections with an aspirational tone
- SaaS or technology product pages
- Dark-themed sites that need visual depth beyond a flat color
- Sections where Particles feels too technical and Aurora feels too organic

## When NOT to Use

- Light-themed designs
- Pages with heavy image content (visual competition)
- Client verticals that don't align with space/tech aesthetics
- More than one animated background per page

## Pairs Well With

- `blur-text` - Stars behind blur-revealing headline
- `split-text` - Text reveals as stars twinkle around it
- `spotlight-card` - Cards over a subtle star field
- `count-up` - Metrics floating in a galaxy

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| density | number | 1 | Star density multiplier |
| glowIntensity | number | 0.3 | Star glow brightness |
| twinkleIntensity | number | 0.3 | Twinkle animation intensity |
| speed | number | 0.5 | Star movement speed |
| mouseInteraction | boolean | true | Stars respond to cursor |
| hueShift | number | 140 | Color hue in degrees |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Galaxy-TS-TW
```

## Usage Example

```jsx
import Galaxy from '@/components/ui/Galaxy';
import BlurText from '@/components/ui/BlurText';

function VisionSection() {
  return (
    <section className="relative min-h-[70vh] flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Galaxy density={0.8} glowIntensity={0.2} speed={0.3} hueShift={20} />
      </div>
      <div className="relative z-10 text-center max-w-3xl px-8">
        <BlurText text="Building the Future of Business Infrastructure." delay={150} className="text-4xl md:text-5xl font-extrabold text-white" />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- `hueShift` of 15-25 gives warm orange-tinted stars matching Lyfework brand
- `density` of 0.6-1.0 for subtle. Above 1.5 feels crowded.
- `glowIntensity` of 0.15-0.3 for ambient glow. Above 0.5 becomes a light show.
- More versatile than Hyperspeed. Can be used on multiple site types.
- Uses OGL library (lighter than Three.js) but still not suitable for GHL
- Add dark overlay for text readability if needed

## Performance Notes

- OGL (OpenGL library) is lighter than Three.js (~40kb vs ~150kb)
- WebGL canvas, runs on GPU
- Reduce density on mobile
- Respects `prefers-reduced-motion`
