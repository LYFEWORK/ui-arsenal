---
name: distorted-glass
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/distorted-glass
category: components
tags: glass, distortion, frosted, blur, effect, premium
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# DistortedGlass

> Distorted frosted glass effect panel with chromatic aberration and refraction distortion.

## When to Use
- Premium hero overlays with high-end frosted glass treatment
- Creative portfolio content panels with distorted glass aesthetics
- Feature highlight panels on dark backgrounds
- Modal or dialog overlays with advanced glass morphism
- Immersive visual effects for product showcase sections

## When NOT to Use
- Standard glass morphism needs (use lyf-glass utility instead)
- Content-heavy panels where distortion reduces readability
- Performance-critical mobile pages
- Accessibility-focused interfaces where distortion confuses users

## Pairs Well With
- `aurora` - Aurora background visible through distorted glass panel
- `particles` - Particles distorted through glass refraction effect
- `gradient-text` - Gradient text inside distorted glass container
- `blur-text` - Text blur reveal inside glass panel

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| blur | number | 20 | Base blur amount in pixels |
| distortion | number | 0.3 | Glass distortion intensity |
| chromatic | boolean | true | Enable chromatic aberration |
| tint | string | '#ffffff08' | Glass tint color with alpha |
| border | boolean | true | Show glass border |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Panel content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/distorted-glass"
```

## Usage Example
```jsx
import { DistortedGlass } from "@/components/ui/distorted-glass";

export function PremiumOverlay() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      {/* Background content like aurora or particles */}
      <div className="relative z-10 flex items-center justify-center min-h-screen px-6">
        <DistortedGlass
          blur={24}
          distortion={0.2}
          chromatic={true}
          tint="#ff642a08"
          className="rounded-[12px] p-10 max-w-xl"
        >
          <h2 className="font-manrope font-800 text-4xl text-white">
            Premium Experience
          </h2>
          <p className="font-manrope font-400 text-white/70 mt-4">
            Crafted with attention to every pixel and interaction.
          </p>
        </DistortedGlass>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Tint with brand orange: "#ff642a08" for subtle warm glass on #0a0a0a
- 12px border-radius for consistency with card standards
- Manrope 800 headings remain readable through distorted glass
- Use as premium alternative to standard lyf-glass utility
- Not recommended for GHL pages -- relies on CSS filter compositing

## Performance Notes
- CSS backdrop-filter based -- requires GPU compositing
- Chromatic aberration uses multiple pseudo-elements with offset blur
- Performance cost scales with blur radius (keep under 30px)
- Safari handles backdrop-filter natively; Firefox needs -webkit prefix
- Falls back to standard blur on unsupported browsers
