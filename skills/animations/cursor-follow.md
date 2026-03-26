---
name: cursor-follow
source: Animate UI
source_url: https://animate-ui.com/docs/components/animations/cursor-follow
category: animations
tags: cursor, follow, custom cursor, spring, pointer, interactive
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# CursorFollow

> Custom animated cursor element that follows the mouse pointer with spring physics, creating a trailing or enhanced cursor effect.

## When to Use
- Portfolio or agency sites where the cursor IS part of the design experience
- Hero sections with interactive cursor effects (glow, dot, ring)
- Product demos where cursor enhancement guides user attention
- Creative landing pages with playful, art-directed interactions
- Hover-intensive pages where cursor feedback adds interactivity depth

## When NOT to Use
- Mobile-only layouts where custom cursors are irrelevant
- Accessibility-focused contexts where custom cursors cause confusion
- Text-heavy content pages where cursor effects distract from reading
- Forms and input-heavy interfaces where cursor precision matters
- Sites where users rely on system cursor for familiarity

## Pairs Well With
- `button-magnetic` - magnetic button attraction combined with custom cursor creates cohesive interaction
- `spotlight-card` - cursor glow intensifies as it enters spotlight card boundaries
- `aurora` - custom cursor trailing over aurora background for immersive hero
- `tilted-card` - cursor transforms as it enters the tilt zone of cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Custom cursor element content |
| className | string | — | Cursor element CSS classes |
| springConfig | SpringConfig | { stiffness: 500, damping: 28 } | Spring physics configuration |
| offset | { x: number; y: number } | { x: 0, y: 0 } | Cursor position offset |
| hideSystemCursor | boolean | false | Hide the default system cursor |
| scale | number | 1 | Cursor element scale |
| mixBlendMode | string | — | CSS mix-blend-mode for visual effects |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/cursor-follow"
```

## Usage Example
```jsx
import { CursorFollow } from "@/components/ui/cursor-follow";

export function PortfolioHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <CursorFollow
        className="pointer-events-none fixed z-50"
        springConfig={{ stiffness: 400, damping: 25 }}
        hideSystemCursor
      >
        <div className="w-8 h-8 rounded-full border-2 border-[#ff642a] mix-blend-difference" />
      </CursorFollow>

      <div className="text-center space-y-6">
        <h1 className="font-manrope font-800 text-7xl text-white">
          Creative Studio
        </h1>
        <p className="font-manrope font-400 text-gray-400 text-xl">
          We design experiences that move people
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Cursor ring: `border-2 border-[#ff642a]` for brand-colored cursor outline
- Use `mix-blend-difference` for cursor that inverts on light/dark content
- Keep `springConfig` stiffness at 400-500 for responsive but smooth trailing
- Cursor element must be `pointer-events-none fixed z-50` to avoid blocking clicks
- GHL compatible — custom cursor renders as a fixed-position div, no conflicts
- Consider scaling cursor up on interactive elements and down on text

## Performance Notes
- Uses framer-motion's useMotionValue for optimal mouse tracking performance
- Spring calculation runs per frame but is lightweight (two values: x, y)
- Fixed positioning avoids layout recalculation — pure transform updates
- Hide system cursor via CSS `cursor: none` — no additional JS
- Auto-disables on touch devices — no wasted mobile computation
