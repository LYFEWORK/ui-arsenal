---
name: magic-bento
source: ReactBits
source_url: https://reactbits.dev/components/magic-bento
category: components
tags: bento, grid, layout, animated, hover, feature, showcase
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# MagicBento

> An animated bento grid layout with interactive hover effects. Each cell in the grid can expand, reveal hidden content, or play animations on hover. Inspired by Apple's bento-style feature showcases. Creates visually rich, information-dense sections.

## When to Use

- Feature showcase sections on SaaS or agency landing pages
- Product capability overviews with mixed content (text, images, stats)
- Dashboard overview panels with varied-size info cards
- "What we do" or "How it works" sections with asymmetric grid layouts
- Portfolio or case study grids with hero items and supporting thumbnails

## When NOT to Use

- Simple feature lists where a uniform grid is cleaner
- Mobile-only designs (bento grids collapse to single column and lose their magic)
- Content-light sections that don't have enough to fill varied grid sizes
- Text-heavy layouts where asymmetric sizing creates awkward reading flow

## Pairs Well With

- `spotlight-card` - Add spotlight hover to individual bento cells
- `count-up` - Animated stats inside bento stat cells
- `gradient-text` - Gradient headings in hero bento cells
- `animated-content` - Scroll-reveal the entire bento grid

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Grid cell components |
| columns | number | 4 | Number of grid columns |
| gap | number | 6 | Gap between cells in Tailwind spacing units |
| animated | boolean | true | Enable hover animations on cells |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MagicBento-TS-TW
```

## Usage Example

```jsx
import MagicBento from '@/components/ui/MagicBento';
import CountUp from '@/components/ui/CountUp';

function FeaturesSection() {
  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        Everything You Need to Scale
      </h2>
      <MagicBento columns={4} gap={6} className="max-w-6xl mx-auto">
        {/* Hero cell - spans 2 cols, 2 rows */}
        <div className="col-span-2 row-span-2 lyf-glass rounded-xl p-8 flex flex-col justify-end">
          <img src="/features/crm-preview.png" alt="CRM" className="rounded-lg mb-6" />
          <h3 className="text-2xl font-bold text-white font-[Manrope]">Smart CRM</h3>
          <p className="text-gray-400 mt-2">Pipelines, automations, and AI-powered lead scoring in one place.</p>
        </div>

        {/* Stat cell */}
        <div className="lyf-glass rounded-xl p-6 flex flex-col items-center justify-center">
          <CountUp end={340} suffix="%" className="text-4xl font-extrabold text-[#ff642a]" />
          <p className="text-sm text-gray-400 mt-2">Avg. Booking Increase</p>
        </div>

        {/* Feature cell */}
        <div className="lyf-glass rounded-xl p-6">
          <span className="text-2xl">🤖</span>
          <h3 className="mt-3 text-lg font-bold text-white font-[Manrope]">AI Chatbot</h3>
          <p className="text-sm text-gray-400 mt-1">24/7 lead qualification on autopilot.</p>
        </div>

        {/* Wide cell - spans 2 cols */}
        <div className="col-span-2 lyf-glass rounded-xl p-6 flex items-center gap-6">
          <img src="/features/analytics.png" alt="Analytics" className="w-32 rounded-lg" />
          <div>
            <h3 className="text-lg font-bold text-white font-[Manrope]">Real-Time Analytics</h3>
            <p className="text-sm text-gray-400 mt-1">Track every metric that matters. Attribution, ROI, velocity.</p>
          </div>
        </div>
      </MagicBento>
    </section>
  );
}
```

## Lyfework Customization Notes

- All bento cells: `lyf-glass` with `rounded-xl` (12px) for Lyfework glass standard
- Hero cell accent: `bg-gradient-to-br from-[#ff642a]/10 to-[#ff0301]/5` subtle gradient bg
- Font: `Manrope` 700 for cell headings, 400 for descriptions
- Stat cells: use `CountUp` component with `text-[#ff642a]` for brand color numbers
- GHL compatible when built as a static React section embedded via code widget
- For client builds, adjust column spans to match content density

## Performance Notes

- CSS Grid handles the layout; Framer Motion only handles hover animations
- Hover animations use GPU-accelerated `scale` and `translateY` transforms
- Images inside cells should use `loading="lazy"` and responsive `srcset`
- Keep total cell count under 8 for optimal first-viewport performance
- On mobile, grid collapses to single column; hover effects are disabled via media query
