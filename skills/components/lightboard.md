---
name: lightboard
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/lightboard
category: components
tags: lightboard, led, text, display, interactive, retro
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# Lightboard

> Interactive LED lightboard text display with clickable pixels and scrolling text support.

## When to Use
- Retro-themed hero sections with LED text display
- Interactive brand name display on creative portfolio sites
- Event countdown or status boards with LED aesthetic
- Loading or processing states with scrolling LED messages
- Creative about/contact pages with distinctive typography

## When NOT to Use
- Standard text display where readability is paramount
- Professional/corporate pages where LED style feels too playful
- Content-heavy sections where pixel text is hard to read
- Mobile screens where LED pixels become too small

## Pairs Well With
- `particles` - Particles floating around LED lightboard display
- `background-texture` - Noise texture behind lightboard for depth
- `aurora` - Aurora glow behind LED display
- `number-ticker` - LED-style number counter displays

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | '' | Display text |
| rows | number | 8 | Grid row count |
| columns | number | 64 | Grid column count |
| color | string | '#ff642a' | Active LED color |
| offColor | string | '#1a1a1a' | Inactive LED color |
| pixelSize | number | 4 | LED pixel size in px |
| gap | number | 1 | Gap between pixels |
| scrolling | boolean | false | Enable text scrolling |
| scrollSpeed | number | 50 | Scroll speed in ms per step |
| interactive | boolean | false | Enable click-to-toggle pixels |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/lightboard"
```

## Usage Example
```jsx
import { Lightboard } from "@/components/ui/lightboard";

export function RetroHero() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6 flex flex-col items-center">
      <Lightboard
        text="LYFEWORK"
        rows={8}
        columns={80}
        color="#ff642a"
        offColor="#151515"
        pixelSize={5}
        gap={1}
        scrolling={false}
        className="mx-auto"
      />
      <p className="font-manrope font-400 text-white/60 mt-8 text-center max-w-md">
        Building the future of digital experiences, one pixel at a time.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- LED color: brand orange #ff642a, off pixels: #151515 on #0a0a0a
- Use "LYFEWORK" or brand messaging as LED display text
- Pair with Manrope 400 supporting text below lightboard
- Interactive mode allows users to draw on the lightboard
- Not recommended for GHL -- high DOM count from pixel grid

## Performance Notes
- DOM node count = rows x columns; keep total under 1000 pixels
- Use CSS grid for pixel layout -- efficient browser rendering
- Scrolling uses requestAnimationFrame with visibility check
- Interactive mode adds single delegated click handler (not per-pixel)
- Consider canvas-based alternative for grids larger than 80x12
