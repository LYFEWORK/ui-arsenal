---
name: ripple-grid
source: ReactBits
source_url: https://reactbits.dev/backgrounds/ripple-grid
category: backgrounds
tags: background, ripple, grid, distortion, interactive, wave, click
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# RippleGrid

> A grid pattern with ripple distortion waves that spread from cursor position or click events. Creates a reactive, interactive background that responds to user input.

## When to Use

- Interactive hero sections where you want users to "play" with the background
- SaaS product pages to demonstrate responsiveness and interactivity
- Portfolio sections where the ripple reacts to scrolling or clicking
- Behind CTAs to create a satisfying ripple effect on click
- Tech-forward landing pages where interactivity reinforces the product message

## When NOT to Use

- Static, print-like layouts where interaction is unexpected
- Mobile-primary pages where touch ripples may feel sluggish
- Behind forms or input areas where accidental ripples are distracting
- Sections with existing hover/click animations on child elements (interaction conflict)

## Pairs Well With

- `spotlight-card` - Cards over a ripple grid create a double-interactive effect
- `animated-content` - Content appearing over the responsive grid feels layered
- `count-up` - Metrics over a reactive grid reinforce a "data is alive" theme
- `gradient-text` - Gradient text over the grid creates a clean tech aesthetic

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| gridSize | number | 30 | Size of each grid cell in pixels |
| gridColor | string | "rgba(255,255,255,0.08)" | Color of the grid lines |
| rippleColor | string | "#ffffff" | Color of the ripple wave |
| rippleSpeed | number | 0.5 | Speed of the ripple propagation |
| rippleDecay | number | 0.95 | How quickly the ripple fades (0-1) |
| trigger | string | "hover" | Trigger mode: "hover", "click", "both" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/RippleGrid-TS-TW
```

## Usage Example

```jsx
import RippleGrid from '@/components/ui/RippleGrid';
import GradientText from '@/components/ui/GradientText';

function InteractiveHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <RippleGrid
          gridSize={35}
          gridColor="rgba(255,100,42,0.06)"
          rippleColor="#ff642a"
          rippleSpeed={0.6}
          rippleDecay={0.93}
          trigger="hover"
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <GradientText
          colors={['#ff642a', '#ff0301']}
          className="text-5xl md:text-7xl font-extrabold font-[Manrope]"
        >
          Touch the Future.
        </GradientText>
        <p className="mt-6 text-lg text-gray-400 max-w-xl mx-auto font-[Manrope]">
          Interactive infrastructure that responds to every move.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework ripple: `rippleColor="#ff642a"` with grid `rgba(255,100,42,0.06)` for brand warmth
- `trigger="hover"` for desktop hero sections, switch to `trigger="click"` for mobile
- `rippleDecay` of 0.90-0.95 lets ripples spread wide. Below 0.85 and they die too fast.
- `gridSize` of 25-40px works for most section widths. Smaller grids show more detail.
- GHL: the grid is CSS-replicable, but the ripple interaction requires JavaScript
- Pair with `lyf-glass` styled content cards for a cohesive interactive layout

## Performance Notes

- Canvas-based rendering for the ripple wave propagation
- The grid distortion calculation runs per-frame during active ripples
- Performance scales with grid density. Larger `gridSize` values are lighter.
- On mobile, use `trigger="click"` to avoid continuous hover tracking
- SSR-compatible, renders the static grid and enables ripple on client
