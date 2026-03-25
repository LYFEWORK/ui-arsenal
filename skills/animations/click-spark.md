---
name: click-spark
source: ReactBits
source_url: https://reactbits.dev/animations/click-spark
category: animations
tags: click, spark, micro-interaction, delight, cursor, effect
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ClickSpark

> Emits a burst of sparks from the click point on any element. A subtle micro-interaction that adds delight to button clicks, card interactions, or any clickable element.

## When to Use

- CTA buttons on landing pages (adds satisfying click feedback)
- Card clicks that navigate to detail pages
- Interactive elements that benefit from tactile feedback
- Portfolio pieces or gallery items on click
- Anywhere you want to reward the user's click with visual delight

## When NOT to Use

- Form submissions (the spark might imply something happened before it did)
- Navigation links that fire instantly (spark competes with page transition)
- High-frequency click targets (rapid clicks produce too many sparks)
- Enterprise or conservative brand contexts (may feel too playful)

## Pairs Well With

- `tilted-card` - Click a tilted card and sparks fly
- `spotlight-card` - Spotlight hover + spark on click
- `magnet` - Magnetic pull toward button + spark on click

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Clickable element to wrap |
| sparkColor | string | "#ff642a" | Color of the spark particles |
| sparkCount | number | 8 | Number of spark particles |
| sparkSize | number | 10 | Size of each spark |
| duration | number | 400 | Spark animation duration in ms |

## Installation

```bash
npx shadcn@latest add @react-bits/ClickSpark-TS-TW
```

## Usage Example

```jsx
import ClickSpark from '@/components/ui/ClickSpark';

function CTAButton() {
  return (
    <ClickSpark sparkColor="#ff642a" sparkCount={10} duration={500}>
      <button className="px-8 py-4 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg hover:scale-105 transition-transform">
        Book Your Install
      </button>
    </ClickSpark>
  );
}
```

## Lyfework Customization Notes

- Default spark color: `#ff642a` (Lyfework brand orange)
- For client builds, match their CTA accent color
- `sparkCount` of 8-12 is ideal. Above 15 gets messy.
- Keep `duration` at 300-500ms so sparks feel snappy
- Works perfectly in GHL since it's pure DOM manipulation
- Add to primary CTAs only, not every clickable element on the page

## Performance Notes

- Zero dependencies, pure DOM element creation and CSS animation
- Sparks are created on click and removed after animation completes
- No memory leaks, no persistent listeners beyond the click handler
- Negligible performance impact
