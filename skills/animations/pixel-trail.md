---
name: pixel-trail
source: ReactBits
source_url: https://reactbits.dev/animations/pixel-trail
category: animations
tags: pixel, trail, cursor, retro, interactive, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# PixelTrail

> A pixelated trail effect that follows cursor movement, rendering blocky pixel squares that fade out behind the mouse for a retro-meets-modern interactive layer.

## When to Use

- Creative portfolio sites where the cursor trail reinforces an artistic brand
- Gaming or retro-themed landing pages where pixel aesthetics are on-brand
- Interactive hero sections that make visitors explore by moving the mouse
- Tech or developer-focused sites where the pixel grid feels native
- Event pages or product launches where curiosity-driven interactions boost engagement

## When NOT to Use

- Polished luxury or corporate sites where pixel blocks clash with the premium tone
- Mobile-first builds (cursor trails are desktop-only interactions)
- Form-heavy pages or dashboards where the trail obscures input fields
- Accessibility-critical builds where custom cursor behavior is problematic

## Pairs Well With

- `click-spark` - Pixel trail on move, spark explosion on click for full cursor gamification
- `ghost-cursor` - Choose one or the other; both active at once is too busy
- `particles` - Pixel trail over a particle background creates a layered retro-tech feel
- `split-text` - Retro pixel trail pairs well with a character-by-character text reveal

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| pixelSize | number | 16 | Size of each pixel block in pixels |
| color | string | "#ff642a" | Pixel fill color |
| fadeSpeed | number | 0.9 | Opacity decay rate per frame (0-1) |
| trailLength | number | 30 | Maximum number of pixel blocks in the trail |
| gridSnap | boolean | true | Snap pixels to a grid for crisp alignment |
| rainbow | boolean | false | Cycle through hue values for a rainbow trail |
| className | string | "" | Additional CSS classes on the canvas container |

## Installation

```bash
npx shadcn@latest add @react-bits/PixelTrail-TS-TW
```

## Usage Example

```jsx
import PixelTrail from '@/components/ui/PixelTrail';

function DevToolsLanding() {
  return (
    <div className="relative min-h-screen bg-[#0a0a0a] font-[Manrope]">
      <PixelTrail
        pixelSize={12}
        color="#ff642a"
        fadeSpeed={0.88}
        trailLength={40}
        gridSnap
      />
      <section className="relative z-10 max-w-4xl mx-auto py-32 px-8 text-center">
        <h1 className="text-5xl font-bold text-white">
          Build{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Pixel-Perfect
          </span>{' '}
          Websites
        </h1>
        <p className="mt-6 text-lg text-gray-400">
          Move your cursor around. Every pixel matters.
        </p>
        <div className="mt-12 flex justify-center gap-4">
          <button className="px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
            Get Started
          </button>
          <button className="px-8 py-3 rounded-[8px] border border-gray-700 text-white font-bold">
            View Docs
          </button>
        </div>
      </section>
    </div>
  );
}
```

## Lyfework Customization Notes

- `color="#ff642a"` keeps the pixel trail on-brand. For variation, try `rainbow={true}` on event or launch pages.
- Set `pixelSize={12}` for a refined grid or `pixelSize={20}` for a chunkier retro look.
- The canvas renders full-viewport behind content; layer page sections with `relative z-10`.
- On `#0a0a0a` backgrounds, the orange pixels glow naturally. No additional blend mode needed.
- GHL embeds: canvas binds `mousemove` to its own element, so iframe cursor events should propagate correctly.
- Combine with Manrope bold headings and the brand gradient for a cohesive tech-forward aesthetic.

## Performance Notes

- Canvas-based rendering: one `<canvas>` element handles all pixel drawing
- `requestAnimationFrame` loop clears and redraws only active pixels each frame
- Memory is bounded: maximum `trailLength` pixels tracked at any time
- `gridSnap` quantizes cursor position, reducing the number of unique pixel positions drawn
- Auto-disables on touch devices since there is no cursor to follow
