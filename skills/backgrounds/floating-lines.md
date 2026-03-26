---
name: floating-lines
source: ReactBits
source_url: https://reactbits.dev/backgrounds/floating-lines
category: backgrounds
tags: background, lines, floating, drift, ambient, elegant, minimal
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FloatingLines

> Thin animated lines that drift lazily across the background, creating an elegant, ambient sense of motion. Perfect for adding life to sections without overwhelming content.

## When to Use

- SaaS landing page hero or feature sections for subtle ambient motion
- Behind testimonial carousels to add gentle visual interest
- Professional service page backgrounds (legal, consulting, finance)
- Portfolio section dividers where you want motion without chaos
- Dashboard or app preview sections for a polished tech feel

## When NOT to Use

- Sections with heavy line-based design elements (visual confusion)
- Behind wireframe or schematic illustrations (competing line patterns)
- Very small sections where the lines cannot fully drift
- Backgrounds that already have particle or line-based effects

## Pairs Well With

- `animated-content` - Content fading in over the drifting lines feels seamless
- `spotlight-card` - Cards over floating lines create a sophisticated layered look
- `blur-text` - Headline reveal over the gentle lines adds polish
- `gradient-text` - Gradient text over white floating lines creates elegant contrast

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| lineCount | number | 8 | Number of floating lines |
| lineColor | string | "rgba(255,255,255,0.1)" | Color of the lines |
| lineWidth | number | 1 | Thickness of each line in pixels |
| speed | number | 0.5 | Drift speed of the lines |
| angle | number | 45 | Angle of line drift in degrees |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FloatingLines-TS-TW
```

## Usage Example

```jsx
import FloatingLines from '@/components/ui/FloatingLines';
import AnimatedContent from '@/components/ui/AnimatedContent';

function TestimonialSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <FloatingLines
          lineCount={6}
          lineColor="rgba(255,100,42,0.08)"
          lineWidth={1}
          speed={0.3}
          angle={30}
        />
      </div>

      <div className="relative z-10 max-w-4xl mx-auto px-8 text-center">
        <AnimatedContent direction="up" delay={200}>
          <blockquote className="text-2xl text-white font-[Manrope] italic">
            "Lyfework didn't just build our site. They built our entire digital presence."
          </blockquote>
          <p className="mt-6 text-gray-400 font-[Manrope]">
            -- Dr. Sarah Chen, Apex Dental Group
          </p>
        </AnimatedContent>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework line color: `rgba(255,100,42,0.08)` for a barely-there brand warmth
- For clinic clients: `rgba(255,255,255,0.06)` keeps it neutral and professional
- `lineCount` of 5-8 is the sweet spot. More than 12 starts looking like a cage.
- `speed` of 0.2-0.4 feels premium. Above 0.7 feels rushed.
- GHL: replicate with CSS keyframe animations on absolute-positioned `div` elements
- The 30-45 degree angle range looks most natural and elegant

## Performance Notes

- Lightweight CSS transform animations on simple DOM elements
- No canvas or WebGL overhead
- Each line is a single DOM element with a CSS animation
- Safe for mobile and low-powered devices at standard line counts
- SSR-compatible, lines render in starting positions and animate on client
