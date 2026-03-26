---
name: texture-overlay
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/texture-overlay
category: components
tags: texture, overlay, effect, grain, noise, filter
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# TextureOverlay

> Texture overlay effect for images, sections, or any container element.

## When to Use
- Adding film grain to hero images or video backgrounds
- Creating textured overlays on solid-color sections
- Applying noise to glass-morphism elements for depth
- Photo sections needing aged or editorial texture treatment
- Any container needing subtle surface imperfection

## When NOT to Use
- Clean photography that should remain unaltered
- Already textured backgrounds where overlay doubles the effect
- Print or export contexts where overlay SVG may not translate

## Pairs Well With
- `background-texture` - Combined background + overlay textures for rich surfaces
- `aurora` - Texture overlay on aurora background for organic feel
- `spotlight-card` - Subtle texture over spotlight-lit areas
- `tilted-card` - Textured overlay on tilted card images

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| texture | 'noise' \| 'grain' \| 'dots' \| 'scratch' \| 'halftone' | 'grain' | Overlay texture type |
| opacity | number | 0.1 | Overlay opacity |
| blend | string | 'overlay' | CSS mix-blend-mode |
| color | string | '#ffffff' | Texture color |
| scale | number | 1 | Texture pattern scale |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/texture-overlay"
```

## Usage Example
```jsx
import { TextureOverlay } from "@/components/ui/texture-overlay";

export function EditorialHero() {
  return (
    <section className="relative min-h-[60vh] bg-[#0a0a0a]">
      <img
        src="/images/clinic-interior.jpg"
        alt="Clinic"
        className="absolute inset-0 w-full h-full object-cover opacity-40"
      />
      <TextureOverlay
        texture="grain"
        opacity={0.12}
        blend="overlay"
        className="absolute inset-0 pointer-events-none z-10"
      />
      <div className="relative z-20 flex items-center justify-center min-h-[60vh] px-6">
        <h2 className="font-manrope font-800 text-5xl text-white text-center">
          Crafted Experiences
        </h2>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Grain at 0.08-0.15 opacity adds editorial quality to hero images
- Always apply pointer-events-none to prevent interaction blocking
- Use blend="overlay" on #0a0a0a backgrounds for natural integration
- Combine with darkened hero images (opacity-40) for readability
- GHL safe -- CSS/SVG overlay with no JavaScript

## Performance Notes
- SVG filter-based -- resolution-independent and tiny file size
- pointer-events-none ensures zero interaction cost
- No JavaScript runtime; pure CSS pseudo-element
- No repaints or layout shifts from overlay
- Works with SSR and static generation without issues
