---
name: 3d-carousel-cult
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/3d-carousel-cult
category: components
tags: carousel, 3d, perspective, depth, showcase, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# 3DCarouselCult

> 3D perspective carousel with depth, rotation, and parallax effects for immersive showcases.

## When to Use
- Portfolio project showcases with dramatic presentation
- Product image galleries with 3D perspective browsing
- Team member spotlights with rotating card presentation
- Feature showcases where 3D depth enhances understanding
- Landing page hero sections with immersive product display

## When NOT to Use
- Standard image galleries where 3D adds unnecessary complexity
- Mobile-first pages where 3D transforms are heavy
- Content that must be compared side-by-side (use flat grid)
- Accessibility-critical pages where 3D perspective confuses users

## Pairs Well With
- `spotlight-card` - Spotlight effect on the focused carousel item
- `blur-text` - Text details that blur-reveal on the active card
- `gradient-text` - Gradient titles on carousel items
- `animated-content` - Content within carousel items animating on focus

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | { content: ReactNode; key: string }[] | [] | Carousel items |
| perspective | number | 1000 | 3D perspective depth in px |
| radius | number | 400 | Carousel rotation radius |
| autoRotate | boolean | false | Enable automatic rotation |
| rotateSpeed | number | 0.5 | Auto-rotation speed |
| draggable | boolean | true | Enable drag to rotate |
| showReflection | boolean | false | Show floor reflection |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/3d-carousel-cult"
```

## Usage Example
```jsx
import { ThreeDCarousel } from "@/components/ui/3d-carousel-cult";

const projects = [
  {
    key: "clinic",
    content: (
      <div className="lyf-glass rounded-[12px] p-6 w-[280px] h-[360px]">
        <img src="/projects/clinic.jpg" alt="Clinic" className="rounded-[8px] w-full h-40 object-cover" />
        <h3 className="font-manrope font-700 text-lg text-white mt-4">Wellness Clinic</h3>
        <p className="font-manrope font-400 text-white/60 text-sm mt-2">Complete digital transformation</p>
      </div>
    ),
  },
  {
    key: "saas",
    content: (
      <div className="lyf-glass rounded-[12px] p-6 w-[280px] h-[360px]">
        <img src="/projects/saas.jpg" alt="SaaS" className="rounded-[8px] w-full h-40 object-cover" />
        <h3 className="font-manrope font-700 text-lg text-white mt-4">SaaS Platform</h3>
        <p className="font-manrope font-400 text-white/60 text-sm mt-2">Full-stack product build</p>
      </div>
    ),
  },
];

export function ProjectShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24 overflow-hidden">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-16">
        Our Work
      </h2>
      <ThreeDCarousel
        items={projects}
        perspective={1000}
        radius={350}
        autoRotate={true}
        rotateSpeed={0.3}
        draggable={true}
        className="mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Item cards: lyf-glass, 12px radius with Manrope 700/400 typography
- Images: rounded-[8px] with object-cover for consistent sizing
- Container: overflow-hidden to prevent 3D elements from causing scrollbars
- Auto-rotate at low speed (0.2-0.4) for ambient motion
- Test with 4-6 items for best visual balance; not ideal for GHL pages

## Performance Notes
- CSS transform-style: preserve-3d with GPU acceleration
- Framer Motion handles drag-to-rotate with velocity-based inertia
- Only visible items receive full render quality
- perspective property creates 3D context on single parent element
- Keep item count under 8 to prevent overlapping z-index issues
