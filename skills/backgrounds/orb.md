---
name: orb
source: ReactBits
source_url: https://reactbits.dev/backgrounds/orb
category: backgrounds
tags: background, orb, sphere, glow, ambient, gradient, blur
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Orb

> A glowing, blurred orb/sphere that serves as an ambient background element. The simplest way to add color, depth, and a premium glow to any dark section.

## When to Use

- Behind any dark section that needs a pop of ambient color
- Hero sections paired with other effects for layered depth
- Behind cards or content blocks to create a soft spotlight effect
- Corner accents on sections to break up flat backgrounds
- Behind CTAs to draw the eye with a subtle glow

## When NOT to Use

- As the sole visual element of a hero section (too simple on its own)
- On light-themed pages where the glow effect is invisible
- When you need the orb to be perfectly circular (blur makes it amorphous)

## Pairs Well With

- `spotlight-card` - An orb behind spotlight cards adds an extra layer of depth
- `blur-text` - Text revealing over an orb glow creates a premium focal point
- `animated-content` - Content appearing near the orb feels naturally illuminated
- `dot-grid` - Orb over a dot grid creates a layered, SaaS-style background

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#8b5cf6" | Color of the orb |
| size | number | 400 | Diameter of the orb in pixels |
| blur | number | 80 | Blur radius applied to the orb |
| opacity | number | 0.5 | Opacity of the orb (0-1) |
| position | object | { top: "50%", left: "50%" } | Position of the orb center |
| animated | boolean | false | Whether the orb drifts/pulses |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Orb-TS-TW
```

## Usage Example

```jsx
import Orb from '@/components/ui/Orb';
import SpotlightCard from '@/components/ui/SpotlightCard';

function FeaturesSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      {/* Background orbs */}
      <Orb
        color="#ff642a"
        size={500}
        blur={100}
        opacity={0.15}
        position={{ top: '20%', left: '10%' }}
      />
      <Orb
        color="#ff0301"
        size={400}
        blur={120}
        opacity={0.1}
        position={{ top: '60%', left: '80%' }}
      />

      <div className="relative z-10 max-w-6xl mx-auto px-8">
        <h2 className="text-3xl font-bold text-white text-center font-[Manrope]">
          Built for Scale
        </h2>
        <div className="mt-12 grid grid-cols-1 md:grid-cols-3 gap-8">
          <SpotlightCard className="p-8 rounded-2xl">
            <h3 className="text-xl font-bold text-white">Automation</h3>
            <p className="mt-2 text-gray-400">Set it and forget it.</p>
          </SpotlightCard>
          {/* More cards */}
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework orb palette: `#ff642a` (primary) and `#ff0301` (secondary) at 10-20% opacity
- Use 2-3 orbs per section max, placed asymmetrically for organic balance
- `blur` of 80-150 keeps the orb soft and ambient. Below 50 shows a defined circle.
- `opacity` of 0.1-0.2 is the sweet spot for subtle glow. Above 0.3 starts to dominate.
- GHL: replicate with a `div` using `border-radius: 50%`, `filter: blur(80px)`, and absolute positioning
- The Orb is the most reusable background element. It works on literally every page.
- For client builds: use their primary accent color at 10-15% opacity

## Performance Notes

- Single DOM element with CSS `border-radius` and `filter: blur()`
- Extremely lightweight, near-zero performance impact
- The blur filter is GPU-accelerated in modern browsers
- Animated variant uses CSS keyframes for gentle drift, negligible cost
- SSR-compatible with zero hydration overhead
