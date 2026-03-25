---
name: hyperspeed
source: ReactBits
source_url: https://reactbits.dev/backgrounds/hyperspeed
category: backgrounds
tags: background, hyperspeed, warp, stars, space, WebGL, dramatic
dependencies: three.js
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Hyperspeed

> A star-field warp speed effect. Particles streak toward the camera creating a hyperspace jump visual. Three.js powered. Maximum dramatic impact.

## When to Use

- Launch pages or product announcements where you need maximum drama
- Tech/AI product hero sections
- "Coming soon" or waitlist pages
- One-time use for the most important page on a site
- Builds where the client explicitly wants a "sci-fi" or futuristic feel

## When NOT to Use

- Standard business landing pages (way too dramatic)
- Pages with important text content (readability suffers)
- Mobile-first builds (Three.js is heavy on phones)
- Any page that isn't the hero (this is a one-per-site component)
- Conservative verticals (medical, legal, financial)

## Pairs Well With

- `blur-text` - Text blur-reveals over the hyperspeed field
- `gradient-text` - Brand name in gradient over starfield
- `fade-content` - Fade in CTA after the initial impact settles

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| starCount | number | 1000 | Number of star particles |
| speed | number | 2 | Warp speed multiplier |
| starColor | string | "#ffffff" | Color of stars |
| trailLength | number | 3 | Length of star trails |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Hyperspeed-TS-TW
```

## Usage Example

```jsx
import Hyperspeed from '@/components/ui/Hyperspeed';

function LaunchHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Hyperspeed starCount={800} speed={1.5} trailLength={2.5} />
      </div>
      <div className="relative z-10 text-center">
        <h1 className="text-7xl font-extrabold text-white">The Future is Live.</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- This is the nuclear option. Use once per build, for the single most important page.
- `starCount` of 600-1000. Higher than 1500 tanks mobile performance.
- `speed` of 1.0-2.0 for ambient warp. Above 3.0 for explosive launch moment.
- Star color: white by default. Add `#ff642a` tinted stars for Lyfework brand.
- Not for GHL builds (requires Three.js canvas)
- Always add a fallback: dark gradient background for devices that can't run WebGL
- Consider auto-slowing speed after 3-4 seconds to let content breathe

## Performance Notes

- Three.js adds ~150kb gzipped. Heavy dependency.
- WebGL required. Add feature detection.
- Reduce starCount to 300-400 on mobile
- Use `requestAnimationFrame` pause when tab is hidden
- Will drain mobile battery if left running
