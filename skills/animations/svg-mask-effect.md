---
name: svg-mask-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/svg-mask-effect
category: animations
tags: svg, mask, reveal, cursor, content, effect, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# SvgMaskEffect

> SVG mask that reveals content underneath as the cursor moves, creating a spotlight/window effect to expose hidden layers.

## When to Use
- Before/after reveals where the cursor exposes a new layer
- Interactive hero sections with hidden messaging under a surface
- Dark/light mode previews where cursor reveals the alternate theme
- Product comparison sections with cursor-driven reveal
- Creative portfolio showcases with layered content

## When NOT to Use
- When both content layers must be visible simultaneously
- On mobile without a touch-drag fallback implementation
- For text-critical content where hidden layers frustrate users

## Pairs Well With
- `text-reveal-card` - Similar concept at card scale vs section scale
- `particles` - Particles in the revealed layer for added depth
- `gradient-text` - Gradient text in the revealed content
- `aurora` - Aurora as the hidden layer revealed by the mask

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Top layer content |
| revealContent | ReactNode | - | Hidden layer revealed by cursor |
| size | number | 200 | Mask circle diameter in pixels |
| className | string | - | Classes for the container |
| revealSize | number | 300 | Reveal area diameter when hovering |

## Installation
```bash
npx aceternity-ui@latest add svg-mask-effect
```

## Usage Example
```jsx
import { MaskContainer } from "@/components/ui/svg-mask-effect";

export function BeforeAfterReveal() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-5xl mx-auto h-[500px]">
        <MaskContainer
          revealText={
            <p className="font-[Manrope] font-800 text-5xl text-white text-center max-w-4xl mx-auto">
              Websites that{" "}
              <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
                convert patients and close deals.
              </span>
            </p>
          }
          className="rounded-[12px] border border-white/10"
          size={250}
        >
          <p className="font-[Manrope] font-800 text-5xl text-neutral-600 text-center max-w-4xl mx-auto">
            Just another website agency with generic templates.
          </p>
        </MaskContainer>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Revealed text uses `from-[#ff642a] to-[#ff0301]` gradient for brand impact
- Container uses `rounded-[12px]` with `border border-white/10` on #0a0a0a
- Top layer text in neutral-600 creates clear contrast with revealed white/gradient text
- Manrope 800 at 5xl for both layers for typographic consistency
- Provide mobile fallback that auto-reveals the content without cursor interaction

## Performance Notes
- SVG mask uses `clipPath` with `circle()` function, GPU-composited
- Cursor position updates via `mousemove` at animation frame rate
- Both content layers are rendered in DOM; keep each layer's content lightweight
- Mask circle size transition uses CSS `transition`, smooth at 60fps
- Single instance per page recommended for performance and visual clarity
