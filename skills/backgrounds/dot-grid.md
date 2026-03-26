---
name: dot-grid
source: ReactBits
source_url: https://reactbits.dev/backgrounds/dot-grid
category: backgrounds
tags: background, dots, grid, pattern, minimal, subtle, geometric
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# DotGrid

> An animated dot grid pattern background that creates a clean, minimal geometric texture. The go-to subtle background for SaaS sections, dashboards, and professional layouts.

## When to Use

- SaaS product landing page backgrounds for feature sections
- Behind dashboard previews or product screenshots
- Professional service pages that need subtle texture without distraction
- FAQ or content-heavy sections where flat color feels too empty
- Clinic/medical site section backgrounds for a clean, clinical feel

## When NOT to Use

- Hero sections that need visual impact (too subtle as a primary hero)
- Over dark images where the dots will be invisible
- Behind very small components or cards (pattern gets lost)

## Pairs Well With

- `spotlight-card` - Dot grid behind spotlight cards creates a polished SaaS layout
- `animated-content` - Content appearing over the dot grid feels clean and intentional
- `count-up` - Animated metrics over a dot grid background screams SaaS dashboard
- `gradient-text` - Gradient headings pop cleanly over the subtle dot pattern

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| dotSize | number | 2 | Radius of each dot in pixels |
| gap | number | 24 | Spacing between dots |
| dotColor | string | "rgba(255,255,255,0.15)" | Color of the dots |
| animated | boolean | false | Whether dots pulse or shift subtly |
| fadeEdges | boolean | true | Whether dots fade out near the edges |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/DotGrid-TS-TW
```

## Usage Example

```jsx
import DotGrid from '@/components/ui/DotGrid';
import CountUp from '@/components/ui/CountUp';

function MetricsSection() {
  return (
    <section className="relative py-24 overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <DotGrid
          dotSize={1.5}
          gap={28}
          dotColor="rgba(255,100,42,0.12)"
          fadeEdges={true}
        />
      </div>

      <div className="relative z-10 max-w-6xl mx-auto px-8">
        <h2 className="text-3xl font-bold text-white text-center font-[Manrope]">
          Results That Speak
        </h2>
        <div className="mt-12 grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
          <div>
            <CountUp end={147} suffix="%" className="text-5xl font-bold text-white" />
            <p className="mt-2 text-gray-400">Average ROI Increase</p>
          </div>
          <div>
            <CountUp end={2400} prefix="+" className="text-5xl font-bold text-white" />
            <p className="mt-2 text-gray-400">Leads Generated</p>
          </div>
          <div>
            <CountUp end={98} suffix="%" className="text-5xl font-bold text-white" />
            <p className="mt-2 text-gray-400">Client Retention</p>
          </div>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework dot color: `rgba(255,100,42,0.12)` for a warm, barely-there brand tint
- For clinic clients: use `rgba(255,255,255,0.08)` for a neutral, clinical feel
- `gap` of 24-32 works for most sections. Tighter gaps (16-20) for dashboard-style layouts.
- `fadeEdges` should almost always be `true` to prevent harsh pattern cutoffs
- GHL: can be replicated with a CSS `radial-gradient` repeating pattern in a custom code block
- Pairs perfectly with `lyf-glass` cards layered on top for the standard Lyfework SaaS look

## Performance Notes

- Pure CSS implementation using `radial-gradient` and `background-repeat`
- Zero JavaScript overhead in the static variant
- Animated variant uses CSS keyframes, extremely lightweight
- Safe for all devices and browsers
- SSR-compatible with no hydration cost
