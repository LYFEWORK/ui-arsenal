---
name: circular-gallery
source: ReactBits
source_url: https://reactbits.dev/components/circular-gallery
category: components
tags: gallery, circular, 3d, carousel, images, immersive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# CircularGallery

> A 3D circular carousel gallery where images are arranged in a ring and rotate around a central axis. Users can drag or auto-rotate to browse through items. Creates an immersive, cinematic browsing experience.

## When to Use

- Portfolio hero sections where projects orbit in 3D space
- Product showcases that need a premium, Apple-style carousel feel
- Agency landing pages with client logos or work samples in rotation
- Event or conference speaker highlights with circular browsing
- Any hero section that needs a "wow factor" above the fold

## When NOT to Use

- Mobile-first designs (3D carousel is hard to navigate on small screens)
- Image-heavy galleries with 20+ items (becomes unwieldy to rotate through)
- Content where users need to quickly scan all items at once
- SEO-critical pages where images must be indexable and visible on load

## Pairs Well With

- `aurora` - Aurora background behind the circular gallery for atmosphere
- `gradient-text` - Gradient heading above the rotating gallery
- `animated-content` - Fade in the gallery section on scroll
- `blur-text` - Blur-reveal captions as images rotate to center

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | GalleryItem[] | required | Array of items with image, title, description |
| radius | number | 300 | Radius of the circular arrangement in px |
| autoRotate | boolean | true | Whether the gallery auto-rotates |
| rotateSpeed | number | 0.5 | Rotation speed (degrees per frame) |
| draggable | boolean | true | Allow drag to rotate |
| perspective | number | 1000 | CSS perspective value for 3D depth |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CircularGallery-TS-TW
```

## Usage Example

```jsx
import CircularGallery from '@/components/ui/CircularGallery';

function ProjectShowcase() {
  const projects = [
    { image: '/work/project-1.jpg', title: 'Summit Dental', description: 'Full digital transformation' },
    { image: '/work/project-2.jpg', title: 'Glow Aesthetics', description: 'AI-powered booking system' },
    { image: '/work/project-3.jpg', title: 'Peak Performance', description: 'Lead gen landing page' },
    { image: '/work/project-4.jpg', title: 'Urban Fitness', description: 'Membership platform' },
    { image: '/work/project-5.jpg', title: 'Clarity Coaching', description: 'Course & funnel build' },
  ];

  return (
    <section className="py-32 bg-[#0a0a0a] overflow-hidden">
      <h2 className="text-5xl font-extrabold text-white text-center font-[Manrope] mb-4">
        Featured Work
      </h2>
      <p className="text-gray-400 text-center mb-16 font-[Manrope]">
        Drag to explore our recent projects
      </p>
      <CircularGallery
        items={projects}
        radius={350}
        autoRotate
        rotateSpeed={0.3}
        perspective={1200}
        className="h-[500px]"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Image cards in the carousel should have `rounded-xl` (12px) and a subtle `lyf-glass` border
- Active/center image: add a faint `box-shadow: 0 0 40px rgba(255,100,42,0.15)` glow
- Font: `Manrope` 700 for titles, 400 for descriptions
- Background: `#0a0a0a` ensures 3D depth perception works well
- GHL: requires React + Framer Motion in a code embed; not suitable for native GHL pages
- For client builds, adjust `radius` based on item count (fewer items = smaller radius)

## Performance Notes

- 3D transforms are GPU-accelerated via `transform: rotateY()` and `translateZ()`
- Only front-facing items render at full resolution; back items can use lower-res thumbnails
- Auto-rotate uses `requestAnimationFrame` for smooth 60fps rotation
- Drag gesture uses Framer Motion's `useMotionValue` for inertia-based physics
- Consider disabling auto-rotate on mobile and using swipe instead
