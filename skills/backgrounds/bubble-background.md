---
name: bubble-background
source: Animate UI
source_url: https://animate-ui.com/docs/components/backgrounds/bubble-background
category: backgrounds
tags: bubbles, particles, ambient, floating, background, organic
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# BubbleBackground

> Floating bubble particles creating a soft ambient background with organic movement and depth through varying sizes and opacities.

## When to Use
- SaaS landing page hero backgrounds for a soft, approachable feel
- About or culture pages where bubbles create a friendly atmosphere
- Wellness or spa clinic sites where organic movement fits the brand
- Loading or transition screens with ambient visual interest
- Light-hearted sections needing subtle background motion

## When NOT to Use
- Corporate or medical sites requiring a serious, clinical aesthetic
- Content-heavy pages where floating bubbles distract from reading
- Mobile-first designs where ambient animations drain battery
- Pages already using another animated background — avoid stacking

## Pairs Well With
- `blur-text` - text reveals over floating bubbles for dreamy hero sections
- `gradient-text` - gradient heading text floating above soft bubble backdrop
- `spotlight-card` - glass cards over bubbles create aquatic depth
- `shimmer-button` - shimmer CTA floating above the bubble field

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| count | number | 20 | Number of bubble particles |
| minSize | number | 4 | Minimum bubble size in pixels |
| maxSize | number | 40 | Maximum bubble size in pixels |
| color | string | "rgba(255,255,255,0.1)" | Bubble color |
| speed | number | 1 | Animation speed multiplier |
| className | string | — | Container CSS classes |
| blur | boolean | true | Apply blur to bubbles for depth effect |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/bubble-background"
```

## Usage Example
```jsx
import { BubbleBackground } from "@/components/ui/bubble-background";

export function WellnessHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <BubbleBackground
        count={25}
        color="rgba(255,100,42,0.08)"
        minSize={6}
        maxSize={50}
        speed={0.7}
        className="absolute inset-0"
      />
      <div className="relative z-10 text-center space-y-6">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Your Wellness Journey Starts Here
        </h1>
        <p className="font-manrope font-400 text-gray-400 text-xl max-w-2xl mx-auto">
          Holistic care tailored to your unique needs
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Bubble color: `"rgba(255,100,42,0.08)"` for subtle brand-tinted bubbles on `#0a0a0a`
- Keep `count` under 30 for performance on lower-end devices
- Set `speed` to 0.7 for a relaxed, premium float feel
- Content should be `relative z-10` to layer above the background
- GHL compatible — CSS-only animation, no JS conflicts with iframe
- Add `overflow-hidden` to parent to prevent bubble overflow

## Performance Notes
- Pure CSS animation with randomized keyframes — no JavaScript runtime
- Each bubble is a single div with border-radius — minimal DOM footprint
- Blur effect uses CSS filter — GPU-accelerated
- Reduce count on mobile via media query or responsive prop
- No continuous JS calculations — set-and-forget CSS animations
