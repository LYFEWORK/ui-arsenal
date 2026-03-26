---
name: morph-surface
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/morph-surface
category: components
tags: morph, surface, shape, transition, blob, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# MorphSurface

> Surface that morphs shape between states using smooth border-radius and path animations.

## When to Use
- Decorative background shapes that transition between organic forms
- Feature section dividers with morphing blob boundaries
- Interactive surfaces responding to user state changes
- Creative hero accents with living, breathing shapes
- Loading states with organic shape morphing

## When NOT to Use
- Structured layouts requiring consistent rectangular shapes
- Content containers where morphing edges clip content
- Performance-constrained pages where continuous animation is costly
- Professional/corporate pages where organic shapes feel casual

## Pairs Well With
- `aurora` - Morphing surface with aurora color effects
- `gradient-text` - Text positioned relative to morphing shape
- `particles` - Particles constrained within morphing surface bounds
- `animated-content` - Content that adapts to surface morphing state

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| shapes | string[] | [] | Array of border-radius or SVG path states |
| duration | number | 4 | Morph cycle duration in seconds |
| colors | string[] | ['#ff642a', '#ff0301'] | Surface gradient colors |
| autoMorph | boolean | true | Automatically cycle through shapes |
| ease | string | 'easeInOut' | Animation easing |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/morph-surface"
```

## Usage Example
```jsx
import { MorphSurface } from "@/components/ui/morph-surface";

export function HeroAccent() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a] overflow-hidden">
      <MorphSurface
        shapes={[
          "30% 70% 70% 30% / 30% 30% 70% 70%",
          "70% 30% 30% 70% / 70% 70% 30% 30%",
          "50% 50% 30% 70% / 60% 40% 60% 40%",
        ]}
        duration={6}
        colors={["#ff642a20", "#ff030120"]}
        className="absolute top-1/4 left-1/2 -translate-x-1/2 w-[600px] h-[600px]"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Always Evolving
        </h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use brand colors at 10-20% opacity for subtle background blobs
- Position with absolute + translate for floating accent shapes
- overflow-hidden on parent prevents morphing shape from causing scrollbars
- Manrope 800 headings positioned in z-10 above morphing surface
- Not ideal for GHL embeds -- use static shapes as fallback

## Performance Notes
- Framer Motion animates border-radius with GPU-accelerated transitions
- Gradient background is static; only shape morphs
- Single element animation with no DOM mutation
- Auto-morph uses keyframe cycle -- predictable, low overhead
- Disable on prefers-reduced-motion media query
