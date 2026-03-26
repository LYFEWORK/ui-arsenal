---
name: grid-scan
source: ReactBits
source_url: https://reactbits.dev/backgrounds/grid-scan
category: backgrounds
tags: background, grid, scan, line, tech, futuristic, animated
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GridScan

> A grid pattern background with a scanning line that sweeps across it, creating a futuristic radar/tech aesthetic. Ideal for tech-forward SaaS and developer tool pages.

## When to Use

- Developer tool or API product landing pages
- Tech company hero sections for a futuristic feel
- Dashboard preview sections where a "scanning" effect adds dynamism
- AI/ML product pages where the scanning line suggests analysis
- Cybersecurity or monitoring product pages

## When NOT to Use

- Warm, organic, or lifestyle brand pages (too cold and techy)
- Medical or clinic sites (feels too sci-fi for healthcare)
- Content-heavy pages where the scanning line becomes a distraction
- Sections visited repeatedly (the scan loop gets repetitive)

## Pairs Well With

- `count-up` - Metrics animating as the scan line passes over them feels integrated
- `animated-content` - Content appearing in sync with the scan line creates a reveal effect
- `gradient-text` - Tech-colored gradient text over the grid reinforces the theme
- `spotlight-card` - Cards over the scanned grid feel like data panels

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| gridSize | number | 40 | Size of each grid cell in pixels |
| gridColor | string | "rgba(255,255,255,0.05)" | Color of the grid lines |
| scanColor | string | "#00ff88" | Color of the scanning line |
| scanWidth | number | 2 | Width of the scan line in pixels |
| scanSpeed | number | 3 | Seconds for one full scan pass |
| direction | string | "vertical" | Scan direction: "vertical" or "horizontal" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GridScan-TS-TW
```

## Usage Example

```jsx
import GridScan from '@/components/ui/GridScan';
import GradientText from '@/components/ui/GradientText';

function AIProductHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <GridScan
          gridSize={48}
          gridColor="rgba(255,100,42,0.04)"
          scanColor="#ff642a"
          scanWidth={2}
          scanSpeed={4}
          direction="vertical"
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <GradientText
          colors={['#ff642a', '#ff0301', '#ff642a']}
          className="text-5xl md:text-7xl font-extrabold font-[Manrope]"
        >
          Intelligence, Deployed.
        </GradientText>
        <p className="mt-6 text-lg text-gray-400 max-w-2xl mx-auto font-[Manrope]">
          AI-powered automation that watches, learns, and acts.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework scan color: `#ff642a` with grid `rgba(255,100,42,0.04)` for brand-tinted tech look
- `scanSpeed` of 3-5 seconds feels deliberate and professional. Under 2s feels frantic.
- `gridSize` of 40-60px works for most sections. Smaller grids feel busy, larger feels sparse.
- For client SaaS builds: match `scanColor` to their primary accent
- GHL: the grid can be a CSS `repeating-linear-gradient`, scan line as a CSS keyframe animation
- Combine with `lyf-glass` cards for a dashboard-style layout over the scanning grid

## Performance Notes

- Grid is a pure CSS `repeating-linear-gradient`, zero JS overhead
- Scan line is a single element with a CSS translateY/translateX animation
- Extremely lightweight, safe for all devices
- The glow effect on the scan line uses `box-shadow`, may cause minor repaints
- SSR-compatible, grid renders immediately, scan animates on client
