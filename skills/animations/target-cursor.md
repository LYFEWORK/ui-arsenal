---
name: target-cursor
source: ReactBits
source_url: https://reactbits.dev/animations/target-cursor
category: animations
tags: cursor, target, scope, aim, precision, interactive
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# TargetCursor

> A target/crosshair scope overlay that follows the mouse cursor, replacing or augmenting the default cursor with a precision-aimed reticle for a bold, high-impact interactive feel.

## When to Use

- Gaming or esports themed landing pages where the scope cursor fits the brand
- Product launch pages where "targeting" or "precision" is part of the messaging
- Interactive hero sections on tech or dev-tool sites to make browsing feel tactile
- Portfolio sites for photographers or designers where the scope suggests precision
- One-page experiences where cursor customization adds to the immersive feel

## When NOT to Use

- E-commerce checkout flows where custom cursors interfere with purchase actions
- Form pages where the reticle over input fields feels aggressive
- Accessibility-focused builds where replacing the default cursor is problematic
- Multi-page sites where the scope on every page becomes tiresome

## Pairs Well With

- `click-spark` - Target cursor for aiming, spark on click for the "impact" moment
- `particles` - Scope cursor hunting through particles creates a playful interactive scene
- `pixel-trail` - Pixel trail behind the target cursor for a retro-FPS aesthetic
- `magnet-lines` - Lines attract to the scope cursor, creating a magnetic targeting effect

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| size | number | 40 | Diameter of the target reticle in pixels |
| color | string | "#ff642a" | Reticle color |
| strokeWidth | number | 1.5 | Thickness of the crosshair lines |
| innerDot | boolean | true | Show a center dot in the reticle |
| smoothing | number | 0.15 | Cursor follow smoothing factor (0 = instant, 1 = very delayed) |
| hideDefault | boolean | true | Hide the native cursor |
| scale | { hover: number; click: number } | { hover: 1.3, click: 0.8 } | Scale on hover and click |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TargetCursor-TS-TW
```

## Usage Example

```jsx
import TargetCursor from '@/components/ui/TargetCursor';

function ProductLaunchHero() {
  return (
    <div className="relative min-h-screen bg-[#0a0a0a] font-[Manrope]">
      <TargetCursor
        size={44}
        color="#ff642a"
        strokeWidth={1.5}
        innerDot
        smoothing={0.12}
        scale={{ hover: 1.4, click: 0.75 }}
      />
      <section className="relative z-10 flex items-center justify-center min-h-screen px-8">
        <div className="text-center max-w-3xl">
          <p className="text-sm uppercase tracking-widest text-[#ff642a] font-semibold">
            Launching March 2026
          </p>
          <h1 className="mt-4 text-6xl font-bold text-white leading-tight">
            Precision{' '}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Redefined
            </span>
          </h1>
          <p className="mt-6 text-xl text-gray-400">
            Every detail matters. Aim higher.
          </p>
          <button className="mt-10 px-10 py-4 rounded-[12px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg">
            Join Waitlist
          </button>
        </div>
      </section>
    </div>
  );
}
```

## Lyfework Customization Notes

- `color="#ff642a"` keeps the reticle on-brand. The orange crosshair is clearly visible on `#0a0a0a`.
- Set `smoothing={0.1-0.15}` for a fluid follow that feels intentional, not laggy.
- The `scale.hover` at 1.3-1.4 makes the reticle expand over interactive elements, providing implicit hover feedback.
- Use `hideDefault={true}` on the hero section only; restore the default cursor on form sections via conditional rendering.
- GHL pages: custom cursor rendering via a portal at document root works, but test that GHL's own cursor styles don't override.
- Pair with Manrope typography and the brand gradient CTA for a cohesive launch page aesthetic.

## Performance Notes

- Uses a single `div` with SVG crosshair positioned via `transform: translate()` at 60fps
- `requestAnimationFrame` with lerp-based smoothing for fluid movement
- `pointer-events: none` on the reticle prevents interference with page interactions
- Automatically hides on touch devices (no cursor to replace)
- Bundle size: ~2KB (SVG reticle + mouse tracking logic), zero dependencies
