---
name: pixel-transition
source: ReactBits
source_url: https://reactbits.dev/animations/pixel-transition
category: animations
tags: transition, pixel, page, section, reveal, dramatic
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# PixelTransition

> A full-screen pixel dissolve transition between two states. Content breaks apart into pixels and reassembles into new content. Used for page transitions or dramatic section reveals.

## When to Use

- Page-to-page transitions on single-page React apps
- Hero section content swaps (before/after states)
- Portfolio project reveals (thumbnail dissolves into full view)
- Launch or reveal moments where maximum drama is the goal
- Section transitions on scroll for storytelling layouts

## When NOT to Use

- Standard multi-page websites (transition won't persist across page loads)
- Frequent transitions (the effect is dramatic and should be rare)
- Content-heavy pages where the transition delays access to info
- Mobile (pixel count makes it heavy on phones)

## Pairs Well With

- `hyperspeed` - Hyperspeed background dissolves via pixel transition into content
- `blur-text` - After pixel transition resolves, text blur-reveals
- `particles` - Pixels dissolve into a particle field

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| firstContent | ReactNode | required | Initial state content |
| secondContent | ReactNode | required | Target state content |
| gridSize | number | 7 | Pixel grid density |
| duration | number | 1500 | Transition duration in ms |
| trigger | "click" \| "scroll" \| "auto" | "click" | What triggers the transition |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PixelTransition-TS-TW
```

## Usage Example

```jsx
import PixelTransition from '@/components/ui/PixelTransition';

function HeroReveal() {
  return (
    <PixelTransition
      firstContent={
        <div className="flex items-center justify-center h-screen bg-[#0a0a0a]">
          <h1 className="text-7xl font-extrabold text-white">Before</h1>
        </div>
      }
      secondContent={
        <div className="flex items-center justify-center h-screen bg-gradient-to-br from-[#ff642a] to-[#ff0301]">
          <h1 className="text-7xl font-extrabold text-white">After</h1>
        </div>
      }
      gridSize={8}
      duration={1200}
      trigger="click"
    />
  );
}
```

## Lyfework Customization Notes

- Tier 3 showcase only. One per site maximum.
- `gridSize` of 6-10. Lower = larger pixels (more dramatic). Higher = finer (more subtle).
- `duration` of 1000-2000ms. Below 800ms feels rushed. Above 2500ms tests patience.
- Best for single-page React builds, not GHL
- Consider pairing with a sound effect for maximum impact (optional)

## Performance Notes

- Canvas-based pixel manipulation
- Can be heavy on low-end devices at high gridSize
- Reduce gridSize on mobile
- Only runs during the transition (no idle cost)
