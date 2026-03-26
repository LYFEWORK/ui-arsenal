---
name: direction-aware-hover
source: Aceternity UI
source_url: https://ui.aceternity.com/components/direction-aware-hover
category: components
tags: hover, direction, overlay, card, interactive, cursor, animation
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# DirectionAwareHover

> Card with an overlay that enters from the direction the cursor approaches, creating a natural reveal animation.

## When to Use
- Portfolio or gallery grids where hover reveals project details
- Team member photo cards with bio overlay
- Product image grids with detail overlays
- Case study image cards with result metrics overlay
- Any image-centric grid where hover context is needed

## When NOT to Use
- On mobile-first layouts where hover is not available
- For cards that are primarily text-based without images
- When overlay content is too complex for a hover state

## Pairs Well With
- `focus-cards` - Combine direction-aware hover with focus expansion
- `animated-content` - Stagger grid entrance before hover becomes active
- `gradient-text` - Gradient overlay text for project titles
- `marquee` - Scrolling portfolio strip with direction-aware hover on items

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| imageUrl | string | - | URL of the card background image |
| children | ReactNode | - | Overlay content shown on hover |
| childrenClassName | string | - | Classes for the overlay content wrapper |
| imageClassName | string | - | Classes for the background image |
| className | string | - | Classes for the card container |

## Installation
```bash
npx aceternity-ui@latest add direction-aware-hover
```

## Usage Example
```jsx
import { DirectionAwareHover } from "@/components/ui/direction-aware-hover";

const projects = [
  { image: "/portfolio/clinic-site.webp", title: "Wellness Clinic", desc: "Full rebrand + Next.js site" },
  { image: "/portfolio/saas-dashboard.webp", title: "DataFlow SaaS", desc: "Dashboard UI + GHL integration" },
  { image: "/portfolio/ai-landing.webp", title: "AI Product Launch", desc: "Landing page + demo showcase" },
];

export function PortfolioGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-16">
        Recent <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Work</span>
      </h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-6xl mx-auto">
        {projects.map((p) => (
          <DirectionAwareHover key={p.title} imageUrl={p.image} className="rounded-[12px] h-[400px]">
            <div className="space-y-2">
              <h3 className="font-[Manrope] font-700 text-xl text-white">{p.title}</h3>
              <p className="font-[Manrope] font-400 text-neutral-300 text-sm">{p.desc}</p>
            </div>
          </DirectionAwareHover>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set card `rounded-[12px]` for consistent border radius across the design system
- Overlay background should use `bg-black/60 backdrop-blur-sm` for the Lyfework glass feel
- Use Manrope 700 for project titles in overlays, 400 for descriptions
- #0a0a0a section background ensures the cards pop visually
- Ensure images are optimized WebP; direction calculation uses element bounds, not image size

## Performance Notes
- Direction detection uses simple mouse enter coordinate math, negligible CPU cost
- Overlay animation uses framer-motion spring transitions, GPU-composited
- Images should use `object-cover` to maintain aspect ratio during hover transitions
- Works smoothly with up to 12 cards in a grid layout
- Consider `loading="lazy"` for images below the fold
