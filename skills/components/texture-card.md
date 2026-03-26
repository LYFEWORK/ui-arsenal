---
name: texture-card
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/texture-card
category: components
tags: card, texture, surface, tactile, pattern
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# TextureCard

> Card with textured background surface for tactile visual depth and material feel.

## When to Use
- Feature cards needing physical, material-like qualities
- Premium product showcases with crafted surface feel
- Portfolio project cards with distinctive visual texture
- Dashboard widgets with differentiated surface treatments
- Dark-themed sections where texture adds dimension

## When NOT to Use
- Clean minimal designs where texture adds visual noise
- Image-heavy cards where texture competes with photos
- Dense layouts where multiple textured cards feel busy

## Pairs Well With
- `texture-button` - Matching textured button inside textured card
- `texture-overlay` - Layered texture effects for depth
- `animated-content` - Textured cards animating into view
- `spotlight-card` - Combine spotlight hover with surface texture

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| texture | 'noise' \| 'grain' \| 'fabric' \| 'concrete' \| 'paper' | 'noise' | Surface texture type |
| textureOpacity | number | 0.1 | Texture visibility |
| variant | 'default' \| 'bordered' \| 'elevated' | 'default' | Card variant |
| hover | boolean | true | Enable hover effects |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Card content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/texture-card"
```

## Usage Example
```jsx
import { TextureCard } from "@/components/ui/texture-card";

export function ServiceCards() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-5xl mx-auto">
        <TextureCard
          texture="grain"
          textureOpacity={0.08}
          variant="bordered"
          className="rounded-[12px] p-6"
        >
          <h3 className="font-manrope font-700 text-xl text-white">Web Design</h3>
          <p className="font-manrope font-400 text-white/60 mt-3">
            Custom websites built on modern frameworks with conversion optimization.
          </p>
        </TextureCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use grain texture at 0.05-0.10 opacity on lyf-glass cards
- 12px card radius with border-white/10 for bordered variant
- Manrope 700 titles, 400 body text on textured surface
- Hover state: slight border color shift to #ff642a/20
- GHL compatible -- CSS texture with no external dependencies

## Performance Notes
- Texture is CSS SVG filter -- no image assets
- Zero JavaScript runtime; texture is a pseudo-element
- hover effect uses CSS transition only
- No repaints from texture layer
- Sub-1KB component with no dependencies
