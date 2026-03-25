---
name: variable-proximity
source: ReactBits
source_url: https://reactbits.dev/text-animations/variable-proximity
category: text-animations
tags: text, proximity, cursor, variable-font, interactive, hover, weight
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# VariableProximity

> Text that changes font weight, size, or style based on cursor proximity. Characters near the mouse become bolder/larger while distant ones stay thin/small. Uses variable font technology.

## When to Use

- Interactive headings on creative/portfolio sites
- Hero text that responds to mouse exploration
- Typography-focused brand pages
- Design agency showcases where type IS the design
- Any headline where cursor interaction adds discovery

## When NOT to Use

- Body text or readable content (weight changes disrupt reading)
- Mobile (no cursor proximity)
- Fonts that aren't variable weight (requires variable font file)
- Standard business sites

## Pairs Well With

- `splash-cursor` - Cursor effects + proximity text for full interactive type experience
- `blob-cursor` - Organic cursor + responsive type
- `aurora` - Soft background behind interactive typography
- `noise` - Texture overlay on interactive type section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display |
| fontFamily | string | "Manrope" | Variable font family |
| minWeight | number | 100 | Min font weight (far from cursor) |
| maxWeight | number | 900 | Max font weight (near cursor) |
| radius | number | 150 | Effect radius in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/VariableProximity-TS-TW
```

## Lyfework Customization Notes

- Manrope supports weights 200-800, perfect for this effect
- `minWeight` of 200, `maxWeight` of 800 for dramatic range
- `radius` of 100-200px for controlled effect
- Tier 2 situational. Use for creative builds, not standard client sites.
- Works in GHL with vanilla JS mouse tracking + CSS font-variation-settings

## Performance Notes

- CSS font-variation-settings updates on mousemove
- Each character needs individual weight calculation
- Keep to short text (under 30 characters) for performance
- requestAnimationFrame throttled mouse tracking
