---
name: 3d-animated-pin
source: Aceternity UI
source_url: https://ui.aceternity.com/components/3d-animated-pin
category: components
tags: 3d, pin, map, hover, popup, location, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# 3dAnimatedPin

> 3D elevated pin popup that rises on hover, ideal for maps, location markers, and spatial UI elements.

## When to Use
- Displaying clinic or office locations on a custom map layout
- Showing location-based service areas with interactive detail popups
- Creating spatial product showcases where items rise to reveal details
- Building interactive city or region selectors for multi-location businesses
- Adding depth to contact pages with office location highlights

## When NOT to Use
- On mobile-heavy layouts where hover is unavailable
- When you need standard Google Maps integration instead
- For simple tooltip displays without spatial context

## Pairs Well With
- `world-map` - Combine pins with the animated world map for global presence
- `spotlight-card` - Use spotlight cards as pin popup content
- `blur-text` - Animate location names as they appear in the popup
- `particles` - Add particle effects around active pin locations

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | - | Title displayed in the pin popup |
| href | string | - | Link URL when pin is clicked |
| children | ReactNode | - | Content rendered inside the elevated popup |
| containerClassName | string | - | Additional classes for the outer container |
| className | string | - | Additional classes for the pin element |

## Installation
```bash
npx aceternity-ui@latest add 3d-animated-pin
```

## Usage Example
```jsx
import { PinContainer } from "@/components/ui/3d-animated-pin";

export function ClinicLocations() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-[Manrope] font-800 text-4xl text-white mb-16">
        Our <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Locations</span>
      </h2>
      <div className="flex flex-wrap justify-center gap-16">
        <PinContainer title="Visit Downtown Clinic" href="/locations/downtown">
          <div className="lyf-glass rounded-[12px] p-6 w-[280px]">
            <h3 className="font-[Manrope] font-700 text-white text-lg">Downtown Clinic</h3>
            <p className="text-neutral-400 font-[Manrope] font-400 text-sm mt-2">
              Full-service wellness center with AI-powered diagnostics
            </p>
            <span className="mt-4 inline-block text-sm bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent font-700">
              Book Appointment →
            </span>
          </div>
        </PinContainer>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `lyf-glass` class to pin popup content for frosted glass aesthetic on #0a0a0a backgrounds
- Use Manrope 700/800 for pin titles, 400 for descriptions
- Apply gradient `from-[#ff642a] to-[#ff0301]` to CTA text inside popup
- Set popup card border-radius to 12px per Lyfework design system
- Ensure GHL embed compatibility by wrapping in a relative-positioned container with defined height

## Performance Notes
- Hover-only interaction means zero cost on mobile (renders as static)
- Uses CSS transforms for 3D effect, GPU-accelerated
- Limit to 6-8 pins per viewport to avoid layout thrashing
- Framer Motion animations are hardware-accelerated via `will-change: transform`
- Lazy load pin content if popups contain images
