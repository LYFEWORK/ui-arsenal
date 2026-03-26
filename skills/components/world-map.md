---
name: world-map
source: Aceternity UI
source_url: https://ui.aceternity.com/components/world-map
category: components
tags: map, world, globe, connections, dots, locations, global
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# WorldMap

> World map visualization with animated dot connections between locations, showing global presence or network reach.

## When to Use
- "Where we operate" sections showing global clinic or office locations
- Network visualization for SaaS platforms with worldwide users
- Supply chain or partner network maps
- Customer distribution displays for investor or about pages
- International service coverage maps

## When NOT to Use
- When only showing 1-2 nearby locations (use a simple map instead)
- For precise geographic data that needs real map coordinates
- When the audience is local-only and global context is irrelevant

## Pairs Well With
- `3d-animated-pin` - Add interactive pins on the world map locations
- `count-up` - Animated stats beside the map ("50+ countries")
- `particles` - Background particles enhancing the global atmosphere
- `aurora` - Northern lights effect behind the map visualization

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| dots | array | - | Array of { start, end } coordinate pairs for connections |
| lineColor | string | "#ff642a" | Color of connection lines |
| className | string | - | Classes for the map container |

## Installation
```bash
npx aceternity-ui@latest add world-map
```

## Usage Example
```jsx
import { WorldMap } from "@/components/ui/world-map";

const connections = [
  { start: { lat: 37.7749, lng: -122.4194 }, end: { lat: 51.5074, lng: -0.1278 } },
  { start: { lat: 37.7749, lng: -122.4194 }, end: { lat: 35.6762, lng: 139.6503 } },
  { start: { lat: 51.5074, lng: -0.1278 }, end: { lat: 1.3521, lng: 103.8198 } },
  { start: { lat: 37.7749, lng: -122.4194 }, end: { lat: -33.8688, lng: 151.2093 } },
];

export function GlobalPresence() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-4">
        Trusted <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Worldwide</span>
      </h2>
      <p className="font-[Manrope] font-400 text-neutral-400 text-center text-lg mb-16">
        Powering clinic and SaaS websites across 4 continents
      </p>
      <div className="max-w-5xl mx-auto">
        <WorldMap dots={connections} lineColor="#ff642a" />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `lineColor` to `#ff642a` for brand-consistent connection lines
- Map dot/node points can be colored with the gradient end color `#ff0301`
- Use Manrope 800 for section title, 400 for subtitle on #0a0a0a background
- Map renders as SVG so it scales cleanly to any container width
- Zero dependencies makes this fully GHL-compatible with no JS framework requirements

## Performance Notes
- SVG-based rendering is lightweight and resolution-independent
- Connection line animations use CSS `stroke-dashoffset`, GPU-friendly
- Dot pulsing animations are CSS-only keyframes
- Map viewBox is fixed aspect ratio; container should maintain proportions
- No canvas or WebGL overhead; safe for mobile and low-power devices
