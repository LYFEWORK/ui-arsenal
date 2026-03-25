---
name: text-pressure
source: ReactBits
source_url: https://reactbits.dev/text-animations/text-pressure
category: text-animations
tags: text, pressure, distort, squeeze, interactive, cursor, creative
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# TextPressure

> Text that deforms and squeezes under cursor pressure. Characters compress, stretch, or warp based on how close the cursor is, simulating physical pressure on the type.

## When to Use

- Interactive typography experiments on creative sites
- Portfolio or agency hero sections
- Art or design brand pages where type is expressive
- Interactive "about" page headlines
- Showcase builds that demonstrate range

## When NOT to Use

- Any text that needs to be easily readable
- Business or professional contexts
- Mobile (no cursor interaction)
- More than one instance per page

## Pairs Well With

- `variable-proximity` - Choose one: VariableProximity for weight change, TextPressure for spatial distortion
- `blob-cursor` - Organic cursor + type pressure
- `aurora` - Atmospheric background for pressure type
- `noise` - Textured backdrop for experimental typography

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display |
| pressureStrength | number | 0.5 | Deformation intensity (0-1) |
| pressureRadius | number | 100 | Cursor effect radius in px |
| recoverSpeed | number | 0.3 | Speed text returns to normal |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TextPressure-TS-TW
```

## Lyfework Customization Notes

- Tier 3. Showcase and creative builds only.
- `pressureStrength` of 0.3-0.6 for controlled effect. Above 0.8 gets wild.
- Use Manrope 800 at large sizes for maximum impact
- Desktop only. Static text fallback on mobile.
- Not for GHL

## Performance Notes

- SVG or Canvas-based text deformation
- Per-character position calculations on mousemove
- Keep to short text (under 20 chars)
- requestAnimationFrame throttled
