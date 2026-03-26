---
name: shader-lens-blur
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/shader-lens-blur
category: animations
tags: shader, blur, lens, gpu, webgl, effect, depth
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# ShaderLensBlur

> GPU shader-based lens blur effect with bokeh simulation and depth-of-field control.

## When to Use
- Hero sections with cinematic depth-of-field blur on backgrounds
- Image galleries with focus/defocus transitions
- Portfolio showcases with professional bokeh effects
- Product photography with simulated lens blur
- Creative transitions between focused and blurred content states

## When NOT to Use
- Pages requiring broad browser support (WebGL dependency)
- Mobile-first designs where GPU shaders drain battery
- Simple blur needs (use CSS backdrop-filter instead)
- GHL embedded pages where WebGL may not initialize properly
- Accessibility-critical interfaces where blur obscures content

## Pairs Well With
- `aurora` - Aurora background with lens blur creates dreamy atmosphere
- `animated-content` - Content focuses as it enters viewport (blur to sharp)
- `gradient-text` - Sharp gradient text over lens-blurred background
- `spotlight-card` - Spotlight cards with blurred surroundings for focus emphasis

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| intensity | number | 0.5 | Blur strength (0-1) |
| bokehShape | 'circle' \| 'hexagon' \| 'star' | 'circle' | Bokeh highlight shape |
| focalPoint | { x: number; y: number } | { x: 0.5, y: 0.5 } | Focal center (0-1 range) |
| focalRange | number | 0.3 | Sharp focus radius from focal point |
| brightness | number | 1.2 | Bokeh highlight brightness boost |
| animated | boolean | false | Animate focal point |
| children | ReactNode | - | Content to apply blur effect to |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/shader-lens-blur"
```

## Usage Example
```jsx
import { ShaderLensBlur } from "@/components/ui/shader-lens-blur";

export function CinematicHero() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      <ShaderLensBlur
        intensity={0.4}
        bokehShape="hexagon"
        focalPoint={{ x: 0.5, y: 0.4 }}
        focalRange={0.35}
        brightness={1.3}
        className="absolute inset-0"
      >
        <img
          src="/images/clinic-hero.jpg"
          alt="Clinic"
          className="w-full h-full object-cover opacity-60"
        />
      </ShaderLensBlur>
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen">
        <h1 className="font-manrope font-800 text-6xl text-white drop-shadow-xl">
          Precision. Clarity. Care.
        </h1>
        <p className="font-manrope font-400 text-white/70 mt-4 max-w-lg text-center">
          Where technology meets human touch.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set focalPoint to center heading area for natural depth-of-field
- Use hexagon bokeh for professional photographic look
- Intensity 0.3-0.5 keeps background recognizable while adding depth
- Manrope 800 with drop-shadow for guaranteed readability over blur
- Not compatible with GHL embeds -- use CSS blur as fallback

## Performance Notes
- WebGL fragment shader runs on GPU -- offloads CPU entirely
- Shader compiles once on mount; subsequent frames are efficient
- Bokeh shape complexity affects fragment shader performance minimally
- Falls back to CSS blur filter on devices without WebGL
- IntersectionObserver pauses shader when off-screen
- Budget 5-10ms per frame on mid-range GPUs
