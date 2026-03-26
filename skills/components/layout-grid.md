---
name: layout-grid
source: Aceternity UI
source_url: https://ui.aceternity.com/components/layout-grid
category: components
tags: grid, layout, expand, click, gallery, interactive, bento
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# LayoutGrid

> Animated expanding grid layout where cards grow to reveal detailed content on click, then shrink back to grid.

## When to Use
- Portfolio project grids with expandable case study details
- Service offering bento grids with detail expansion
- Product feature showcases with click-to-expand interaction
- Image galleries with overlay detail views
- Team or client showcase grids

## When NOT to Use
- For simple card grids without expandable content
- When detail views are complex enough to warrant a separate page
- On mobile where expanded cards may not fit viewport

## Pairs Well With
- `animated-content` - Entrance animation for the grid before interaction
- `gradient-text` - Gradient headings inside expanded card detail
- `blur-text` - Text reveal animation in expanded state
- `spotlight-card` - Spotlight glow on active/expanded card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| cards | array | - | Array of card objects with content and className |
| className | string | - | Classes for the grid container |

## Installation
```bash
npx aceternity-ui@latest add layout-grid
```

## Usage Example
```jsx
import { LayoutGrid } from "@/components/ui/layout-grid";

const cards = [
  {
    id: 1,
    className: "md:col-span-2",
    thumbnail: "/portfolio/clinic-hero.webp",
    content: (
      <div>
        <h3 className="font-[Manrope] font-800 text-2xl text-white">Wellness Clinic Redesign</h3>
        <p className="font-[Manrope] font-400 text-neutral-300 mt-2">
          Full rebrand and website overhaul with GHL booking integration. 3x increase in patient bookings.
        </p>
      </div>
    ),
  },
  {
    id: 2,
    className: "col-span-1",
    thumbnail: "/portfolio/saas-app.webp",
    content: (
      <div>
        <h3 className="font-[Manrope] font-800 text-2xl text-white">SaaS Dashboard</h3>
        <p className="font-[Manrope] font-400 text-neutral-300 mt-2">
          AI-powered analytics dashboard for healthcare data visualization.
        </p>
      </div>
    ),
  },
];

export function ProjectGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-16">
        Featured <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Projects</span>
      </h2>
      <div className="max-w-6xl mx-auto">
        <LayoutGrid cards={cards} />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Card thumbnails should be high-res WebP for crisp expanded views
- Expanded content overlay uses `bg-black/70 backdrop-blur-md` for glass effect
- Manrope 800 for expanded titles, 400 for descriptions on dark overlays
- Use `rounded-[12px]` on grid cards for consistent design language
- GHL iframe requires `overflow: visible` on parent for expansion to work properly

## Performance Notes
- Layout animation uses framer-motion `layout` prop with shared layout IDs
- Only the expanded card re-renders; other cards use CSS dimming
- Images should use `object-cover` for consistent aspect ratios during transition
- Click-to-expand is more performant than hover-to-expand for grids
- Limit to 6-8 cards for smooth expand/collapse transitions
