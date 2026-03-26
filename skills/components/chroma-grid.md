---
name: chroma-grid
source: ReactBits
source_url: https://reactbits.dev/components/chroma-grid
category: components
tags: grid, chromatic, color, animated, mosaic, gallery
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ChromaGrid

> A chromatic, colorful animated grid layout where cells shift colors, reveal content, or pulse with vibrant gradients. Creates a mosaic-style visual that is part gallery, part art piece. Pure CSS with optional JS for interactivity.

## When to Use

- Portfolio or gallery sections that need a visually striking grid
- Brand showcase pages where color and energy are key
- Agency "our work" sections with image tiles and color overlays
- Creative studio landing pages that want to feel artistic
- Event or music-related sites where vibrancy matches the brand

## When NOT to Use

- Corporate or clinical sites where bold colors feel off-brand
- Data-heavy dashboards where the mosaic distracts from content
- Text-heavy pages where chromatic effects reduce readability
- E-commerce product grids where clean presentation matters more

## Pairs Well With

- `animated-content` - Scroll-reveal the grid rows for cascading entrance
- `spotlight-card` - Add spotlight hover to individual grid cells
- `blur-text` - Blur-reveal text overlays on grid items
- `particles` - Particle background behind the chroma grid for depth

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | GridItem[] | required | Array of grid items with content, color, size |
| columns | number | 4 | Number of grid columns |
| gap | number | 4 | Gap between grid cells in px |
| animated | boolean | true | Whether colors animate/pulse |
| palette | string[] | ["#ff642a","#ff0301","#1a1a2e"] | Color palette for chromatic effects |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ChromaGrid-TS-TW
```

## Usage Example

```jsx
import ChromaGrid from '@/components/ui/ChromaGrid';

function PortfolioSection() {
  const projects = [
    { image: '/work/clinic-site.jpg', label: 'Summit Dental', color: '#ff642a', size: 'large' },
    { image: '/work/saas-dash.jpg', label: 'AI Dashboard', color: '#ff0301', size: 'small' },
    { image: '/work/ecom-store.jpg', label: 'Glow Store', color: '#ff642a', size: 'small' },
    { image: '/work/landing-page.jpg', label: 'Peak Performance', color: '#1a1a2e', size: 'medium' },
    { image: '/work/booking-app.jpg', label: 'BookFlow', color: '#ff0301', size: 'medium' },
    { image: '/work/brand-site.jpg', label: 'Vibe Studio', color: '#ff642a', size: 'small' },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-16">
        Our Work
      </h2>
      <ChromaGrid
        items={projects}
        columns={3}
        gap={6}
        palette={['#ff642a', '#ff0301', '#1a1a2e']}
        className="max-w-6xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Default palette: `['#ff642a', '#ff0301', '#1a1a2e']` aligns with Lyfework brand gradient
- Grid cells should have `rounded-xl` (12px) corners for consistency
- Overlay text uses `Manrope` 700, white with `text-shadow` for readability over images
- For client builds, extract 3-4 colors from their brand palette for the chroma effect
- GHL compatible as it uses CSS grid + minimal JS for hover interactions
- Background: `#0a0a0a` to let the chromatic colors pop

## Performance Notes

- Pure CSS grid layout with `object-fit: cover` for responsive images
- Color animations use CSS `transition` on background-color, no JS animation loop
- Images should be lazy-loaded with `loading="lazy"` for grids with many items
- Hover effects use CSS `::after` pseudo-element overlays, no repaints
- Keep grid items under 12 for initial viewport to maintain fast LCP
