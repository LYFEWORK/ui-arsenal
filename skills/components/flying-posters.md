---
name: flying-posters
source: ReactBits
source_url: https://reactbits.dev/components/flying-posters
category: components
tags: poster, flying, entrance, 3d, gallery, dramatic
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FlyingPosters

> Posters and cards that fly in from different directions with 3D rotation, converging into a grid or scattered layout. Creates a dramatic, cinematic entrance effect that demands attention. Perfect for portfolio hero sections.

## When to Use

- Portfolio hero sections where project images need a dramatic entrance
- Agency "our work" sections that want to feel cinematic
- Event or conference promotional pages with speaker posters
- Product launch pages where multiple product images converge
- Any gallery section where a static grid feels too predictable

## When NOT to Use

- Frequently visited pages (flying animation gets old on repeat visits)
- Mobile-first designs (complex 3D flight paths can feel chaotic on small screens)
- Content-first layouts where users need to scan images quickly
- Pages with slow load times (flying animation on late-loading images looks broken)

## Pairs Well With

- `animated-content` - Section-level reveal before posters fly in
- `aurora` - Aurora background while posters settle into position
- `gradient-text` - Gradient heading that appears after posters land
- `click-spark` - Spark effect when a poster is clicked to view detail

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | PosterItem[] | required | Array of poster items with image, title, link |
| layout | "grid" \| "scattered" | "grid" | Final resting layout |
| columns | number | 3 | Number of grid columns (grid layout only) |
| staggerDelay | number | 0.1 | Delay between each poster's flight (seconds) |
| perspective | number | 1200 | CSS perspective for 3D depth |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FlyingPosters-TS-TW
```

## Usage Example

```jsx
import FlyingPosters from '@/components/ui/FlyingPosters';

function WorkHero() {
  const projects = [
    { image: '/work/poster-1.jpg', title: 'Summit Dental', link: '/work/summit' },
    { image: '/work/poster-2.jpg', title: 'AI Dashboard', link: '/work/ai-dash' },
    { image: '/work/poster-3.jpg', title: 'Glow Aesthetics', link: '/work/glow' },
    { image: '/work/poster-4.jpg', title: 'Peak PT', link: '/work/peak' },
    { image: '/work/poster-5.jpg', title: 'BookFlow', link: '/work/bookflow' },
    { image: '/work/poster-6.jpg', title: 'Vibe Studio', link: '/work/vibe' },
  ];

  return (
    <section className="min-h-screen bg-[#0a0a0a] py-32 px-8 overflow-hidden">
      <h1 className="text-6xl font-extrabold text-white text-center font-[Manrope] mb-20">
        Our Work
      </h1>
      <FlyingPosters
        items={projects}
        layout="grid"
        columns={3}
        staggerDelay={0.12}
        perspective={1200}
        className="max-w-6xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Poster cards: `rounded-xl` (12px), subtle `border border-white/5` once landed
- On hover after landing, add a `scale-[1.02]` and `shadow-lg` with orange tint
- Title overlays: `Manrope` 700, white with dark gradient overlay at bottom of image
- Background: `#0a0a0a` provides the depth needed for 3D flight to register visually
- Not ideal for GHL native pages -- best deployed as a standalone React section
- For client builds, match poster aspect ratios (3:4 portrait works best for this effect)

## Performance Notes

- Framer Motion `variants` with staggered children for sequenced flight animations
- 3D transforms (`rotateX`, `rotateY`, `translateZ`) are GPU-composited
- Images should be preloaded before animation starts to avoid blank flying rectangles
- Use `Intersection Observer` to trigger flight only when section enters viewport
- Limit to 6-9 posters for smooth performance; more than 12 can drop frames on mid-range devices
