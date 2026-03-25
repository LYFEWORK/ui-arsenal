---
name: counter
source: ReactBits
source_url: https://reactbits.dev/components/counter
category: components
tags: counter, increment, decrement, input, number, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Counter

> An animated increment/decrement counter with spring physics. Number changes animate with rolling or sliding transitions. More visual than a standard number input.

## When to Use

- Quantity selectors on pricing or order pages
- Interactive demos where users adjust a count
- Dashboard metrics that update in real-time
- Any numeric input that benefits from visual feedback on change

## When NOT to Use

- Standard form number fields (over-engineered for basic forms)
- Large number ranges (use ElasticSlider instead)
- Values that change too frequently (animation can't keep up)

## Pairs Well With

- `spotlight-card` - Counter inside a spotlight metrics card
- `glow-card` - Highlighted counter in a pricing section
- `elastic-slider` - Slider for range, counter for precise adjustments

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| value | number | 0 | Current value |
| min | number | 0 | Minimum value |
| max | number | 99 | Maximum value |
| onChange | function | required | Value change handler |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Counter-TS-TW
```

## Lyfework Customization Notes

- Button styling: glass background with Lyfework gradient on hover
- Number display: Manrope 800, large size
- Spring animation on number change for premium feel
- Works in GHL with React embeds

## Performance Notes

- framer-motion AnimatePresence for number transitions
- Lightweight, single number element animating
- No performance concerns
