---
name: magnet
source: ReactBits
source_url: https://reactbits.dev/animations/magnet
category: animations
tags: magnet, hover, cursor, pull, attraction, button, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Magnet

> Makes an element magnetically attracted to the cursor on hover. The element subtly shifts toward the mouse position, creating a "pull" effect. Most commonly used on buttons and interactive elements.

## When to Use

- Primary CTA buttons to increase their visual pull and interactivity
- Navigation items or icon buttons
- Floating action buttons or dock items
- Any isolated interactive element that benefits from cursor awareness
- "Book a call" or "Get started" buttons on hero sections

## When NOT to Use

- Dense layouts with many elements close together (elements would fight for attention)
- Form inputs or select dropdowns (interferes with interaction)
- Text links inline with content
- Elements that are part of a scrollable list

## Pairs Well With

- `click-spark` - Magnetic pull toward button, then spark on click
- `dock` - Dock items already have magnification, but standalone buttons benefit from Magnet
- `gradient-text` - Magnetic button with gradient text label

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element to make magnetic |
| strength | number | 0.5 | Pull strength (0-1) |
| range | number | 200 | Distance in px where magnet activates |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Magnet-TS-TW
```

## Usage Example

```jsx
import Magnet from '@/components/ui/Magnet';
import ClickSpark from '@/components/ui/ClickSpark';

function HeroCTA() {
  return (
    <Magnet strength={0.4} range={180}>
      <ClickSpark sparkColor="#ff642a">
        <button className="px-10 py-5 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg shadow-lg shadow-orange-500/20 hover:shadow-orange-500/40 transition-shadow">
          Book Your Install
        </button>
      </ClickSpark>
    </Magnet>
  );
}
```

## Lyfework Customization Notes

- `strength` of 0.3-0.5 for buttons. Above 0.6 feels glitchy.
- `range` of 150-200px for hero CTAs. Smaller range for nav items.
- Only apply to 1-2 elements per viewport. Multiple magnets competing looks broken.
- For GHL: test that the transform doesn't push the element outside its container bounds
- On mobile, Magnet has no effect (no cursor). No fallback needed, it just renders normally.

## Performance Notes

- framer-motion spring animation on mouse position
- Only active when cursor is within range (no idle computation)
- Single transform per frame, GPU accelerated
- Negligible performance impact
