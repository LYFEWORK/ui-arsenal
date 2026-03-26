---
name: luxe-card
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-card
category: components
tags: card, hover, glow, lift, glass, container
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LuxeCard

> Elegant card component with animated hover glow effect, subtle lift transform, and smooth border illumination.

## When to Use
- Feature grid sections showcasing 3-6 capabilities or benefits
- Pricing plan cards that need to feel premium and interactive
- Portfolio project thumbnails with hover-to-reveal details
- Testimonial cards where the glow effect adds emotional warmth
- Service offering cards on clinic or agency landing pages

## When NOT to Use
- Dense data displays like tables or dashboards where glow adds noise
- Blog post listing cards at small sizes where the effect is invisible
- Print-optimized layouts where hover states don't translate
- Performance-critical pages with 20+ cards visible simultaneously

## Pairs Well With
- `spotlight-card` - use Luxe card for content areas and spotlight card for featured items
- `gradient-text` - gradient heading inside the card ties into the glow accent color
- `shimmer-button` - shimmer CTA button at the card's footer for cohesive premium feel
- `animated-content` - animate card content in on scroll for a staged reveal

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Card content |
| className | string | — | Additional CSS classes |
| glowColor | string | "rgba(255,100,42,0.15)" | Color of the hover glow |
| liftAmount | number | 8 | Pixels to lift on hover |
| borderGlow | boolean | true | Enable border illumination on hover |
| as | ElementType | "div" | Render as different element |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-card"
```

## Usage Example
```jsx
import { LuxeCard } from "@/components/ui/luxe-card";

export function FeatureGrid() {
  const features = [
    { title: "Smart Scheduling", desc: "AI-powered appointment booking that syncs with your calendar" },
    { title: "Patient Portal", desc: "Secure portal for records, billing, and communication" },
    { title: "Review Boost", desc: "Automated review requests sent at the perfect moment" },
  ];

  return (
    <section className="py-20 bg-[#0a0a0a]">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-6xl mx-auto px-6">
        {features.map((f) => (
          <LuxeCard
            key={f.title}
            className="lyf-glass rounded-[12px] p-8"
            glowColor="rgba(255,100,42,0.12)"
          >
            <h3 className="font-manrope font-800 text-xl text-white mb-3">{f.title}</h3>
            <p className="font-manrope font-400 text-gray-400">{f.desc}</p>
          </LuxeCard>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `glowColor` to `"rgba(255,100,42,0.12)"` to match the Lyfework orange brand accent
- Apply `lyf-glass rounded-[12px]` for brand card styling
- Use `#0a0a0a` section background to maximize glow visibility
- Card headings: `font-manrope font-800`, body text: `font-manrope font-400`
- GHL compatible — hover glow uses box-shadow and transform, no layout impact
- Combine with `border border-white/5` for subtle resting-state definition

## Performance Notes
- Hover glow uses box-shadow transition — GPU-composited, no repaints
- Lift effect uses `translateY` transform — no layout recalculation
- Framer Motion handles enter/exit smoothly with spring config
- Border glow is a pseudo-element — doesn't affect content layout
- Safe for grids up to 12 cards without noticeable performance impact
