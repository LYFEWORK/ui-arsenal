---
name: animated-testimonials
source: Aceternity UI
source_url: https://ui.aceternity.com/components/animated-testimonials
category: components
tags: testimonials, carousel, social-proof, animation, auto-rotate, reviews
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# AnimatedTestimonials

> Auto-rotating testimonial carousel with smooth cross-fade animations, avatar displays, and quote transitions.

## When to Use
- Social proof sections on clinic or SaaS landing pages
- Client review showcases on portfolio sites
- Case study highlights with rotating quotes
- Team endorsement or partner testimonial blocks
- Before/after transformation stories for health and wellness sites

## When NOT to Use
- When you have fewer than 3 testimonials (use static cards instead)
- For long-form case studies that need full reading time
- When testimonials include complex media like video

## Pairs Well With
- `count-up` - Pair with animated stats (e.g., "500+ Happy Clients")
- `animated-content` - Fade in the testimonial section on scroll
- `gradient-text` - Highlight key phrases in testimonial quotes
- `aurora` - Use aurora background behind testimonial section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| testimonials | array | - | Array of { quote, name, designation, src } objects |
| autoplay | boolean | true | Auto-rotate through testimonials |
| interval | number | 5000 | Milliseconds between rotations |

## Installation
```bash
npx aceternity-ui@latest add animated-testimonials
```

## Usage Example
```jsx
import { AnimatedTestimonials } from "@/components/ui/animated-testimonials";

const reviews = [
  {
    quote: "Lyfework transformed our clinic's online presence. Patient bookings increased 3x within the first month.",
    name: "Dr. Sarah Chen",
    designation: "Medical Director, Wellness First Clinic",
    src: "/testimonials/sarah.webp",
  },
  {
    quote: "The AI-powered scheduling integration with GHL saved our team 20 hours per week. Absolutely game-changing.",
    name: "Marcus Rivera",
    designation: "Operations Manager, HealthTech Solutions",
    src: "/testimonials/marcus.webp",
  },
  {
    quote: "Beautiful design, blazing fast performance. Our SaaS conversion rate jumped 40% after the Lyfework rebuild.",
    name: "Emily Zhao",
    designation: "CEO, DataFlow Analytics",
    src: "/testimonials/emily.webp",
  },
];

export function TestimonialSection() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="text-center font-[Manrope] font-800 text-4xl text-white mb-4">
        What Our <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Clients Say</span>
      </h2>
      <AnimatedTestimonials testimonials={reviews} autoplay />
    </section>
  );
}
```

## Lyfework Customization Notes
- Override testimonial card styles with `lyf-glass` class for frosted glass look on dark backgrounds
- Use Manrope 400 for quote text, 700 for client names, 400 italic for designations
- Apply #0a0a0a section background with subtle `border-b border-white/5` dividers
- Avatar images should be optimized WebP at 80x80px minimum
- GHL embedded pages may need `overflow: hidden` on the carousel container to prevent scroll bleed

## Performance Notes
- Auto-rotation pauses on hover/focus for accessibility
- Images are preloaded one slide ahead to avoid flash of empty content
- Cross-fade animation uses opacity transforms only (GPU-composited)
- Limit to 8-10 testimonials; beyond that, consider paginated display
- Use `loading="lazy"` on avatar images not in the first visible slide
