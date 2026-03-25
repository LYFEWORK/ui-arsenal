---
name: grid-motion
source: ReactBits
source_url: https://reactbits.dev/backgrounds/grid-motion
category: backgrounds
tags: background, grid, motion, tiles, images, text, mosaic
dependencies: gsap
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GridMotion

> An animated grid of tiles that shift, scale, and rearrange with smooth motion. Tiles can contain images, text, or colored blocks. Creates a living mosaic background.

## When to Use

- Portfolio showcase backgrounds (grid of project thumbnails in motion)
- Agency "about" or culture sections
- Event or conference landing pages
- Creative hero alternatives when you want something unique
- Sections that need to display many visual assets at once

## When NOT to Use

- Behind text-heavy content (too visually active)
- Minimalist designs (grid motion is inherently busy)
- Standard business landing pages
- Mobile-first builds (grid looks cramped on small screens)

## Pairs Well With

- `blur-text` - Headline over a moving grid of portfolio images
- `gradient-text` - Brand name floating above the mosaic
- `fade-content` - Content fades in as the grid moves behind it

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | (string \| ReactNode)[] | [] | Grid tile content (URLs or components) |
| columns | number | 4 | Number of grid columns |
| speed | number | 1 | Animation speed |
| gap | number | 4 | Gap between tiles in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GridMotion-TS-TW
```

## Usage Example

```jsx
import GridMotion from '@/components/ui/GridMotion';

function PortfolioBackground() {
  const items = ['/work/1.jpg', '/work/2.jpg', '/work/3.jpg', '/work/4.jpg', '/work/5.jpg', '/work/6.jpg', '/work/7.jpg', '/work/8.jpg'];
  return (
    <section className="relative h-screen overflow-hidden">
      <div className="absolute inset-0 opacity-30">
        <GridMotion items={items} columns={4} speed={0.5} gap={4} />
      </div>
      <div className="relative z-10 flex items-center justify-center h-full">
        <h1 className="text-6xl font-extrabold text-white">Our Work</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use at 20-40% opacity as a background layer, not full brightness
- Images should be uniform aspect ratio for clean grid
- `columns` of 3-5 depending on viewport. 4 is default.
- `speed` of 0.3-0.8 for ambient. Above 1.0 gets distracting.
- GSAP powers the tile animations. Load globally if using SplitText too.
- Not for GHL (requires GSAP + React)

## Performance Notes

- GSAP handles tile transforms
- Images should be thumbnails (200-400px), not full resolution
- Reduce columns on mobile (2-3)
- Lazy load images outside initial viewport
