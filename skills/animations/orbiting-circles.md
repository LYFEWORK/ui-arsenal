---
name: orbiting-circles
source: Magic UI
source_url: https://magicui.design/docs/components/orbiting-circles
category: animations
tags: orbit, circle, rotation, icons, animated
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# OrbitingCircles

> Icons or elements that orbit around a central point in smooth circular motion.

## When to Use
- Feature hubs showing capabilities orbiting a core product
- Integration showcases with partner logos circling the main product
- Tech stack displays with tools orbiting a central framework
- Hero sections with a visual anchor surrounded by moving elements
- "How it works" sections showing connected concepts

## When NOT to Use
- Dense content areas where orbiting elements distract from text
- Mobile viewports where the orbit radius is too large
- Sections with many elements (>8 items creates visual chaos)
- When a static grid layout would communicate the same information

## Pairs Well With
- `spotlight-card` - Central card with orbiting feature icons
- `gradient-text` - Gradient text for the central label
- `particles` - Subtle particle field behind the orbiting area
- `animated-content` - Fade in before the orbit animation starts

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element to orbit (icon, image, etc.) |
| radius | number | 50 | Orbit radius in pixels |
| duration | number | 20 | Full orbit cycle duration in seconds |
| delay | number | 0 | Animation start delay in seconds |
| reverse | boolean | false | Reverse orbit direction |
| path | boolean | true | Show the circular orbit path |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/orbiting-circles"
```

## Usage Example
```jsx
import { OrbitingCircles } from "@/components/magicui/orbiting-circles";

export function IntegrationHub() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-16">
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Lyfework
        </span>{" "}
        connects everything
      </h2>
      <div className="relative flex h-[500px] w-full items-center justify-center">
        <span className="font-manrope font-800 text-2xl text-white z-10">LW</span>

        <OrbitingCircles radius={120} duration={25}>
          <img src="/icons/ghl.svg" alt="GoHighLevel" className="w-10 h-10" />
        </OrbitingCircles>
        <OrbitingCircles radius={120} duration={25} delay={8}>
          <img src="/icons/stripe.svg" alt="Stripe" className="w-10 h-10" />
        </OrbitingCircles>
        <OrbitingCircles radius={120} duration={25} delay={16}>
          <img src="/icons/calendar.svg" alt="Calendar" className="w-10 h-10" />
        </OrbitingCircles>

        <OrbitingCircles radius={220} duration={35} reverse>
          <img src="/icons/slack.svg" alt="Slack" className="w-8 h-8" />
        </OrbitingCircles>
        <OrbitingCircles radius={220} duration={35} delay={12} reverse>
          <img src="/icons/zapier.svg" alt="Zapier" className="w-8 h-8" />
        </OrbitingCircles>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Place the Lyfework logo or "LW" monogram at the center with Manrope font-800
- Use integration partner icons (GHL, Stripe, Zapier) as orbiting elements
- Orbit path color can be set to `border-white/10` for subtle visibility on `#0a0a0a`
- Multiple orbit rings with different radii create depth (inner fast, outer slow)
- GHL compatible — CSS `@keyframes rotate` animation, no Web Components

## Performance Notes
- CSS `@keyframes` animation — fully GPU composited via `transform: rotate()`
- Each orbiting element is a single animated container — lightweight
- Multiple orbits (6-8 elements) have negligible combined CPU cost
- Animation runs continuously — consider `prefers-reduced-motion` support
- No JavaScript animation loops — purely declarative CSS
