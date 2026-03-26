---
name: text-reveal-card
source: Aceternity UI
source_url: https://ui.aceternity.com/components/text-reveal-card
category: components
tags: card, text, reveal, cursor, mask, hover, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# TextRevealCard

> Card where cursor movement reveals hidden text underneath, like wiping away a surface layer to expose content.

## When to Use
- Before/after reveals for design transformations or results
- Interactive hero elements with hidden messaging
- Playful CTA sections where curiosity drives engagement
- Brand storytelling with reveal-based narrative
- Secret message or Easter egg interactions

## When NOT to Use
- When the hidden text contains critical information users must see
- On mobile without a hover/swipe fallback mechanism
- For accessibility-critical content that must be screen-reader visible

## Pairs Well With
- `gradient-text` - Gradient styling on the revealed text
- `spotlight-card` - Spotlight glow combined with text reveal
- `particles` - Particle effects around the reveal area
- `blur-text` - Blur entrance for surrounding card elements

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | - | Top layer visible text |
| revealText | string | - | Hidden text revealed on hover |
| className | string | - | Classes for the card container |
| children | ReactNode | - | Additional card content |

## Installation
```bash
npx aceternity-ui@latest add text-reveal-card
```

## Usage Example
```jsx
import { TextRevealCard, TextRevealCardTitle, TextRevealCardDescription } from "@/components/ui/text-reveal-card";

export function RevealSection() {
  return (
    <section className="bg-[#0a0a0a] py-24 flex justify-center px-6">
      <TextRevealCard text="We build websites" revealText="We build experiences" className="lyf-glass rounded-[12px]">
        <TextRevealCardTitle className="font-[Manrope] font-800">
          Hover to discover the{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            difference
          </span>
        </TextRevealCardTitle>
        <TextRevealCardDescription className="font-[Manrope] font-400 text-neutral-400">
          At Lyfework, we go beyond templates. Every pixel serves a purpose.
        </TextRevealCardDescription>
      </TextRevealCard>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `lyf-glass` with `rounded-[12px]` for the card background
- Revealed text can use the `from-[#ff642a] to-[#ff0301]` gradient for emphasis
- Manrope 800 for card titles, 400 for descriptions on #0a0a0a backgrounds
- Text mask color should contrast enough against both surface and revealed layers
- Provide a touch swipe fallback for mobile users visiting outside GHL desktop views

## Performance Notes
- Cursor masking uses CSS `clip-path` or `mask-image`, GPU-accelerated
- Mouse move tracking is throttled to 60fps for smooth reveal
- Text layers are simple DOM elements, minimal memory overhead
- Single card instance is recommended per viewport section
- Fallback for mobile should auto-reveal the text without interaction
