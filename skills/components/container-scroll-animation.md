---
name: container-scroll-animation
source: Aceternity UI
source_url: https://ui.aceternity.com/components/container-scroll-animation
category: components
tags: scroll, macbook, product, reveal, animation, showcase, hero
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# ContainerScrollAnimation

> MacBook-style scroll reveal animation for product showcases, with a device frame that scales and reveals content as the user scrolls.

## When to Use
- Product launch hero sections showing a dashboard or app interface
- SaaS landing pages showcasing the product in a device frame
- Portfolio pieces displaying web design work in context
- AI tool demos where the product reveal builds anticipation
- Agency case study pages showing before/after results

## When NOT to Use
- For text-heavy content pages where scroll hijacking frustrates users
- On pages with multiple scroll-based sections competing for attention
- When the target audience is primarily mobile (device frame loses impact)

## Pairs Well With
- `gradient-text` - Animated headline above the scroll reveal
- `aurora` - Aurora background behind the device showcase
- `blur-text` - Fade in the section tagline as the device appears
- `animated-content` - Stagger feature bullets alongside the reveal

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| titleComponent | ReactNode | - | Content displayed above the device frame |
| children | ReactNode | - | Content displayed inside the device screen |
| className | string | - | Additional classes for the container |

## Installation
```bash
npx aceternity-ui@latest add container-scroll-animation
```

## Usage Example
```jsx
import { ContainerScroll } from "@/components/ui/container-scroll-animation";

export function ProductShowcase() {
  return (
    <section className="bg-[#0a0a0a]">
      <ContainerScroll
        titleComponent={
          <div className="text-center">
            <p className="font-[Manrope] font-400 text-neutral-400 text-lg mb-2">Introducing</p>
            <h2 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
              Your AI-Powered{" "}
              <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
                Clinic Dashboard
              </span>
            </h2>
          </div>
        }
      >
        <img
          src="/product/dashboard-preview.webp"
          alt="Lyfework Clinic Dashboard"
          className="w-full h-full object-cover rounded-[8px]"
        />
      </ContainerScroll>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use #0a0a0a background to match the dark device frame aesthetic
- Title uses Manrope 800 at 5xl-7xl with the `from-[#ff642a] to-[#ff0301]` gradient
- Product screenshots should be high-res WebP (1920x1080 minimum) for crisp device display
- Apply `rounded-[8px]` to the screen content image for natural device screen corners
- Test scroll behavior in GHL iframe embeds; may need `overflow: visible` on parent container

## Performance Notes
- Scroll animation uses `useScroll` and `useTransform` from framer-motion, highly optimized
- Product image is the heaviest asset; use WebP with `priority` loading for above-fold placements
- 3D transform scale animation is fully GPU-composited
- Consider `will-change: transform` on the device container for smoother Safari performance
- Section height is typically 200-300vh; ensure page length is appropriate for the content
