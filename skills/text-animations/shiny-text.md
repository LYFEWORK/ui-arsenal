---
name: shiny-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/shiny-text
category: text-animations
tags: text, shiny, shimmer, gloss, sweep, premium, badge
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ShinyText

> A glossy shimmer sweep that passes across text on a loop. Like a light reflection moving across a metal surface. Pure CSS, zero dependencies.

## When to Use

- "New" or "Featured" badges and labels
- Brand taglines or slogans that need subtle premium movement
- CTA button text for extra attention
- Pricing plan names or feature highlights
- Any short text that should shimmer with quality

## When NOT to Use

- Body text or paragraphs (too distracting for reading)
- More than 2-3 shiny text instances per page
- Long sentences (shimmer takes too long to traverse)
- Headings that already use BlurText or SplitText (double animation)

## Pairs Well With

- `glow-card` - Shiny text title inside a glow-bordered card
- `star-border` - Star border on a button with shiny text label
- `spotlight-card` - Shiny "Featured" badge on a spotlight card
- `gradient-text` - Choose one or the other for accent text, not both

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display |
| speed | number | 3 | Shimmer cycle duration in seconds |
| color | string | "#ffffff" | Base text color |
| shimmerColor | string | "rgba(255,255,255,0.8)" | Shimmer highlight color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ShinyText-TS-TW
```

## Usage Example

```jsx
import ShinyText from '@/components/ui/ShinyText';

function PricingBadge() {
  return (
    <div className="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-white/5 border border-white/10">
      <ShinyText text="Most Popular" speed={2.5} className="text-sm font-bold uppercase tracking-wide" />
    </div>
  );
}
```

## Lyfework Customization Notes

- Shimmer color: `rgba(255,255,255,0.8)` on dark backgrounds. `rgba(255,100,42,0.6)` for orange shimmer.
- `speed` of 2-4 seconds. Faster for badges (2s). Slower for headlines (4s).
- Great for "New", "Popular", "Featured", "Limited" labels
- Works perfectly in GHL (pure CSS animation with `background-size` and `background-position`)

## Performance Notes

- Zero JavaScript, pure CSS with animated `background-position`
- Negligible performance cost
- Works on all browsers
