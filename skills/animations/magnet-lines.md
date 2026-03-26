---
name: magnet-lines
source: ReactBits
source_url: https://reactbits.dev/animations/magnet-lines
category: animations
tags: magnet, lines, cursor, interactive, field, generative
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# MagnetLines

> Lines that dynamically attract toward or repel from the cursor like a magnetic field, creating a generative art background that responds to user movement.

## When to Use

- Hero section backgrounds that react to cursor movement for an interactive first impression
- Agency portfolio pages where the background itself demonstrates creative capability
- "About us" or team pages where the magnetic field adds visual energy
- Conference or event landing pages where interactivity creates engagement
- Full-screen loading or transition states with ambient interactivity

## When NOT to Use

- Mobile-first pages (no cursor to interact with)
- Text-heavy sections where the moving lines distract from reading
- E-commerce pages where focus should be on products, not backgrounds
- Pages requiring fast TTI since the line calculations add to initial load

## Pairs Well With

- `blur-text` - Interactive magnetic background behind a blur-reveal headline
- `split-text` - SplitText headline over magnetic lines for a dynamic hero
- `ghost-cursor` - Magnetic lines reacting to the cursor plus a ghost trail following it
- `animated-content` - Content sections animate in while the magnetic background is always active

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| lineCount | number | 40 | Number of lines in the field |
| color | string | "rgba(255,100,42,0.2)" | Line stroke color |
| lineWidth | number | 1 | Thickness of each line in pixels |
| magnetRadius | number | 150 | Radius of cursor influence in pixels |
| force | "attract" \| "repel" | "attract" | Whether lines pull toward or push from cursor |
| strength | number | 0.5 | Force strength (0-1) |
| orientation | "vertical" \| "horizontal" \| "radial" | "vertical" | Base line orientation |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MagnetLines-TS-TW
```

## Usage Example

```jsx
import MagnetLines from '@/components/ui/MagnetLines';

function AgencyHero() {
  return (
    <section className="relative bg-[#0a0a0a] min-h-screen flex items-center font-[Manrope]">
      <div className="absolute inset-0">
        <MagnetLines
          lineCount={50}
          color="rgba(255,100,42,0.15)"
          magnetRadius={180}
          force="attract"
          strength={0.6}
          orientation="vertical"
        />
      </div>
      <div className="relative z-10 max-w-4xl mx-auto px-8">
        <h1 className="text-6xl font-bold text-white leading-tight">
          We build websites that{' '}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            convert
          </span>
        </h1>
        <p className="mt-6 text-xl text-gray-400 max-w-xl">
          Premium web design and development for brands that refuse to blend in.
        </p>
        <div className="mt-10 flex gap-4">
          <button className="px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
            View Work
          </button>
          <button className="px-8 py-3 rounded-[8px] border border-gray-700 text-white font-bold">
            Contact Us
          </button>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use `rgba(255,100,42,0.15)` for brand-tinted lines that are visible but not overwhelming on `#0a0a0a`.
- Keep `lineCount` between 30-50 for desktop; anything higher can feel too dense.
- Set `force="attract"` for a welcoming feel or `"repel"` for a more dramatic, explosive vibe.
- The magnetic field container should be `absolute inset-0` with content layered above at `z-10`.
- GHL embeds: cursor tracking binds to the component container, not the window, so it works in iframes.
- All text above the field should use Manrope with sufficient contrast (`text-white` or `text-gray-300`).

## Performance Notes

- Uses `canvas` for line rendering -- handles 50+ lines at 60fps efficiently
- `requestAnimationFrame` drives the cursor-tracking update loop
- Each line calculation is O(1) distance check, so total cost is O(n) where n = `lineCount`
- Automatically pauses rendering when the component is off-screen via IntersectionObserver
- On touch devices, falls back to a static line pattern or responds to touch position
