---
name: cubes
source: ReactBits
source_url: https://reactbits.dev/animations/cubes
category: animations
tags: cube, 3d, rotate, geometric, interactive, css
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Cubes

> A 3D rotating cube animation built with pure CSS transforms, ideal for loading states, hero decorations, or interactive geometric backgrounds.

## When to Use

- Loading screens or skeleton states that need more personality than a spinner
- Hero section decorative elements to add depth and dimension
- Interactive 3D showcases where each cube face displays different content
- Background ambient motion for SaaS or tech-forward landing pages
- "About us" sections where each cube face shows a team value or stat

## When NOT to Use

- Mobile-first builds where 3D CSS transforms can be janky on low-end devices
- Pages that need fast LCP scores (3D transforms can delay paint)
- Content that needs to be accessible via screen readers (cube faces are decorative)
- Simple marketing pages for non-tech brands where cubes feel out of place

## Pairs Well With

- `aurora` - Aurora background behind rotating cubes creates a sci-fi atmosphere
- `particles` - Cubes floating among particles for a deep-space hero section
- `gradient-text` - Brand gradient text next to geometric cube animations
- `animated-content` - Scroll-trigger the cube spin as the section enters the viewport

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| size | number | 120 | Cube edge length in pixels |
| speed | number | 4 | Rotation cycle duration in seconds |
| axis | "x" \| "y" \| "xy" | "xy" | Rotation axis |
| faces | ReactNode[] | [] | Content for each cube face (up to 6) |
| pauseOnHover | boolean | false | Pause rotation when hovered |
| color | string | "rgba(255,255,255,0.1)" | Face background color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Cubes-TS-TW
```

## Usage Example

```jsx
import Cubes from '@/components/ui/Cubes';

function SaasHeroDecoration() {
  return (
    <section className="relative bg-[#0a0a0a] min-h-screen flex items-center font-[Manrope]">
      <div className="max-w-6xl mx-auto px-8 grid grid-cols-2 gap-16 items-center">
        <div>
          <h1 className="text-5xl font-bold text-white leading-tight">
            Build faster with{' '}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Lyfework
            </span>
          </h1>
          <p className="mt-6 text-lg text-gray-400">
            Ship premium websites in half the time.
          </p>
        </div>
        <div className="flex justify-center">
          <Cubes
            size={160}
            speed={6}
            axis="xy"
            color="rgba(255,100,42,0.08)"
            pauseOnHover
          />
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Set face color to `rgba(255,100,42,0.08)` for a subtle brand-tinted cube on `#0a0a0a` backgrounds.
- Use `border: 1px solid rgba(255,100,42,0.15)` on faces for a visible edge with brand color.
- Keep cube `size` under 200px on mobile viewports to avoid overflow.
- Rounded corners on cube faces don't work well with 3D transforms; stick to sharp edges or `rounded-[4px]` max.
- For GHL embeds, ensure the parent container has `perspective: 800px` set explicitly.
- Font on cube faces should be Manrope bold at a readable size relative to the cube dimensions.

## Performance Notes

- Pure CSS transforms with `transform-style: preserve-3d` -- no JS runtime cost
- Uses `will-change: transform` for GPU layer promotion
- Can cause compositing issues on older Safari; test on WebKit
- Bundle size: 0KB runtime (CSS-only animation)
- Reduce `speed` or pause on mobile to save battery on continuous animations
