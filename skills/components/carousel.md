---
name: carousel
source: ReactBits
source_url: https://reactbits.dev/components/carousel
category: components
tags: carousel, slider, swipe, gallery, images, testimonials
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Carousel

> A smooth, gesture-enabled carousel with momentum scrolling. Supports swipe on mobile, drag on desktop. Spring physics for snap-to-slide behavior.

## When to Use

- Testimonial sections with 4+ quotes
- Portfolio/case study image galleries
- Product or service showcases on mobile-first layouts
- Before/after image comparisons
- Any horizontal content that exceeds viewport width

## When NOT to Use

- Content with fewer than 3 items (just show them all)
- Desktop layouts where a grid is more scannable
- Critical content that shouldn't require interaction to see
- Pages with multiple carousels (one per page max)

## Pairs Well With

- `animated-content` - Scroll reveal the carousel section
- `tilted-card` - Carousel of tilted cards
- `glow-card` - Highlighted card in the center of the carousel
- `blur-text` - Section headline above the carousel

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | ReactNode[] | [] | Slide content |
| autoPlay | boolean | false | Auto-advance slides |
| interval | number | 4000 | Auto-play interval in ms |
| showDots | boolean | true | Show pagination dots |
| showArrows | boolean | true | Show prev/next arrows |
| gap | number | 20 | Gap between slides in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Carousel-TS-TW
```

## Usage Example

```jsx
import Carousel from '@/components/ui/Carousel';

function TestimonialCarousel() {
  const testimonials = [
    { quote: "No-show rate dropped 40%.", name: "Dr. Sarah Chen" },
    { quote: "Paid for itself in two weeks.", name: "Mark Rivera, DDS" },
    { quote: "I finally stopped chasing patients.", name: "Dr. James Park" },
    { quote: "Best investment we've made.", name: "Lisa Thompson, NP" },
  ];

  return (
    <Carousel autoPlay={true} interval={5000} showDots={true} gap={24}>
      {testimonials.map((t, i) => (
        <div key={i} className="lyf-glass p-10 rounded-2xl min-w-[350px]">
          <p className="text-lg text-white italic">"{t.quote}"</p>
          <p className="mt-4 text-sm text-gray-400 font-bold">{t.name}</p>
        </div>
      ))}
    </Carousel>
  );
}
```

## Lyfework Customization Notes

- Slide width: 320-400px for testimonials. Full viewport width for hero image carousels.
- Pagination dots: Lyfework orange `#ff642a` for active dot, `rgba(255,255,255,0.2)` for inactive
- Arrow buttons: glass background with white chevron icons
- `autoPlay` with `interval={4000-6000}` for testimonials. Disable for portfolios (let users browse).
- For GHL: test touch events inside the GHL iframe on mobile

## Performance Notes

- framer-motion drag gestures with momentum physics
- Only renders visible slides + 1 on each side
- Images should be lazy-loaded for image carousels
- Touch-optimized for mobile
