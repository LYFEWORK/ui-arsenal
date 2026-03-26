---
name: stripe-bg-guides
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/stripe-bg-guides
category: backgrounds
tags: stripe, guides, lines, vertical, background, minimal, layout
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# StripeBgGuides

> Stripe-style vertical guide lines background for clean, structured page layouts.

## When to Use
- SaaS landing pages emulating Stripe's polished design language
- Pricing or feature comparison sections needing visual structure
- Developer documentation pages with grid-aligned content
- Any dark-themed page needing subtle structural guides
- GHL funnel pages requiring lightweight background structure

## When NOT to Use
- Creative or organic designs where rigid lines feel constraining
- Image-heavy pages where guide lines add visual clutter
- Very narrow mobile layouts where vertical lines crowd the space

## Pairs Well With
- `animated-content` - Content fading in along guide lines creates alignment emphasis
- `spotlight-card` - Cards aligned to guide columns with spotlight effects
- `number-ticker` - Stats aligned to guide columns for structured data display
- `marquee` - Scrolling marquee contrasting with static vertical guides

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| columns | number | 4 | Number of vertical guide lines |
| color | string | '#ffffff' | Guide line color |
| opacity | number | 0.06 | Line opacity |
| width | number | 1 | Line width in pixels |
| maxWidth | string | '1280px' | Max width of guide container |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/stripe-bg-guides"
```

## Usage Example
```jsx
import { StripeBgGuides } from "@/components/ui/stripe-bg-guides";

export function PricingSection() {
  return (
    <section className="relative bg-[#0a0a0a] py-24">
      <StripeBgGuides
        columns={4}
        color="#ffffff"
        opacity={0.05}
        maxWidth="1200px"
        className="absolute inset-0"
      />
      <div className="relative z-10 max-w-5xl mx-auto px-6">
        <h2 className="font-manrope font-800 text-4xl text-white text-center">
          Simple, Transparent Pricing
        </h2>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-8 mt-16">
          {/* Pricing cards aligned to guide columns */}
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use white lines at 0.04-0.06 opacity on #0a0a0a for barely-visible structure
- Set columns to match your content grid (3 for pricing, 4 for features)
- maxWidth should match your content container (typically 1200-1280px)
- Perfect for GHL pages -- pure CSS with zero JS
- Align card widths with guide spacing for satisfying visual alignment

## Performance Notes
- Pure CSS implementation using repeating-linear-gradient
- Zero JavaScript, zero repaints, zero layout shifts
- Sub-kilobyte addition to CSS bundle
- SSR-safe with no hydration requirements
- Works in every browser including legacy
