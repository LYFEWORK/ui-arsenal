---
name: radar
source: ReactBits
source_url: https://reactbits.dev/backgrounds/radar
category: backgrounds
tags: background, radar, sweep, scan, rotating, tech, circular
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Radar

> A rotating radar sweep scan animation with concentric rings and a sweeping beam. Creates a surveillance/monitoring tech aesthetic for dashboards and data-driven pages.

## When to Use

- Monitoring or analytics dashboard landing pages
- Cybersecurity product pages for a surveillance aesthetic
- Location-based service or geolocation product pages
- Tech startup hero sections with a "scanning for opportunities" theme
- Behind map or data visualization sections

## When NOT to Use

- Warm, friendly, or approachable brand pages (too cold and militaristic)
- Clinic or healthcare sites (surveillance aesthetic is inappropriate)
- Content-heavy pages where the rotating sweep distracts
- Sections shorter than 400px height (the circular pattern needs space)

## Pairs Well With

- `count-up` - Metrics appearing as the radar sweep passes over them
- `animated-content` - Data points revealing as the radar scans the section
- `gradient-text` - Tech-colored gradient text complements the radar aesthetic
- `dot-grid` - Dot grid underneath the radar creates a layered tech background

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#00ff88" | Color of the radar sweep and rings |
| ringCount | number | 4 | Number of concentric rings |
| sweepSpeed | number | 3 | Seconds for one full sweep rotation |
| dotCount | number | 8 | Number of "blip" dots on the radar |
| size | number | 500 | Diameter of the radar in pixels |
| opacity | number | 0.3 | Overall opacity of the radar |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Radar-TS-TW
```

## Usage Example

```jsx
import Radar from '@/components/ui/Radar';
import CountUp from '@/components/ui/CountUp';

function AnalyticsDashboardHero() {
  return (
    <section className="relative min-h-[80vh] flex items-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0 flex items-center justify-center">
        <Radar
          color="#ff642a"
          ringCount={5}
          sweepSpeed={4}
          dotCount={6}
          size={600}
          opacity={0.2}
        />
      </div>

      <div className="relative z-10 max-w-4xl mx-auto px-8 text-center">
        <h1 className="text-4xl md:text-6xl font-bold text-white font-[Manrope]">
          Always Watching. Always Optimizing.
        </h1>
        <p className="mt-6 text-lg text-gray-300 font-[Manrope]">
          Real-time monitoring for your entire digital ecosystem.
        </p>
        <div className="mt-12 flex justify-center gap-12">
          <div>
            <CountUp end={99.9} suffix="%" decimals={1} className="text-4xl font-bold text-[#ff642a]" />
            <p className="mt-1 text-gray-400 text-sm">Uptime</p>
          </div>
          <div>
            <CountUp end={24} suffix="/7" className="text-4xl font-bold text-[#ff642a]" />
            <p className="mt-1 text-gray-400 text-sm">Monitoring</p>
          </div>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework radar: `color="#ff642a"` at `opacity={0.15-0.25}` for a warm tech look
- `sweepSpeed` of 3-5 seconds feels deliberate and professional. Under 2s feels frantic.
- The concentric rings work best at `ringCount` of 3-5 with thin stroke widths
- For SaaS client builds: match radar color to their primary accent
- GHL: the rings can be CSS `border-radius: 50%` borders, sweep via CSS `conic-gradient` rotation
- Center the radar behind the main content block for natural visual anchoring

## Performance Notes

- CSS-based rotation animation on a conic-gradient element
- Concentric rings are simple border-radius elements, zero overhead
- The blip dots can be animated with CSS keyframes for appearance/fade
- Lightweight overall, safe for all devices
- SSR-compatible, renders static rings and animates the sweep on client
