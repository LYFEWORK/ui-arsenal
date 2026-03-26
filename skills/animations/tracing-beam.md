---
name: tracing-beam
source: Aceternity UI
source_url: https://ui.aceternity.com/components/tracing-beam
category: animations
tags: beam, trace, scroll, svg, progress, line, content, reading
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# TracingBeam

> SVG beam that traces scroll progress along the side of content, creating a visual reading progress indicator with glow effects.

## When to Use
- Long-form blog posts or articles with scroll progress indication
- Case study pages with side-tracked reading progress
- Documentation or guide pages with visual section tracking
- Process or workflow explanations with linear progress
- Any content-heavy page where scroll position context helps

## When NOT to Use
- On very short pages where scroll progress is unnecessary
- When a top progress bar already provides scroll indication
- For pages with complex multi-column layouts where side beam is confusing

## Pairs Well With
- `timeline` - Tracing beam alongside a timeline component
- `animated-content` - Content sections animate as beam reaches them
- `gradient-text` - Section headers with gradient styling
- `blur-text` - Text entrance triggered by beam progress

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content the beam traces alongside |
| className | string | - | Classes for the container |

## Installation
```bash
npx aceternity-ui@latest add tracing-beam
```

## Usage Example
```jsx
import { TracingBeam } from "@/components/ui/tracing-beam";

export function CaseStudy() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <TracingBeam className="max-w-3xl mx-auto px-6">
        <article>
          <h1 className="font-[Manrope] font-800 text-4xl text-white mb-4">
            How We Increased Patient Bookings by{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">300%</span>
          </h1>
          <p className="font-[Manrope] font-400 text-neutral-400 text-lg leading-relaxed mb-8">
            A deep dive into our clinic website redesign for Wellness First, including GHL automation and AI chatbot integration.
          </p>
          <h2 className="font-[Manrope] font-700 text-2xl text-white mb-3">The Challenge</h2>
          <p className="font-[Manrope] font-400 text-neutral-400 leading-relaxed mb-8">
            Wellness First was losing 60% of potential patients to competitors with modern websites...
          </p>
          <h2 className="font-[Manrope] font-700 text-2xl text-white mb-3">Our Approach</h2>
          <p className="font-[Manrope] font-400 text-neutral-400 leading-relaxed">
            We rebuilt their entire digital presence with a Next.js site, GHL CRM integration, and AI-powered scheduling...
          </p>
        </article>
      </TracingBeam>
    </section>
  );
}
```

## Lyfework Customization Notes
- Beam gradient can be set to `from-[#ff642a] to-[#ff0301]` for brand-colored progress
- Content uses Manrope 800 for h1, 700 for h2, 400 for body text
- #0a0a0a background with max-w-3xl content container for optimal reading width
- Beam glow dot color matches the primary brand orange #ff642a
- Works within GHL pages; beam SVG is positioned relative to content container

## Performance Notes
- Scroll tracking uses `useScroll` with a single `useTransform`, highly efficient
- SVG beam uses `stroke-dashoffset` animation, GPU-composited
- Beam glow dot uses CSS box-shadow, lightweight rendering
- Content inside TracingBeam renders normally with no performance penalty
- Works smoothly with pages of any length; overhead is constant regardless of content size
