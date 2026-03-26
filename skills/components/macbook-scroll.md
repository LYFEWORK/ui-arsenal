---
name: macbook-scroll
source: Aceternity UI
source_url: https://ui.aceternity.com/components/macbook-scroll
category: components
tags: macbook, scroll, product, laptop, animation, showcase, reveal
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# MacbookScroll

> MacBook lid-opening scroll animation that reveals a product screenshot or video as the user scrolls, perfect for product pages.

## When to Use
- SaaS product launch pages showcasing a dashboard or web app
- Portfolio presentations showing work in a premium device context
- AI tool demos with progressive reveal as the user scrolls
- Agency landing pages demonstrating web design capabilities
- Product update announcements with new feature screenshots

## When NOT to Use
- On mobile-only audiences where the MacBook frame loses relevance
- When the product is a mobile app (use a phone frame instead)
- For text-focused pages where scroll animation interrupts reading flow

## Pairs Well With
- `gradient-text` - Animated headline above the MacBook reveal
- `blur-text` - Tagline text entrance before the laptop opens
- `aurora` - Aurora glow behind the MacBook for ambient atmosphere
- `marquee` - Client logos scrolling below the product showcase

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| src | string | - | URL of the product image displayed on the MacBook screen |
| title | ReactNode | - | Title content above the MacBook animation |
| showGradient | boolean | true | Show gradient overlay on the screen |
| badge | ReactNode | - | Badge element shown on the laptop |

## Installation
```bash
npx aceternity-ui@latest add macbook-scroll
```

## Usage Example
```jsx
import { MacbookScroll } from "@/components/ui/macbook-scroll";

export function ProductReveal() {
  return (
    <section className="bg-[#0a0a0a] overflow-hidden">
      <MacbookScroll
        src="/product/clinic-dashboard.webp"
        title={
          <h2 className="font-[Manrope] font-800 text-5xl text-white text-center">
            Meet Your New{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Command Center
            </span>
          </h2>
        }
        showGradient
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Product screenshot should be 2880x1800px WebP for Retina-quality display
- Use #0a0a0a background for seamless dark frame integration
- Title uses Manrope 800 at 5xl with `from-[#ff642a] to-[#ff0301]` gradient
- Gradient overlay color can be customized to match the brand orange
- Ensure `overflow: hidden` on section to prevent horizontal scroll in GHL

## Performance Notes
- Scroll animation uses `useScroll` and `useTransform` for efficient scroll-driven motion
- Product image is the main payload; use optimized WebP and consider `priority` loading
- 3D lid rotation is GPU-composited via CSS `transform: rotateX()`
- Section height is typically 200-300vh for smooth animation pacing
- Single animation timeline with no repeated calculations per frame
