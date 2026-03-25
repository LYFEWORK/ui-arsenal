---
name: scroll-velocity
source: ReactBits
source_url: https://reactbits.dev/text-animations/scroll-velocity
category: text-animations
tags: text, scroll, velocity, speed, marquee, kinetic, dynamic
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ScrollVelocity

> Text that scrolls horizontally at a speed proportional to the user's scroll velocity. Scroll fast and the text races by. Stop scrolling and it decelerates. Creates a kinetic, dynamic connection between content and interaction.

## When to Use

- Section dividers with branding text or taglines
- Portfolio sites where scroll interaction should feel alive
- Between-section text strips that add energy to the page
- Brand name or slogan repetition strips
- Any kinetic typography moment tied to scroll behavior

## When NOT to Use

- Content that needs to be read carefully
- Pages with minimal scroll depth
- More than 2 velocity text strips per page
- Accessibility-focused builds (motion-sensitive users)

## Pairs Well With

- `smooth-scroll` - Smooth scrolling makes velocity text feel even better
- `noise` - Noise overlay on the velocity text section
- `marquee` - Use Marquee for constant speed, ScrollVelocity for dynamic speed
- `split-text` - Standard headline above, velocity strip below

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to scroll (repeats infinitely) |
| baseVelocity | number | 5 | Base scroll speed |
| scrollMultiplier | number | 0.5 | How much scroll speed affects text speed |
| direction | "left" \| "right" | "left" | Scroll direction |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ScrollVelocity-TS-TW
```

## Usage Example

```jsx
import ScrollVelocity from '@/components/ui/ScrollVelocity';

function BrandStrip() {
  return (
    <div className="py-8 border-y border-white/5 overflow-hidden">
      <ScrollVelocity
        text="INFRASTRUCTURE • EXCELLENCE • LYFEWORK • "
        baseVelocity={3}
        scrollMultiplier={0.3}
        className="text-6xl font-extrabold text-white/10 uppercase whitespace-nowrap"
      />
    </div>
  );
}
```

## Lyfework Customization Notes

- Text at very low opacity (10-20%) for watermark/branding effect
- `baseVelocity` of 2-5 for ambient. Higher for energetic sections.
- Text should end with a separator (" • ") for seamless looping
- Manrope 800, uppercase, wide tracking for the kinetic typography look
- Use as section dividers, not primary content
- Works in GHL with framer-motion loaded

## Performance Notes

- framer-motion useScroll + useTransform hooks
- Text is duplicated for seamless looping
- GPU accelerated translateX
- Lightweight, scroll listener is debounced
