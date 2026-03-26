---
name: texture-button
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/texture-button
category: components
tags: button, texture, surface, tactile, pattern
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# TextureButton

> Button with textured surface pattern for tactile visual depth and unique aesthetics.

## When to Use
- Creative or portfolio sites with distinctive button design
- Premium product pages where buttons need visual weight
- Dark-themed interfaces where texture adds visual interest
- Call-to-action buttons that need to stand out from flat UI
- Design showcase pages demonstrating UI craftsmanship

## When NOT to Use
- Standard SaaS interfaces where flat/gradient buttons are expected
- Text-heavy forms where textured buttons distract from content
- High-contrast accessibility modes where patterns reduce readability
- Minimal designs where texture conflicts with clean aesthetics

## Pairs Well With
- `texture-card` - Matching textured surface language across cards and buttons
- `texture-overlay` - Consistent texture theme across the section
- `gradient-text` - Gradient text paired with textured button surfaces
- `spotlight-card` - Textured buttons inside spotlight-enhanced cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| texture | 'noise' \| 'grain' \| 'fabric' \| 'metal' \| 'paper' | 'noise' | Surface texture type |
| variant | 'default' \| 'outline' \| 'ghost' | 'default' | Button variant |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Button size |
| textureOpacity | number | 0.15 | Texture visibility |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Button content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/texture-button"
```

## Usage Example
```jsx
import { TextureButton } from "@/components/ui/texture-button";

export function CreativeHeroCTA() {
  return (
    <div className="bg-[#0a0a0a] p-8 flex gap-4">
      <TextureButton
        texture="grain"
        variant="default"
        size="lg"
        textureOpacity={0.12}
        className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 rounded-[8px]"
      >
        Start Your Project
      </TextureButton>
      <TextureButton
        texture="noise"
        variant="outline"
        size="lg"
        className="font-manrope font-700 rounded-[8px] border-white/20"
      >
        View Portfolio
      </TextureButton>
    </div>
  );
}
```

## Lyfework Customization Notes
- Apply brand gradient with grain texture for primary CTAs on #0a0a0a
- Outline variant with noise texture for secondary actions
- Manrope 700, rounded-[8px] standard button radius
- textureOpacity 0.08-0.15 keeps text readable
- GHL compatible -- texture is CSS-based with no external assets

## Performance Notes
- Texture is generated via CSS SVG filter -- no image assets needed
- Zero JavaScript runtime cost; texture is pure CSS
- Hover state transitions use CSS transition only
- Sub-1KB component addition to bundle
- No repaints from texture layer (it's a pseudo-element)
