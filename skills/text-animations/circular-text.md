---
name: circular-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/circular-text
category: text-animations
tags: text, circular, rotating, badge, orbit, decorative
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# CircularText

> Text arranged in a circle that rotates continuously. Characters are placed along a circular path, spinning like a badge or seal. Often used as a decorative element.

## When to Use

- Decorative badges or seals ("Award Winning" rotating around a logo)
- Scroll-to-explore indicators at the bottom of hero sections
- Branding elements on creative/portfolio sites
- Hover effect on circular buttons or icons
- Any decorative text that doesn't need to be read instantly

## When NOT to Use

- Primary content or headlines (hard to read while spinning)
- Information that needs to be scanned quickly
- More than 1-2 instances per page
- Dense layouts where it adds clutter

## Pairs Well With

- `aurora` - Circular text badge floating over aurora hero
- `tilted-card` - Circular text element in the corner of a card
- `splash-cursor` - Decorative circular text on a creative page
- `dock` - Circular text orbiting a central logo above a dock nav

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display in circle |
| radius | number | 80 | Circle radius in px |
| speed | number | 10 | Rotation speed in seconds per revolution |
| fontSize | number | 14 | Font size in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CircularText-TS-TW
```

## Usage Example

```jsx
import CircularText from '@/components/ui/CircularText';

function ScrollIndicator() {
  return (
    <div className="absolute bottom-12 left-1/2 -translate-x-1/2">
      <CircularText
        text="SCROLL DOWN • EXPLORE MORE • "
        radius={60}
        speed={12}
        fontSize={11}
        className="text-gray-400 uppercase tracking-[0.3em]"
      />
      <div className="absolute inset-0 flex items-center justify-center">
        <span className="text-white text-xl">↓</span>
      </div>
    </div>
  );
}
```

## Lyfework Customization Notes

- Text should end with a separator (" • ") for seamless circular flow
- `speed` of 10-15s for gentle rotation. Below 8s feels frantic.
- Use `uppercase tracking-[0.3em]` for the classic rotating badge look
- Pair with a centered icon or logo inside the circle
- Works in GHL (CSS transform + SVG text path)

## Performance Notes

- Pure CSS rotation on a positioned SVG or div container
- Each character is absolutely positioned along the arc
- Zero JavaScript animation needed (CSS `@keyframes rotate`)
- Negligible performance cost
