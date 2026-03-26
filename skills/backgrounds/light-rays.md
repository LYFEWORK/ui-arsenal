---
name: light-rays
source: ReactBits
source_url: https://reactbits.dev/backgrounds/light-rays
category: backgrounds
tags: background, light, rays, radiate, sun, glow, dramatic
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# LightRays

> Radiating light rays emanating from a focal point, creating a sunburst or divine light effect. Adds drama and directional energy to hero sections and key content areas.

## When to Use

- Hero sections for launch or reveal pages with a "dawn" theme
- Behind product showcases to create a halo/spotlight effect
- Event or conference landing pages for a stage-lighting feel
- Achievement or milestone sections to add celebratory energy
- Behind logos or brand marks for a premium presentation

## When NOT to Use

- Subtle, minimal design systems where the rays feel heavy-handed
- Multiple sections on the same page (one sunburst per page max)
- Behind text-heavy content where the rays create uneven readability
- Light-themed pages where the rays blend into the background

## Pairs Well With

- `blur-text` - Text revealing in the center of radiating rays is dramatic
- `gradient-text` - Gradient text that echoes the ray colors creates harmony
- `animated-content` - Content appearing at the focal point of the rays
- `count-up` - Animated numbers in the center of rays for milestone/achievement sections

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#ffffff" | Color of the light rays |
| rayCount | number | 12 | Number of rays emanating from the center |
| spread | number | 360 | Angular spread of rays in degrees |
| intensity | number | 0.5 | Brightness of the rays (0-1) |
| origin | string | "center" | Focal point: "center", "top", "bottom" |
| animated | boolean | true | Whether rays rotate slowly |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LightRays-TS-TW
```

## Usage Example

```jsx
import LightRays from '@/components/ui/LightRays';
import BlurText from '@/components/ui/BlurText';

function MilestoneSection() {
  return (
    <section className="relative py-32 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <LightRays
          color="#ff642a"
          rayCount={16}
          spread={360}
          intensity={0.2}
          origin="center"
          animated={true}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="5 Years. 500+ Builds."
          delay={150}
          animateBy="words"
          className="text-4xl md:text-6xl font-bold text-white font-[Manrope]"
        />
        <p className="mt-6 text-xl text-gray-300 font-[Manrope]">
          Half a decade of building infrastructure that lasts.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework rays: `color="#ff642a"` at `intensity={0.15-0.25}` for a warm, subtle glow
- For celebrations/milestones: bump `intensity` to 0.3-0.4 for more drama
- `rayCount` of 12-20 looks balanced. Below 8 looks sparse, above 24 becomes a solid glow.
- The slow rotation (`animated={true}`) should be barely perceptible, around 60 seconds per revolution
- GHL: replicate with a CSS `conic-gradient` and a slow `rotate` animation
- For client builds: use their accent color at low intensity. The rays should feel like ambient light, not a flashlight.

## Performance Notes

- CSS `conic-gradient` with rotation animation, lightweight
- No canvas or WebGL dependency
- The rotation animation is GPU-accelerated via `transform: rotate()`
- Safe for all devices, though reduce `rayCount` on mobile for cleaner rendering
- SSR-compatible, renders static rays and rotates on client
