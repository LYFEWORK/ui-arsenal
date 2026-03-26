---
name: motion-carousel
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/motion-carousel
category: components
tags: carousel, slider, physics, momentum, drag, gallery
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# MotionCarousel

> Physics-based carousel with momentum scrolling, snap points, and smooth drag interactions powered by spring physics.

## When to Use
- Portfolio project showcases with full-width project slides
- Testimonial carousels with client reviews and photos
- Service offering slides on clinic or agency landing pages
- Image galleries for before/after treatment results
- Feature highlight carousels in SaaS product tours

## When NOT to Use
- Content that should all be visible simultaneously — use a grid
- Two-item toggles — use animated-tabs instead
- Text-heavy content where swiping interrupts reading flow
- Auto-playing carousels that violate WCAG motion guidelines

## Pairs Well With
- `spotlight-card` - spotlight cards as carousel slide items
- `tilted-card` - tilted cards in a draggable carousel for portfolio sections
- `luxe-badge` - category badge overlays on carousel slide items
- `blur-text` - blur-reveal heading above the carousel section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Carousel slide items |
| className | string | — | Container CSS classes |
| itemWidth | string \| number | "100%" | Width of each slide item |
| gap | number | 16 | Gap between slides in pixels |
| snapToItem | boolean | true | Snap to nearest item on release |
| showDots | boolean | true | Show pagination dots |
| showArrows | boolean | true | Show prev/next arrow buttons |
| dragElastic | number | 0.2 | Drag elasticity at boundaries |
| autoPlay | boolean | false | Enable auto-advance |
| autoPlayInterval | number | 5000 | Auto-advance interval in ms |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/motion-carousel"
```

## Usage Example
```jsx
import { MotionCarousel } from "@/components/ui/motion-carousel";

export function TestimonialCarousel() {
  const testimonials = [
    { name: "Dr. Sarah Chen", text: "Lyfework transformed our patient acquisition.", role: "Dental Practice Owner" },
    { name: "Mark Rivera", text: "Our bookings increased 3x in the first month.", role: "Med Spa Director" },
    { name: "Lisa Thompson", text: "The automation saves us 20 hours per week.", role: "Clinic Manager" },
  ];

  return (
    <section className="py-20 bg-[#0a0a0a] overflow-hidden">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-12">
        What Our Clients Say
      </h2>
      <MotionCarousel
        className="max-w-5xl mx-auto px-6"
        itemWidth="100%"
        snapToItem
        showDots
        dragElastic={0.15}
      >
        {testimonials.map((t) => (
          <div key={t.name} className="lyf-glass rounded-[12px] p-10 text-center">
            <p className="font-manrope font-400 text-gray-300 text-lg mb-6">"{t.text}"</p>
            <p className="font-manrope font-700 text-white">{t.name}</p>
            <p className="font-manrope font-400 text-[#ff642a] text-sm">{t.role}</p>
          </div>
        ))}
      </MotionCarousel>
    </section>
  );
}
```

## Lyfework Customization Notes
- Slide cards: `lyf-glass rounded-[12px]` for brand card styling
- Pagination dots active color: `bg-[#ff642a]` inactive: `bg-white/20`
- Arrow buttons: `text-white/50 hover:text-[#ff642a]` for brand accent hover
- Quote text: `font-manrope font-400 text-gray-300`, names: `font-manrope font-700 text-white`
- GHL compatible — drag events use pointer events, work in iframe embeds
- Add `overflow-hidden` to parent section to prevent horizontal scroll bleed

## Performance Notes
- Only visible slides + 1 buffer slide are rendered — virtual scrolling for large sets
- Drag momentum uses framer-motion spring physics — native-feeling inertia
- Snap calculation done once on release — no continuous calculation during drag
- Images in slides should use lazy loading for off-screen items
- Touch events are passive — no scroll-blocking on mobile
