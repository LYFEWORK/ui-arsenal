---
name: dome-gallery
source: ReactBits
source_url: https://reactbits.dev/components/dome-gallery
category: components
tags: gallery, dome, 3d, immersive, portfolio, WebGL
dependencies: three.js, @react-three/fiber, @react-three/drei
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# DomeGallery

> A dome-shaped 3D gallery layout rendered with WebGL. Images or cards are arranged on the inner surface of a hemisphere, creating an immersive virtual environment that users can orbit and explore. Premium-tier visual experience.

## When to Use

- High-end agency portfolio pages where immersion is the differentiator
- Creative studio landing pages that need to demonstrate technical prowess
- Product launch microsites with a cinematic browsing experience
- Art or photography portfolios where 3D context adds to the viewing experience
- Conference or event sites with immersive speaker/session browsing

## When NOT to Use

- Standard business websites (overkill, slow to load)
- Mobile-first audiences (WebGL is heavy on mobile batteries and performance)
- SEO-critical pages (WebGL content is not indexable)
- Pages that need to load fast (three.js bundle adds significant weight)
- Client builds on tight timelines (complex to customize and maintain)

## Pairs Well With

- `gradient-text` - Gradient heading overlay on top of the dome scene
- `animated-content` - Fade in a fallback 2D grid before dome loads
- `particles` - Particle effects inside the dome environment
- `aurora` - Aurora-style background visible through dome gaps

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | DomeItem[] | required | Array of items with image, title, link |
| radius | number | 5 | Dome radius in 3D units |
| autoOrbit | boolean | true | Camera auto-orbits the dome |
| orbitSpeed | number | 0.2 | Speed of auto-orbit rotation |
| fov | number | 60 | Camera field of view in degrees |
| enableZoom | boolean | true | Allow scroll-to-zoom |
| fallback | ReactNode | null | 2D fallback for unsupported devices |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/DomeGallery-TS-TW
```

## Usage Example

```jsx
import DomeGallery from '@/components/ui/DomeGallery';

function ImmersivePortfolio() {
  const works = [
    { image: '/work/dome-1.jpg', title: 'Summit Dental Redesign', link: '/work/summit' },
    { image: '/work/dome-2.jpg', title: 'AI Dashboard MVP', link: '/work/ai-dash' },
    { image: '/work/dome-3.jpg', title: 'Glow Aesthetics Platform', link: '/work/glow' },
    { image: '/work/dome-4.jpg', title: 'Peak Performance Funnel', link: '/work/peak' },
    { image: '/work/dome-5.jpg', title: 'BookFlow SaaS', link: '/work/bookflow' },
    { image: '/work/dome-6.jpg', title: 'Vibe Studio Brand', link: '/work/vibe' },
  ];

  return (
    <section className="relative h-screen bg-[#0a0a0a] overflow-hidden">
      <div className="absolute inset-0 z-0">
        <DomeGallery
          items={works}
          radius={6}
          autoOrbit
          orbitSpeed={0.15}
          fov={55}
          fallback={
            <div className="grid grid-cols-3 gap-4 p-8">
              {works.map((w, i) => (
                <img key={i} src={w.image} alt={w.title} className="rounded-xl" />
              ))}
            </div>
          }
        />
      </div>
      <div className="absolute inset-0 z-10 flex items-end justify-center pb-16 pointer-events-none">
        <h2 className="text-5xl font-extrabold text-white font-[Manrope] text-center drop-shadow-lg">
          Explore Our Universe
        </h2>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use only for premium Lyfework portfolio or agency showcase pages, not standard client builds
- Image panels inside the dome should have `rounded-lg` corners with a subtle white/5 border
- Ambient light color: `#ff642a` at low intensity (0.1) for Lyfework brand warmth
- Always provide a 2D `fallback` grid for mobile and low-power devices
- Not GHL compatible -- requires a standalone React app deployment (Vercel/Netlify)
- Font overlays: `Manrope` 800 with `drop-shadow-lg` for readability over 3D scene

## Performance Notes

- three.js + @react-three/fiber add ~150KB to the bundle (gzipped) -- code-split aggressively
- Use `Suspense` with a loading skeleton while the 3D scene initializes
- Texture images should be power-of-2 dimensions and compressed (WebP preferred)
- Disable auto-orbit and reduce polygon count on mobile via `useMediaQuery`
- `frameloop="demand"` on the Canvas to prevent rendering when nothing moves
