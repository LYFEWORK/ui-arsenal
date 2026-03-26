---
name: pointer-highlight
source: Aceternity UI
source_url: https://ui.aceternity.com/components/pointer-highlight
category: animations
tags: cursor, pointer, highlight, glow, follow, interactive, hover
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# PointerHighlight

> Cursor-following highlight or glow effect that tracks the mouse pointer across an element, creating ambient interactivity.

## When to Use
- Interactive text blocks where words highlight as cursor moves over them
- Feature sections with cursor-responsive ambient lighting
- Card surfaces with following glow for depth perception
- Navigation menus with pointer-tracking highlight
- Hero sections with subtle cursor-aware interaction

## When NOT to Use
- On mobile layouts where cursor tracking is not available
- When other cursor-tracking effects already exist on the same page
- For rapidly scrolled content where the effect is barely noticeable

## Pairs Well With
- `spotlight-card` - Pointer highlight on card surfaces alongside spotlight
- `gradient-text` - Highlight color matches gradient text for consistency
- `hero-highlight` - Different scales of cursor tracking for hero vs content
- `animated-content` - Content entrance before pointer tracking activates

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content to apply the highlight to |
| className | string | - | Classes for the container |
| highlightColor | string | "#ff642a" | Color of the pointer highlight |
| highlightSize | number | 200 | Diameter of the highlight glow in pixels |

## Installation
```bash
npx aceternity-ui@latest add pointer-highlight
```

## Usage Example
```jsx
import { PointerHighlight } from "@/components/ui/pointer-highlight";

export function InteractiveFeatures() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <PointerHighlight highlightColor="#ff642a" className="max-w-4xl mx-auto">
        <div className="lyf-glass rounded-[12px] p-12 border border-white/10">
          <h2 className="font-[Manrope] font-800 text-4xl text-white mb-6">
            Why Choose <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Lyfework</span>
          </h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-8 mt-8">
            <div>
              <h3 className="font-[Manrope] font-700 text-lg text-white">AI-First Approach</h3>
              <p className="font-[Manrope] font-400 text-neutral-400 mt-2">Every feature powered by intelligent automation.</p>
            </div>
            <div>
              <h3 className="font-[Manrope] font-700 text-lg text-white">GHL Integration</h3>
              <p className="font-[Manrope] font-400 text-neutral-400 mt-2">Native GoHighLevel CRM connectivity.</p>
            </div>
          </div>
        </div>
      </PointerHighlight>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `highlightColor` to `#ff642a` for brand-consistent pointer glow
- Container uses `lyf-glass` with `rounded-[12px]` and `border border-white/10`
- Manrope 800 for section titles, 700 for feature names, 400 for descriptions
- Works best on dark #0a0a0a surfaces where the glow has contrast
- GHL compatible; mouse events work within iframe contexts

## Performance Notes
- Pointer tracking uses `mousemove` with passive listeners, no scroll blocking
- Highlight is a single radial gradient repositioned via CSS custom properties
- GPU-composited via CSS `background-position` or `transform`
- No canvas or WebGL; pure CSS rendering for broad browser support
- Safe to use on large containers without performance degradation
