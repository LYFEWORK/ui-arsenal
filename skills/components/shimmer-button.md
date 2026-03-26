---
name: shimmer-button
source: Magic UI
source_url: https://magicui.design/docs/components/shimmer-button
category: components
tags: button, shimmer, shine, sweep, cta
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# ShimmerButton

> Button with a sweeping shimmer/shine animation that glides across the surface continuously.

## When to Use
- Primary hero CTA buttons that need premium feel
- "Get started" buttons on SaaS landing pages
- Pricing card action buttons
- Download or signup buttons on product pages
- Anywhere a button needs to feel polished and alive

## When NOT to Use
- Multiple shimmer buttons competing on the same section
- Subtle or minimal UI where shimmer feels excessive
- Secondary/tertiary actions that should be visually quiet
- When shimmer-button is already paired with pulsating-button (pick one)

## Pairs Well With
- `gradient-text` - Gradient heading leading to the shimmer CTA
- `animated-content` - Scroll-reveal the shimmer button
- `aurora` - Aurora background behind the CTA section
- `spotlight-card` - Shimmer button inside a spotlight card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Button label content |
| className | string | "" | Additional CSS classes |
| shimmerColor | string | "#ffffff" | Color of the shimmer sweep |
| shimmerSize | string | "0.05em" | Size of the shimmer spread |
| shimmerDuration | string | "3s" | Duration of the shimmer animation cycle |
| background | string | "rgba(0,0,0,1)" | Button background color |
| borderRadius | string | "100px" | Border radius of the button |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/shimmer-button"
```

## Usage Example
```jsx
import { ShimmerButton } from "@/components/magicui/shimmer-button";

export function HeroSection() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <h1 className="font-manrope font-800 text-5xl text-white mb-6">
        Grow your practice with{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Lyfework
        </span>
      </h1>
      <p className="font-manrope font-400 text-white/60 text-lg mb-12 max-w-lg mx-auto">
        The all-in-one platform for modern clinics.
      </p>
      <ShimmerButton
        shimmerColor="#ff642a"
        background="linear-gradient(135deg, #ff642a, #ff0301)"
        borderRadius="8px"
        className="font-manrope font-700 px-10 py-4 text-lg text-white"
      >
        Start free trial
      </ShimmerButton>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `shimmerColor="#ff642a"` for brand-consistent shine
- Use `background="linear-gradient(135deg, #ff642a, #ff0301)"` for gradient fill
- Override `borderRadius="8px"` to match button convention
- Manrope font-700 for button text at appropriate size
- GHL compatible — CSS animation with pseudo-elements, no JS dependencies

## Performance Notes
- CSS `@keyframes` animation — zero JavaScript overhead
- Shimmer uses `transform: translateX()` — GPU composited
- Single shimmer sweep per cycle is lightweight
- Animation respects `prefers-reduced-motion` when properly configured
- No DOM manipulation — shimmer is a CSS pseudo-element overlay
