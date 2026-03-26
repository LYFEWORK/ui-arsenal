---
name: magic-card
source: Magic UI
source_url: https://magicui.design/docs/components/magic-card
category: components
tags: card, gradient, cursor, glow, interactive
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# MagicCard

> Card with a radial gradient that follows the cursor on hover, creating a spotlight/glow effect.

## When to Use
- Feature cards on SaaS landing pages
- Pricing plan cards with interactive hover states
- Service offering cards on clinic/agency sites
- Team member or testimonial cards
- Dashboard widget cards in dark-themed UIs

## When NOT to Use
- Light-themed designs where the gradient effect is subtle
- Dense data tables or list views
- Mobile-only layouts where hover is unavailable
- When `spotlight-card` from the arsenal already covers the need

## Pairs Well With
- `animated-content` - Stagger-reveal multiple magic cards on scroll
- `gradient-text` - Gradient headings inside the card
- `particles` - Particle background behind a grid of magic cards
- `aurora` - Aurora effect in the section background

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| className | string | "" | Additional CSS classes |
| gradientSize | number | 200 | Size of the radial gradient in pixels |
| gradientColor | string | "#262626" | Color of the cursor-following gradient |
| gradientOpacity | number | 0.8 | Opacity of the gradient overlay |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/magic-card"
```

## Usage Example
```jsx
import { MagicCard } from "@/components/magicui/magic-card";

const features = [
  { title: "Smart Scheduling", desc: "AI-powered appointment booking that reduces no-shows by 40%." },
  { title: "Patient Portal", desc: "Self-service portal for intake forms, records, and messaging." },
  { title: "Analytics", desc: "Real-time dashboards tracking revenue, retention, and growth." },
];

export function FeaturesGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-4xl text-white mb-16">
        Everything your clinic{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">needs</span>
      </h2>
      <div className="mx-auto max-w-5xl grid grid-cols-1 md:grid-cols-3 gap-6 px-6">
        {features.map((f) => (
          <MagicCard key={f.title} className="rounded-[12px] p-8 border border-white/10" gradientColor="#ff642a20">
            <h3 className="font-manrope font-700 text-xl text-white mb-3">{f.title}</h3>
            <p className="font-manrope font-400 text-white/60">{f.desc}</p>
          </MagicCard>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `gradientColor` to `#ff642a20` (low-opacity brand orange) for subtle brand glow
- Apply `rounded-[12px] border border-white/10` for card styling conventions
- Use Manrope font-700 for card titles, font-400 for body text
- Dark backgrounds (`#0a0a0a`) make the gradient glow most visible
- GHL compatible — uses mouse events and CSS background, no Web Components

## Performance Notes
- Cursor tracking uses Framer Motion's `useMotionValue` — optimized, no re-renders
- Gradient is applied via CSS `radial-gradient` — GPU composited
- Multiple cards in a grid each track independently — no cross-card interference
- Mobile falls back to static appearance (no hover) — no wasted computation
- No layout shift — gradient is layered as a pseudo-element
