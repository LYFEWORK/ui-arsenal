---
name: dotted-map
source: Magic UI
source_url: https://magicui.design/docs/components/dotted-map
category: components
tags: map, global, dots, locations, geography
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# DottedMap

> Animated world map composed of dots with highlighted location pins for showcasing global presence.

## When to Use
- Showing global client or office locations
- "Trusted worldwide" sections on SaaS landing pages
- Visualizing server/CDN distribution points
- Displaying clinic network locations across regions
- Conference or event location displays

## When NOT to Use
- When precise geographic accuracy is required (use a real map library)
- Interactive maps needing zoom/pan/click functionality
- Small viewport areas where dots become indistinguishable
- When only 1-2 locations exist (overkill for simple location display)

## Pairs Well With
- `particles` - Subtle particle background behind the map
- `count-up` - Animated stats like "50+ countries" next to the map
- `aurora` - Aurora background glow beneath the map section
- `animated-content` - Fade in map and location pins sequentially

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| dots | Array | [] | Array of {lat, lng, color} location objects |
| lineColor | string | "#0ea5e9" | Color for connection lines between dots |
| theme | "light" \| "dark" | "dark" | Map background theme |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/dotted-map"
```

## Usage Example
```jsx
import { DottedMap } from "@/components/magicui/dotted-map";

const clinicLocations = [
  { lat: 40.7128, lng: -74.006, color: "#ff642a" },  // New York
  { lat: 51.5074, lng: -0.1278, color: "#ff642a" },   // London
  { lat: 25.2048, lng: 55.2708, color: "#ff0301" },   // Dubai
  { lat: -33.8688, lng: 151.2093, color: "#ff0301" }, // Sydney
];

export function GlobalPresence() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-4xl text-white mb-4">
        Clinics{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          worldwide
        </span>
      </h2>
      <p className="text-center font-manrope font-400 text-white/60 mb-16">
        Powering patient experiences across 4 continents
      </p>
      <div className="mx-auto max-w-5xl">
        <DottedMap dots={clinicLocations} theme="dark" lineColor="#ff642a" />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `#ff642a` and `#ff0301` for dot colors to match the brand gradient
- Set `lineColor` to `#ff642a` for connection lines between locations
- Dark theme blends seamlessly with `#0a0a0a` backgrounds
- Wrap in a `lyf-glass` container with `rounded-[12px]` for card-style presentation
- GHL compatible — SVG-based rendering without Shadow DOM conflicts

## Performance Notes
- SVG-based rendering is lightweight compared to canvas-based map libraries
- Dot count scales linearly — hundreds of dots remain performant
- Animation uses CSS transforms, not JavaScript frame loops
- Consider lazy loading if the map section is below the fold
- No external tile server requests — fully self-contained
