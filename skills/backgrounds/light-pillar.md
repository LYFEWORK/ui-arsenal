---
name: light-pillar
source: ReactBits
source_url: https://reactbits.dev/backgrounds/light-pillar
category: backgrounds
tags: background, light, pillar, beam, vertical, dramatic, glow
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# LightPillar

> A vertical light pillar/beam that rises from the bottom of the section, creating a dramatic spotlight effect. Draws the eye upward and adds a sense of grandeur to hero sections.

## When to Use

- Hero sections where you want to draw attention to a centered headline
- Product launch or reveal pages for a dramatic "unveiling" effect
- Behind CTAs or key conversion elements to create visual weight
- Event landing pages for a stage-light or spotlight feel
- About/mission sections to add gravitas to the messaging

## When NOT to Use

- Multi-column layouts where the centered beam creates visual imbalance
- Sections with left or right-aligned content (beam fights the layout)
- Light-themed pages where the beam effect loses its impact
- Dense content sections where the beam becomes a distraction

## Pairs Well With

- `blur-text` - Headline revealing in the center of the light pillar is cinematic
- `split-text` - Text splitting upward in sync with the rising beam
- `animated-content` - CTA button appearing at the base of the light pillar
- `gradient-text` - Gradient text centered in the pillar glow creates a premium feel

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#ffffff" | Color of the light pillar |
| width | number | 200 | Width of the beam in pixels |
| intensity | number | 0.6 | Brightness/opacity of the beam (0-1) |
| animated | boolean | true | Whether the beam pulses/breathes |
| position | string | "center" | Horizontal position: "left", "center", "right" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LightPillar-TS-TW
```

## Usage Example

```jsx
import LightPillar from '@/components/ui/LightPillar';
import BlurText from '@/components/ui/BlurText';

function LaunchHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <LightPillar
          color="#ff642a"
          width={300}
          intensity={0.3}
          animated={true}
          position="center"
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Something Big Is Coming."
          delay={200}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-xl mx-auto font-[Manrope]">
          The next evolution of business infrastructure drops soon.
        </p>
        <button className="mt-10 px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]">
          Get Early Access
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework pillar: `color="#ff642a"` at `intensity={0.25-0.35}` for a warm brand glow
- For client builds: use their primary color at low intensity for a subtle accent
- `width` of 200-400px works for most hero sections. Wider beams feel more ambient, narrow feels focused.
- Keep `intensity` at 0.2-0.4 to avoid washing out the text above it
- GHL: replicate with a CSS `linear-gradient` from transparent to the beam color on a centered div
- The breathing animation should be slow (3-5 second cycle) for a premium, meditative feel

## Performance Notes

- Pure CSS gradient and opacity animation, very lightweight
- No canvas or WebGL dependency
- The pulsing animation uses CSS `opacity` transitions for GPU acceleration
- Safe for all devices and browsers
- SSR-compatible, renders the static beam and animates on client
