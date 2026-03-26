---
name: card-hover-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/card-hover-effect
category: components
tags: card, hover, glow, gradient, interactive, grid
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# CardHoverEffect

> Card grid with gradient glow hover animation that highlights the active card while dimming others.

## When to Use
- Service offering grids on agency or clinic landing pages
- Feature comparison cards on SaaS pricing pages
- Portfolio project grids with interactive hover states
- Team member cards with highlight-on-focus behavior
- Resource or blog post card layouts

## When NOT to Use
- For single standalone cards without a grid context
- When cards need complex interactive states beyond hover
- On extremely dense grids (8+ columns) where glow overlaps

## Pairs Well With
- `animated-content` - Stagger card grid entrance animations
- `gradient-text` - Apply gradient to card titles on hover
- `blur-text` - Animate card headings into view
- `spotlight-card` - Combine glow effects for layered depth

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | array | - | Array of { title, description, link } objects |
| className | string | - | Additional classes for the grid container |
| hoverClassName | string | - | Classes for the hover glow effect |

## Installation
```bash
npx aceternity-ui@latest add card-hover-effect
```

## Usage Example
```jsx
import { HoverEffect } from "@/components/ui/card-hover-effect";

const services = [
  { title: "Web Design", description: "Custom clinic and SaaS websites built with Next.js and Tailwind.", link: "/services/web-design" },
  { title: "AI Integration", description: "Chatbots, scheduling AI, and predictive analytics for your practice.", link: "/services/ai" },
  { title: "GHL Automation", description: "Full GoHighLevel CRM setup with automated patient workflows.", link: "/services/ghl" },
  { title: "Brand Identity", description: "Logo, typography, and visual systems that reflect your mission.", link: "/services/branding" },
  { title: "SEO & Growth", description: "Data-driven SEO strategies tailored for healthcare and SaaS.", link: "/services/seo" },
  { title: "Maintenance", description: "Ongoing support, updates, and performance monitoring.", link: "/services/maintenance" },
];

export function ServicesGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6 max-w-6xl mx-auto">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-12">
        Our <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Services</span>
      </h2>
      <HoverEffect items={services} />
    </section>
  );
}
```

## Lyfework Customization Notes
- Override default hover glow color to match Lyfework gradient `from-[#ff642a]/20 to-[#ff0301]/20`
- Cards render on `#0a0a0a` background with `border border-white/10` styling
- Apply `rounded-[12px]` to card containers, Manrope 700 for titles, 400 for descriptions
- Glow effect uses absolute-positioned gradient overlay; ensure parent has `overflow: hidden`
- Works well inside GHL funnels when wrapped in a constrained max-width container

## Performance Notes
- Hover glow uses CSS gradient with opacity transition (GPU-composited)
- Framer Motion `layoutId` animation handles smooth glow movement between cards
- Grid renders all cards on mount; use virtualization for 20+ card grids
- Animation frame rate stays at 60fps with up to 12 cards visible
- No additional DOM elements created during hover, just style changes
