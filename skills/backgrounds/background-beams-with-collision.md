---
name: background-beams-with-collision
source: Aceternity UI
source_url: https://ui.aceternity.com/components/background-beams-with-collision
category: backgrounds
tags: beams, collision, scatter, background, animated, particles, physics
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# BackgroundBeamsWithCollision

> Animated light beams that travel across the screen and scatter on collision with a surface, creating a dynamic physics-based background.

## When to Use
- Hero sections on AI or tech product pages
- Above-fold backgrounds for SaaS landing pages
- Feature announcement sections with dramatic atmosphere
- Contact or CTA sections with ambient visual energy
- Event or launch pages with cinematic backgrounds

## When NOT to Use
- On text-heavy pages where beams distract from reading
- For conservative/corporate audiences expecting minimal design
- When multiple animated backgrounds are already competing on the page

## Pairs Well With
- `gradient-text` - Headline text over the beam background
- `blur-text` - Text entrance animation over the beams
- `animated-content` - Foreground content animates independently
- `floating-navbar` - Transparent navbar over the beam hero

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| className | string | - | Classes for the background container |
| children | ReactNode | - | Content rendered over the beam background |

## Installation
```bash
npx aceternity-ui@latest add background-beams-with-collision
```

## Usage Example
```jsx
import { BackgroundBeamsWithCollision } from "@/components/ui/background-beams-with-collision";

export function CTASection() {
  return (
    <BackgroundBeamsWithCollision className="bg-[#0a0a0a] min-h-[600px] flex items-center justify-center">
      <div className="text-center relative z-10 px-6">
        <h2 className="font-[Manrope] font-800 text-5xl text-white mb-6">
          Ready to{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Transform
          </span>{" "}
          Your Practice?
        </h2>
        <p className="font-[Manrope] font-400 text-neutral-400 text-xl mb-10 max-w-xl mx-auto">
          Let us build the website your clinic deserves.
        </p>
        <button className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px] text-lg">
          Start Your Project
        </button>
      </div>
    </BackgroundBeamsWithCollision>
  );
}
```

## Lyfework Customization Notes
- Beam colors can include brand orange `#ff642a` and red `#ff0301`
- Background base is #0a0a0a for maximum beam visibility
- Foreground content needs `relative z-10` to sit above beams
- Manrope 800 for headlines, 700 for CTA buttons, 400 for subtext
- GHL compatible with proper container sizing; beams render within bounds

## Performance Notes
- Beam animation uses CSS `@keyframes` with `translateY`, GPU-accelerated
- Collision effect uses framer-motion for scatter animation, runs on GPU
- Limit beam count (8-12) to balance visual density with performance
- Beams are thin DOM elements with box-shadow for glow, lightweight rendering
- Consider reducing beam count on mobile via media query or JS check
