---
name: 3d-marquee
source: Aceternity UI
source_url: https://ui.aceternity.com/components/3d-marquee
category: animations
tags: marquee, 3d, perspective, scroll, depth, carousel, infinite
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# 3dMarquee

> 3D perspective scrolling marquee with depth effect, creating an infinite scroll of items with a dramatic vanishing point.

## When to Use
- Client logo showcases with premium 3D depth
- Product image carousels with cinematic perspective
- Technology stack or tool displays with visual flair
- Partner or integration logo strips with dimensional effect
- Portfolio thumbnail strips with depth-enhanced scrolling

## When NOT to Use
- When a flat 2D marquee is sufficient for the content
- On performance-constrained pages where 3D transforms are expensive
- For text-only marquees where depth adds no readability benefit

## Pairs Well With
- `marquee` - Use 2D marquee for standard sections, 3D for hero sections
- `aurora` - Aurora background behind the 3D marquee
- `gradient-text` - Section heading with gradient above the marquee
- `animated-content` - Fade in the marquee section on scroll

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Marquee items |
| className | string | - | Classes for the marquee container |
| reverse | boolean | false | Reverse scroll direction |
| speed | number | 30 | Scroll speed in pixels per second |
| perspective | number | 1000 | CSS perspective value for 3D depth |

## Installation
```bash
npx aceternity-ui@latest add 3d-marquee
```

## Usage Example
```jsx
import { ThreeDMarquee } from "@/components/ui/3d-marquee";

const logos = [
  "/logos/nextjs.svg", "/logos/react.svg", "/logos/tailwind.svg",
  "/logos/ghl.svg", "/logos/vercel.svg", "/logos/figma.svg",
  "/logos/stripe.svg", "/logos/openai.svg",
];

export function TechStack() {
  return (
    <section className="bg-[#0a0a0a] py-24 overflow-hidden">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-16">
        Built With the <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Best</span>
      </h2>
      <ThreeDMarquee>
        {logos.map((logo) => (
          <img key={logo} src={logo} alt="" className="h-12 w-auto opacity-60 hover:opacity-100 transition-opacity mx-8" />
        ))}
      </ThreeDMarquee>
    </section>
  );
}
```

## Lyfework Customization Notes
- Logo images should be SVG or transparent PNG for clean rendering on #0a0a0a
- Apply `opacity-60 hover:opacity-100` for subtle interactive feedback
- Section heading uses Manrope 800 with brand gradient accent
- Container needs `overflow: hidden` to prevent 3D perspective overflow
- GHL compatible; perspective transform works within iframe constraints

## Performance Notes
- 3D perspective uses CSS `transform: perspective()`, GPU-composited
- Infinite scroll duplicates items in DOM; limit to 8-12 items for efficiency
- CSS animation with `translateX` is more performant than JS-driven scrolling
- Logo images should be small (SVG or <10KB each) for fast loading
- `will-change: transform` applied to scrolling container for smooth rendering
