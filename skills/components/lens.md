---
name: lens
source: Magic UI
source_url: https://magicui.design/docs/components/lens
category: components
tags: lens, magnify, zoom, hover, image
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Lens

> Magnifying lens effect that follows the cursor on hover over images, revealing zoomed detail.

## When to Use
- Product detail pages showing high-resolution imagery
- Portfolio showcases where design details matter
- Before/after comparisons with zoom capability
- Medical or clinical imagery that benefits from zoom
- E-commerce product galleries

## When NOT to Use
- Small thumbnail images where zoom reveals nothing useful
- Text-heavy content (use actual larger font instead)
- Mobile-first designs where hover is not available
- Performance-sensitive pages with many lens instances

## Pairs Well With
- `spotlight-card` - Card wrapper with spotlight glow containing the lens image
- `animated-content` - Fade in the lens image on scroll
- `blur-text` - Blur-reveal caption text below the image
- `tilted-card` - Combine tilt and lens for interactive image cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to apply the lens effect to |
| zoomFactor | number | 1.5 | Magnification level |
| lensSize | number | 170 | Diameter of the lens in pixels |
| hovering | boolean | undefined | Controlled hover state |
| setHovering | function | undefined | Controlled hover state setter |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/lens"
```

## Usage Example
```jsx
import { Lens } from "@/components/magicui/lens";

export function DesignShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-12">
        Pixel-perfect{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          craftsmanship
        </span>
      </h2>
      <div className="mx-auto max-w-2xl lyf-glass rounded-[12px] p-2">
        <Lens zoomFactor={2} lensSize={200}>
          <img
            src="/images/dashboard-detail.png"
            alt="Lyfework dashboard design detail"
            className="w-full rounded-[10px]"
          />
        </Lens>
      </div>
      <p className="text-center font-manrope font-400 text-white/50 mt-4 text-sm">
        Hover to inspect design details
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Wrap in `lyf-glass rounded-[12px]` for card consistency on dark backgrounds
- Lens border can be tinted with `border-[#ff642a]/30` for subtle brand accent
- Source images must be high-resolution (2x or 3x) for zoom to look sharp
- Use Manrope font-400 for captions below the lens area
- GHL compatible — uses mouse events and CSS transforms, no Web Components

## Performance Notes
- Framer Motion tracks cursor position with `useMotionValue` — efficient
- Zoom renders via CSS `transform: scale()` on a clipped region — GPU composited
- Source image should be preloaded at full resolution for smooth zoom
- Only one lens should be active at a time to prevent competing mouse listeners
- No effect on touch devices unless controlled hover state is managed manually
