---
name: focus-cards
source: Aceternity UI
source_url: https://ui.aceternity.com/components/focus-cards
category: components
tags: cards, focus, expand, hover, grid, gallery, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# FocusCards

> Cards that expand and come into focus when hovered, while dimming the rest of the grid for visual emphasis.

## When to Use
- Portfolio project galleries where one project takes spotlight on hover
- Service offering grids with focus-on-detail interaction
- Team member showcase with expanded bio on hover
- Product category displays on e-commerce or SaaS pages
- Image-forward content grids for clinic or wellness sites

## When NOT to Use
- When all cards need equal visibility at all times
- On text-heavy grids where expansion adds no visual value
- For mobile-primary audiences without hover capability

## Pairs Well With
- `blur-text` - Animate titles as cards come into focus
- `animated-content` - Stagger card entrance before focus interactions
- `gradient-text` - Gradient headings on the focused card
- `spotlight-card` - Add spotlight glow to the focused card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| cards | array | - | Array of { title, src } card objects |
| className | string | - | Classes for the grid container |

## Installation
```bash
npx aceternity-ui@latest add focus-cards
```

## Usage Example
```jsx
import { FocusCards } from "@/components/ui/focus-cards";

const services = [
  { title: "Web Design", src: "/services/web-design.webp" },
  { title: "AI Automation", src: "/services/ai-automation.webp" },
  { title: "GHL Integration", src: "/services/ghl.webp" },
  { title: "Brand Identity", src: "/services/branding.webp" },
];

export function ServiceShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-16">
        What We <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Build</span>
      </h2>
      <FocusCards cards={services} />
    </section>
  );
}
```

## Lyfework Customization Notes
- Card images should be optimized WebP at 16:9 or 4:3 ratio for consistent grid layout
- Overlay text uses Manrope 700 for titles on `bg-black/40 backdrop-blur-sm` overlay
- Section background #0a0a0a with generous padding (py-24) for breathing room
- Dim opacity on unfocused cards should be 0.4-0.6 for sufficient contrast
- GHL compatible; ensure grid container has `overflow: hidden` in iframe contexts

## Performance Notes
- Focus/dim transition uses opacity and scale transforms, GPU-accelerated
- All images load on mount; use `loading="lazy"` for below-fold grids
- Smooth at 60fps with up to 8 cards; beyond that, consider pagination
- Framer Motion `layoutId` handles smooth size transitions between states
- No additional DOM elements created during focus, just style transitions
