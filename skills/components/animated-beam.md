---
name: animated-beam
source: Magic UI
source_url: https://magicui.design/docs/components/animated-beam
category: components
tags: beam, svg, connection, integrations, animation
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# AnimatedBeam

> Animated SVG light beam that visually connects two elements, ideal for illustrating integrations or data flow.

## When to Use
- Showing integrations between platforms (e.g., GHL to Stripe connection)
- Visualizing data pipelines or workflow automation steps
- Building "how it works" sections with connected nodes
- Illustrating API connections between services
- Creating interactive architecture diagrams on landing pages

## When NOT to Use
- Simple decorative animations with no semantic meaning
- Mobile-first layouts where SVG paths may not scale well
- Performance-critical pages with many simultaneous beams (>10)

## Pairs Well With
- `spotlight-card` - Cards as endpoints with beams connecting them
- `particles` - Background particle field behind beam diagrams
- `gradient-text` - Gradient headings above integration sections
- `animated-content` - Stagger-reveal each node before beams animate in

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| containerRef | RefObject | required | Ref to the parent container element |
| fromRef | RefObject | required | Ref to the starting element |
| toRef | RefObject | required | Ref to the ending element |
| curvature | number | 0 | Beam path curve intensity |
| reverse | boolean | false | Reverse animation direction |
| duration | number | 5 | Animation loop duration in seconds |
| delay | number | 0 | Start delay in seconds |
| pathColor | string | "gray" | Color of the beam path line |
| pathWidth | number | 2 | Width of the beam path stroke |
| pathOpacity | number | 0.2 | Opacity of the static path |
| gradientStartColor | string | "#ffaa40" | Beam gradient start color |
| gradientStopColor | string | "#9c40ff" | Beam gradient end color |
| startXOffset | number | 0 | X offset from start element |
| startYOffset | number | 0 | Y offset from start element |
| endXOffset | number | 0 | X offset from end element |
| endYOffset | number | 0 | Y offset from end element |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/animated-beam"
```

## Usage Example
```jsx
import { AnimatedBeam } from "@/components/magicui/animated-beam";
import { useRef } from "react";

export function IntegrationsSection() {
  const containerRef = useRef(null);
  const ghlRef = useRef(null);
  const lyfeworkRef = useRef(null);
  const stripeRef = useRef(null);

  return (
    <section className="relative py-24 bg-[#0a0a0a]">
      <h2 className="text-center font-manrope font-800 text-4xl text-white mb-16">
        Seamless <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Integrations</span>
      </h2>
      <div ref={containerRef} className="relative mx-auto max-w-3xl flex items-center justify-between px-8">
        <div ref={ghlRef} className="lyf-glass rounded-[12px] p-4 z-10">
          <span className="font-manrope font-700 text-white">GoHighLevel</span>
        </div>
        <div ref={lyfeworkRef} className="lyf-glass rounded-[12px] p-4 z-10">
          <span className="font-manrope font-700 text-white">Lyfework</span>
        </div>
        <div ref={stripeRef} className="lyf-glass rounded-[12px] p-4 z-10">
          <span className="font-manrope font-700 text-white">Stripe</span>
        </div>
        <AnimatedBeam containerRef={containerRef} fromRef={ghlRef} toRef={lyfeworkRef} gradientStartColor="#ff642a" gradientStopColor="#ff0301" />
        <AnimatedBeam containerRef={containerRef} fromRef={lyfeworkRef} toRef={stripeRef} gradientStartColor="#ff642a" gradientStopColor="#ff0301" />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `gradientStartColor="#ff642a"` and `gradientStopColor="#ff0301"` to match the Lyfework brand gradient
- Endpoint cards should use `lyf-glass` class with `rounded-[12px]` for consistent styling
- Use Manrope font-700 or font-800 for node labels
- Works well on `#0a0a0a` dark backgrounds where the beam glow is most visible
- GHL compatible — pure SVG/CSS, no Web Components or Shadow DOM conflicts

## Performance Notes
- SVG path calculation runs once on mount, minimal re-renders
- Each beam uses a single `<linearGradient>` animation — lightweight
- Use `delay` to stagger multiple beams instead of rendering all at once
- Container ref must be positioned (`relative` or `absolute`) for correct path math
- Resize observer recalculates paths — avoid rapid container resizing
