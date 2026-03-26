---
name: laser-flow
source: ReactBits
source_url: https://reactbits.dev/animations/laser-flow
category: animations
tags: laser, beam, flow, border, animated, neon, energy
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# LaserFlow

> An animated laser beam that flows along paths or borders of elements, creating a high-energy neon trail effect ideal for futuristic and tech-forward designs.

## When to Use

- Hero section borders where a beam of light traces the card edge
- Section dividers that feel alive instead of static horizontal rules
- Tech product showcases where a laser outlines the product frame
- Gaming or esports themed pages where energy and neon are on-brand
- Accent animations on feature comparison tables to highlight the winning column

## When NOT to Use

- Wellness, healthcare, or calm brand aesthetics (too aggressive)
- Pages with many bordered elements -- laser on every card is overwhelming
- Print-style layouts where neon effects conflict with the design language
- Content-first blogs or documentation pages

## Pairs Well With

- `electric-border` - Laser traces the path while electric arcs crackle alongside
- `gradient-text` - Neon laser border framing a gradient headline creates cohesion
- `aurora` - Laser beams over aurora backgrounds for a full sci-fi atmosphere
- `click-spark` - Laser border + spark on interaction for a high-energy UI

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element to trace with the laser |
| color | string | "#ff642a" | Laser beam color |
| width | number | 2 | Beam width in pixels |
| speed | number | 3 | Time in seconds for one full loop |
| glowRadius | number | 8 | Glow spread radius in pixels |
| path | "border" \| "custom" | "border" | Trace the element border or a custom SVG path |
| customPath | string | "" | SVG path data when path is "custom" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LaserFlow-TS-TW
```

## Usage Example

```jsx
import LaserFlow from '@/components/ui/LaserFlow';

function TechProductShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-8 font-[Manrope]">
      <div className="max-w-3xl mx-auto text-center">
        <h2 className="text-4xl font-bold text-white mb-12">
          The{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Future
          </span>{' '}
          of Web Design
        </h2>
        <LaserFlow color="#ff642a" speed={4} glowRadius={10} width={2}>
          <div className="lyf-glass p-12 rounded-[16px]">
            <img
              src="/platform-preview.png"
              alt="Platform preview"
              className="rounded-[8px] w-full"
            />
            <p className="mt-8 text-gray-400 text-lg">
              Ship pixel-perfect sites faster than ever.
            </p>
            <button className="mt-6 px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
              Start Building
            </button>
          </div>
        </LaserFlow>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use brand color `#ff642a` as the default laser color for warm-toned flows on `#0a0a0a` backgrounds.
- For a cooler variant, try `#3b82f6` (blue) on tech-focused builds, but `#ff642a` stays on-brand.
- Set `glowRadius` to 6-10px. Higher values create a softer neon; lower values create a sharper beam.
- Rounded corners on the traced element should use `rounded-[16px]` for feature cards so the laser follows the curve smoothly.
- GHL compatibility: the SVG-based laser path renders correctly but verify `overflow: visible` on the wrapper.
- Combine with Manrope bold for any text inside the laser-framed card to keep brand consistency.

## Performance Notes

- CSS animation with `stroke-dashoffset` on an SVG path -- no JS animation loop
- The glow uses `filter: drop-shadow()` which creates a compositing layer
- Limit to 1-2 instances per page to avoid stacking GPU layers
- Bundle size: ~2.5KB (SVG path calculation + CSS keyframes)
- On Safari, `drop-shadow` on SVG can flicker; test and consider fallback to `box-shadow`
