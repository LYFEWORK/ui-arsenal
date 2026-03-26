---
name: 3d-card-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/3d-card-effect
category: components
tags: 3d, card, tilt, perspective, hover, interactive, depth
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# 3dCardEffect

> Perspective tilt card with elevated floating children that respond to mouse position, creating depth and interactivity.

## When to Use
- Showcasing SaaS pricing cards with premium feel
- Building portfolio project cards with layered depth
- Creating product feature highlights with floating icons
- Displaying team member cards with elevated avatar photos
- Adding dimensionality to testimonial or case study cards

## When NOT to Use
- For content-heavy cards where tilt distracts from reading
- On touch-only mobile experiences without gyroscope fallback
- When accessibility requires completely static layouts

## Pairs Well With
- `spotlight-card` - Layer spotlight glow under the 3D tilt effect
- `gradient-text` - Use gradient headings inside the floating card layers
- `blur-text` - Animate card titles on viewport entry
- `animated-content` - Stagger card entrance animations in a grid

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Card content with CardBody and CardItem children |
| className | string | - | Additional classes for the card container |
| containerClassName | string | - | Classes for the outer perspective wrapper |

## Installation
```bash
npx aceternity-ui@latest add 3d-card-effect
```

## Usage Example
```jsx
import { CardContainer, CardBody, CardItem } from "@/components/ui/3d-card";

export function SaaSFeatureCards() {
  return (
    <section className="bg-[#0a0a0a] py-20 px-6">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-6xl mx-auto">
        <CardContainer className="inter-var">
          <CardBody className="lyf-glass rounded-[12px] p-8 border border-white/10 w-full">
            <CardItem translateZ="50" className="w-full">
              <h3 className="font-[Manrope] font-800 text-2xl text-white">AI Analytics</h3>
            </CardItem>
            <CardItem translateZ="60" className="mt-4">
              <p className="font-[Manrope] font-400 text-neutral-400">
                Real-time insights powered by machine learning for your clinic dashboard.
              </p>
            </CardItem>
            <CardItem translateZ="100" className="mt-6 w-full">
              <img src="/features/analytics.webp" alt="Analytics" className="rounded-[8px] w-full" />
            </CardItem>
            <CardItem translateZ="40" className="mt-6">
              <button className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-6 py-2 rounded-[8px]">
                Learn More
              </button>
            </CardItem>
          </CardBody>
        </CardContainer>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `lyf-glass` on CardBody with `border border-white/10` for Lyfework glass card style
- Set `rounded-[12px]` on cards, `rounded-[8px]` on buttons per design system
- Apply Manrope 800 for card headings, 400 for body text
- Use `translateZ` values of 40-100 for subtle-to-dramatic depth layering
- Test in GHL iframe context to ensure perspective origin works correctly within embedded layouts

## Performance Notes
- GPU-accelerated via CSS 3D transforms, minimal CPU overhead
- Mouse tracking uses passive event listeners for smooth 60fps
- Each card creates its own stacking context, safe for z-index management
- Disable tilt on mobile with `useMotionValue` check for touch devices
- Image children should use `loading="lazy"` to avoid blocking the tilt calculation
