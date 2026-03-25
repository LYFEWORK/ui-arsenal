---
name: iridescence
source: ReactBits
source_url: https://reactbits.dev/backgrounds/iridescence
category: backgrounds
tags: background, iridescence, holographic, rainbow, premium, WebGL
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Iridescence

> A holographic, iridescent surface effect that shifts colors based on mouse position. Creates a premium, Apple-like reflective material look. Mouse-interactive.

## When to Use

- Premium product pages where the background should feel like a material
- SaaS or tech product hero sections
- Pricing pages where a premium feel justifies the price point
- Brand pages that need to feel modern and high-end
- Alternative to Aurora when you want something more structured

## When NOT to Use

- Warm or organic brand aesthetics (iridescence feels cold/tech)
- Behind complex content layouts (the shifting colors distract)
- Multiple sections (one iridescent area per page)
- Conservative verticals

## Pairs Well With

- `blur-text` - Text revealing over iridescent surface
- `split-text` - GSAP text over shifting holographic background
- `glow-card` - Glass cards floating over iridescent surface
- `spotlight-card` - Spotlight cards on iridescent hero

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | [number,number,number] | [1,1,1] | Base RGB color multiplier |
| speed | number | 1 | Color shift speed |
| mouseInteraction | boolean | true | Respond to cursor position |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Iridescence-TS-TW
```

## Usage Example

```jsx
import Iridescence from '@/components/ui/Iridescence';

function PremiumHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <Iridescence color={[1.0, 0.4, 0.2]} speed={0.8} mouseInteraction={true} />
      </div>
      <div className="relative z-10 text-center">
        <h1 className="text-6xl font-extrabold text-white drop-shadow-lg">Premium Infrastructure.</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Base color `[1.0, 0.4, 0.2]` gives warm orange-tinted iridescence for Lyfework
- `speed` of 0.5-1.0. Slow shifts feel more premium.
- Mouse interaction adds the "Apple product page" feel
- Add `drop-shadow-lg` on text for readability over shifting colors
- Not for GHL (WebGL canvas)

## Performance Notes

- WebGL shader-based (GPU accelerated)
- Smooth on modern hardware
- Add feature detection and fallback gradient for older devices
- Desktop-focused, reduce quality on mobile
