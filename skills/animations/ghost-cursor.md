---
name: ghost-cursor
source: ReactBits
source_url: https://reactbits.dev/animations/ghost-cursor
category: animations
tags: cursor, ghost, trail, follow, opacity, interactive
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GhostCursor

> A ghostly cursor trail that follows the user's mouse with fading opacity echoes, adding a premium interactive layer to any page.

## When to Use

- Portfolio or creative agency sites where the cursor itself is part of the design
- SaaS landing pages to make the browsing experience feel custom and polished
- Event or launch pages where every detail should feel crafted
- Dark-themed hero sections where the ghost trail contrasts beautifully
- Interactive showcase pages where cursor behavior demonstrates attention to detail

## When NOT to Use

- E-commerce product pages where the cursor trail competes with "Add to Cart" actions
- Form-heavy pages where ghost trails over input fields feel distracting
- Accessibility-focused builds where custom cursors can confuse assistive tech
- Pages targeting older browsers or low-spec devices

## Pairs Well With

- `click-spark` - Ghost trail on move, spark on click for a full cursor experience
- `aurora` - Ghost cursor floating over aurora backgrounds creates a dreamy atmosphere
- `particles` - Cursor trail weaving through particles enhances the interactive depth
- `spotlight-card` - The ghost trail adds motion between spotlight-illuminated cards

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#ff642a" | Trail ghost color |
| trailLength | number | 8 | Number of ghost echoes |
| fadeSpeed | number | 0.85 | Opacity decay rate per echo (0-1) |
| size | number | 24 | Ghost cursor diameter in pixels |
| shape | "circle" \| "square" \| "ring" | "circle" | Shape of each ghost echo |
| blendMode | string | "screen" | CSS mix-blend-mode for the trail |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GhostCursor-TS-TW
```

## Usage Example

```jsx
import GhostCursor from '@/components/ui/GhostCursor';

function PortfolioPage() {
  return (
    <div className="relative min-h-screen bg-[#0a0a0a] font-[Manrope]">
      <GhostCursor
        color="#ff642a"
        trailLength={6}
        fadeSpeed={0.8}
        size={20}
        shape="circle"
      />
      <section className="max-w-5xl mx-auto py-24 px-8">
        <h1 className="text-5xl font-bold text-white">
          Creative builds by{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Lyfework
          </span>
        </h1>
        <p className="mt-6 text-lg text-gray-400">
          Move your cursor. Every pixel is intentional.
        </p>
        <div className="grid grid-cols-2 gap-8 mt-16">
          <div className="lyf-glass rounded-[12px] p-8">
            <h3 className="text-white font-bold">Clinic Redesign</h3>
            <p className="text-gray-400 mt-2">Full rebrand for a dental practice.</p>
          </div>
          <div className="lyf-glass rounded-[12px] p-8">
            <h3 className="text-white font-bold">SaaS Dashboard</h3>
            <p className="text-gray-400 mt-2">Analytics platform UI overhaul.</p>
          </div>
        </div>
      </section>
    </div>
  );
}
```

## Lyfework Customization Notes

- Set `color="#ff642a"` to match the Lyfework brand; the orange ghost trail pops on `#0a0a0a`.
- Use `blendMode="screen"` on dark backgrounds for a glowing effect; switch to `"multiply"` on light backgrounds.
- Keep `trailLength` at 6-8 for smooth motion. More than 10 looks jittery on 60Hz displays.
- The ghost trail is rendered via a portal at the document root, so it works fine inside `lyf-glass` containers.
- On GHL pages, the cursor events bind to `document.body`; verify the GHL wrapper doesn't intercept `mousemove`.
- Font rendering is unaffected since the trail uses `pointer-events: none` and sits on its own z-layer.

## Performance Notes

- Uses `requestAnimationFrame` for smooth 60fps trail updates
- Each ghost echo is a simple `div` with opacity transition -- no canvas or WebGL
- `pointer-events: none` on all trail elements prevents interaction interference
- Automatically disables on touch devices (no `mousemove` events)
- Memory footprint is fixed: only `trailLength` DOM nodes exist at any time
