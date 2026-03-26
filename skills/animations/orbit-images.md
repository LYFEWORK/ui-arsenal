---
name: orbit-images
source: ReactBits
source_url: https://reactbits.dev/animations/orbit-images
category: animations
tags: orbit, images, circular, 3d, gallery, rotate
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# OrbitImages

> Images orbiting around a central point in a 3D circular path, creating a dynamic rotating gallery perfect for showcasing work, team members, or product features.

## When to Use

- Portfolio showcases where project thumbnails orbit a central tagline
- Team member photos circling a company logo or mission statement
- Feature highlights orbiting a product screenshot in the center
- Client logo displays that feel more dynamic than a static grid
- Hero sections where visual motion draws attention to the center element

## When NOT to Use

- When you need a traditional gallery with click-to-enlarge behavior
- Pages with many images that would make the orbit too crowded (max 8)
- Mobile screens where the orbit radius shrinks too small to see details
- Content where image order or sequence matters (orbit has no fixed order)

## Pairs Well With

- `animated-content` - Reveal the orbit on scroll, then it starts rotating
- `gradient-text` - Brand gradient text in the center of the orbit
- `magic-rings` - Concentric rings pulsing outward while images orbit inward
- `blur-text` - Center headline reveals with blur while images orbit around it

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| images | { src: string; alt: string }[] | required | Array of images to orbit |
| radius | number | 200 | Orbit radius in pixels |
| speed | number | 20 | Time in seconds for one full orbit |
| tilt | number | 15 | 3D tilt angle in degrees |
| direction | "clockwise" \| "counterclockwise" | "clockwise" | Orbit direction |
| imageSize | number | 64 | Diameter of each orbiting image in pixels |
| pauseOnHover | boolean | true | Pause orbit on hover |
| centerContent | ReactNode | null | Content to display in the center of the orbit |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/OrbitImages-TS-TW
```

## Usage Example

```jsx
import OrbitImages from '@/components/ui/OrbitImages';

function PortfolioShowcase() {
  const projects = [
    { src: '/work/clinic-thumb.jpg', alt: 'Dental clinic site' },
    { src: '/work/saas-thumb.jpg', alt: 'SaaS dashboard' },
    { src: '/work/fitness-thumb.jpg', alt: 'Fitness app landing' },
    { src: '/work/realty-thumb.jpg', alt: 'Real estate platform' },
    { src: '/work/restaurant-thumb.jpg', alt: 'Restaurant website' },
    { src: '/work/ecom-thumb.jpg', alt: 'E-commerce store' },
  ];

  return (
    <section className="bg-[#0a0a0a] py-32 px-8 font-[Manrope]">
      <div className="max-w-4xl mx-auto flex justify-center">
        <OrbitImages
          images={projects}
          radius={220}
          speed={25}
          tilt={20}
          imageSize={72}
          pauseOnHover
          centerContent={
            <div className="text-center">
              <h2 className="text-3xl font-bold bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
                Our Work
              </h2>
              <p className="mt-2 text-gray-500 text-sm">Hover to pause</p>
            </div>
          }
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Set `imageSize={72}` for portfolio thumbnails; `imageSize={56}` for team headshots or logos.
- Orbiting images should have `rounded-full` applied internally for a polished circular crop.
- Center content using the brand gradient (`from-[#ff642a] to-[#ff0301]`) on the headline ties the orbit to the brand.
- On `#0a0a0a` backgrounds, add a subtle border ring at the orbit radius using `lyf-glass` opacity for depth.
- GHL pages: ensure image paths are absolute CDN URLs, not relative, since GHL rewrites paths.
- Reduce `radius` to 150px on tablet and 120px on mobile viewports with responsive logic.

## Performance Notes

- framer-motion drives the rotation with `rotate` transforms on a parent container
- Individual images use `counter-rotate` to stay upright as they orbit
- 3D tilt uses `perspective` and `rotateX` -- GPU composited
- Keep `images` array under 8 items; more causes visual clutter and DOM overhead
- SSR safe: images render in their starting positions, orbit begins on hydration
