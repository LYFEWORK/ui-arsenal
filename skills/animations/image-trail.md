---
name: image-trail
source: ReactBits
source_url: https://reactbits.dev/animations/image-trail
category: animations
tags: cursor, trail, images, hover, gallery, interactive, creative
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# ImageTrail

> Images spawn and trail behind the cursor as it moves across a container. Creates a dynamic gallery effect where portfolio images cascade from mouse movement.

## When to Use

- Portfolio/gallery pages where images should feel alive
- Creative agency hero sections
- Artist or photographer websites
- Interactive "about" or "our work" sections
- Any showcase build where static grids feel too safe

## When NOT to Use

- Business-focused landing pages (too playful)
- Mobile layouts (no cursor trail)
- Pages with heavy existing image content (visual overload)
- Conservative brand verticals

## Pairs Well With

- `infinite-menu` - Image trail on the fullscreen menu
- `splash-cursor` - Choose one or the other, never both
- `blur-text` - Headline over image trail area
- `gradient-text` - "Our Work" in gradient above the trail zone

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| images | string[] | [] | Array of image URLs |
| renderImageBuffer | number | 50 | Distance before new image spawns |
| rotationRange | number | 20 | Max rotation in degrees |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ImageTrail-TS-TW
```

## Usage Example

```jsx
import ImageTrail from '@/components/ui/ImageTrail';

function PortfolioHero() {
  const images = ['/work/site1.jpg', '/work/site2.jpg', '/work/site3.jpg', '/work/site4.jpg'];
  return (
    <section className="relative h-screen">
      <ImageTrail images={images} renderImageBuffer={60} rotationRange={15} className="absolute inset-0" />
      <div className="relative z-10 flex items-center justify-center h-full">
        <h1 className="text-6xl font-extrabold text-white">Our Work</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Tier 3 showcase component. Use for Lyfework's own portfolio page or premium creative builds.
- Images should be optimized thumbnails (300-500px wide), not full-res
- `rotationRange` of 10-20 for subtle tilt. Above 25 gets messy.
- Not for GHL builds (requires React with DOM manipulation)
- Desktop only. Provide a static gallery fallback on mobile.

## Performance Notes

- Creates DOM elements dynamically, cleans up old ones
- Image preloading is important (load all images before enabling)
- Keep to 10-15 unique images max in the rotation
- GPU accelerated transforms
