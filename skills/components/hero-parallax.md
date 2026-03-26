---
name: hero-parallax
source: Aceternity UI
source_url: https://ui.aceternity.com/components/hero-parallax
category: components
tags: hero, parallax, gallery, scroll, images, showcase, landing
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# HeroParallax

> Full-page parallax image gallery hero with multi-row scrolling images that create a dramatic depth effect on scroll.

## When to Use
- Agency portfolio landing pages showcasing multiple projects at once
- Product launch pages with a gallery of screenshots or feature images
- Creative studio websites with visual-first hero sections
- SaaS sites showing multiple dashboard views or integrations
- Any landing page that needs a "wow factor" above the fold

## When NOT to Use
- On pages where hero needs to load fast with minimal assets
- When only 1-2 images are available (needs 9+ for full effect)
- For mobile-first designs where parallax is reduced or disabled
- On content pages where scroll depth should be preserved for content

## Pairs Well With
- `gradient-text` - Animated heading text below the parallax gallery
- `animated-content` - Stagger content section after the parallax hero
- `aurora` - Subtle aurora glow beneath the parallax images
- `marquee` - Transition from parallax hero to client logo marquee

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| products | array | - | Array of { title, thumbnail, link } objects (9-15 recommended) |
| className | string | - | Classes for the hero container |

## Installation
```bash
npx aceternity-ui@latest add hero-parallax
```

## Usage Example
```jsx
import { HeroParallax } from "@/components/ui/hero-parallax";

const projects = [
  { title: "Wellness Clinic", link: "/work/wellness", thumbnail: "/portfolio/wellness.webp" },
  { title: "DataFlow SaaS", link: "/work/dataflow", thumbnail: "/portfolio/dataflow.webp" },
  { title: "AI Assistant", link: "/work/ai-assistant", thumbnail: "/portfolio/ai.webp" },
  { title: "MedTech Portal", link: "/work/medtech", thumbnail: "/portfolio/medtech.webp" },
  { title: "Fitness App", link: "/work/fitness", thumbnail: "/portfolio/fitness.webp" },
  { title: "Legal Dashboard", link: "/work/legal", thumbnail: "/portfolio/legal.webp" },
  { title: "E-Commerce", link: "/work/ecommerce", thumbnail: "/portfolio/ecommerce.webp" },
  { title: "Real Estate", link: "/work/realestate", thumbnail: "/portfolio/realestate.webp" },
  { title: "SaaS Landing", link: "/work/saas", thumbnail: "/portfolio/saas.webp" },
];

export function PortfolioHero() {
  return <HeroParallax products={projects} />;
}
```

## Lyfework Customization Notes
- Project thumbnails should be 16:9 WebP images at 600x400px minimum
- Hero text overlay uses Manrope 800 at 5xl-7xl on `bg-[#0a0a0a]` background
- Apply `from-[#ff642a] to-[#ff0301]` gradient to hero headline keywords
- CTA buttons below parallax use `rounded-[8px]` with gradient background
- In GHL embeds, parallax scroll may need `perspective` value adjustment for iframe context

## Performance Notes
- Loads 9-15 images simultaneously; use WebP and consider `loading="lazy"` on non-visible rows
- Scroll-driven parallax uses `useScroll` + `useTransform`, optimized for 60fps
- Total section height is ~300vh; ensure sufficient content follows for good scroll UX
- Image transforms are GPU-composited via `translate3d`
- Consider a loading skeleton or blur placeholder while images load
