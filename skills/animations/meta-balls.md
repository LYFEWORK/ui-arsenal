---
name: meta-balls
source: ReactBits
source_url: https://reactbits.dev/animations/meta-balls
category: animations
tags: metaball, blob, organic, merge, svg, ambient
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# MetaBalls

> Organic metaball blobs that merge and separate with smooth gooey transitions, creating a lava-lamp-like ambient animation for premium backgrounds.

## When to Use

- Hero section backgrounds where organic motion creates a living, breathing feel
- Behind-the-fold ambient sections on creative agency or design studio sites
- Loading or splash screens that feel artistic instead of utilitarian
- Abstract decoration for SaaS pages to break away from rigid grid layouts
- "Our process" or "How it works" sections where blobs morph to suggest fluidity

## When NOT to Use

- Corporate or enterprise sites where organic blobs feel too casual
- Content-heavy pages where the gooey motion distracts from reading
- Mobile-first builds where SVG filter performance can lag
- Pages that need fast rendering -- SVG filters are computationally expensive

## Pairs Well With

- `aurora` - Metaballs floating over aurora gradients for a layered organic background
- `gradient-text` - Brand gradient text over gooey blob backgrounds ties the palette together
- `blur-text` - Reveal a headline over merging blobs for a dramatic hero sequence
- `animated-content` - Standard content sections below the metaball hero maintain cohesion

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| ballCount | number | 5 | Number of metaball blobs |
| colors | string[] | ["#ff642a", "#ff0301"] | Array of blob fill colors |
| minRadius | number | 40 | Minimum blob radius in pixels |
| maxRadius | number | 100 | Maximum blob radius in pixels |
| speed | number | 2 | Movement speed multiplier |
| gooeyness | number | 20 | SVG filter blur that creates the merge effect |
| interactive | boolean | false | Blobs react to cursor position |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MetaBalls-TS-TW
```

## Usage Example

```jsx
import MetaBalls from '@/components/ui/MetaBalls';

function CreativeHero() {
  return (
    <section className="relative bg-[#0a0a0a] min-h-screen flex items-center font-[Manrope]">
      <div className="absolute inset-0 opacity-40">
        <MetaBalls
          ballCount={6}
          colors={['#ff642a', '#ff0301', '#ff4500']}
          minRadius={50}
          maxRadius={120}
          speed={1.5}
          gooeyness={25}
          interactive
        />
      </div>
      <div className="relative z-10 max-w-3xl mx-auto px-8 text-center">
        <h1 className="text-6xl font-bold text-white leading-tight">
          Design without{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            boundaries
          </span>
        </h1>
        <p className="mt-6 text-xl text-gray-400">
          Fluid, organic, alive. Just like your brand should feel.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use `colors={['#ff642a', '#ff0301']}` to keep blobs within the brand gradient spectrum.
- Wrap the MetaBalls container with `opacity-40` so the blobs tint the background without overpowering text.
- The `gooeyness` prop maps to an SVG `feGaussianBlur` stdDeviation; 15-25 is the sweet spot for smooth merges.
- Position container `absolute inset-0` and overlay content with `relative z-10` for the standard layout pattern.
- On GHL embeds, SVG filters render correctly but can be CPU-intensive; reduce `ballCount` to 3-4 for iframe use.
- Manrope bold text at `text-white` remains readable over the blobs when they are at 30-50% opacity.

## Performance Notes

- Uses SVG with `feGaussianBlur` and `feColorMatrix` filters for the gooey merge effect
- SVG filters are CPU-rendered, not GPU-accelerated -- the most expensive component in this tier
- Keep `ballCount` under 8 and `gooeyness` under 30 to maintain 60fps on mid-range devices
- Movement uses `requestAnimationFrame` with simple sine-wave position updates
- Consider using `IntersectionObserver` to pause animation when scrolled out of view
