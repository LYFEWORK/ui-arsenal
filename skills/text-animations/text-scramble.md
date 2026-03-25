---
name: text-scramble
source: ReactBits
source_url: https://reactbits.dev/text-animations/text-scramble
category: text-animations
tags: text, scramble, decode, cipher, reveal, matrix, hacker
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# TextScramble

> Text that decodes from random characters into the final message. Characters shuffle rapidly before settling into the correct letters. Matrix/cipher aesthetic.

## When to Use

- Tech/AI product hero headlines for a "decoding" feel
- Loading states where text resolves as content loads
- Hover effects on navigation items or CTAs
- Section transitions where new text "decodes" into view
- Taglines or slogans that benefit from a dramatic reveal

## When NOT to Use

- Body text or paragraphs (unreadable during scramble)
- Accessibility-critical content (screen readers can't follow the scramble)
- Soft/organic brand aesthetics (feels too techy)
- More than 2 scramble instances per viewport

## Pairs Well With

- `particles` - Particle background + scrambling text = full hacker aesthetic
- `pixel-card` - Pixel dissolve cards with scramble text titles
- `beams` - Light beams behind decoding text
- `splash-cursor` - Full immersive tech experience

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Final resolved text |
| characters | string | "!@#$%^&*" | Characters used during scramble |
| speed | number | 50 | Scramble speed in ms per tick |
| trigger | "load" \| "scroll" \| "hover" | "load" | When to start scramble |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TextScramble-TS-TW
```

## Usage Example

```jsx
import TextScramble from '@/components/ui/TextScramble';

function TechHero() {
  return (
    <h1>
      <TextScramble
        text="Intelligence. Automated."
        characters="01"
        speed={40}
        trigger="load"
        className="text-5xl font-extrabold text-white font-mono"
      />
    </h1>
  );
}
```

## Lyfework Customization Notes

- `characters="01"` for binary/AI aesthetic. Default symbols for a cipher look.
- `speed` of 30-60ms per tick. Below 20ms is too fast to read. Above 80ms is sluggish.
- Pair with a monospace or code font for the scramble phase, then Manrope for resolved text
- Best on dark backgrounds where the text contrast is sharp
- Works in GHL (pure DOM text manipulation)

## Performance Notes

- Zero dependencies, vanilla JS text manipulation
- Lightweight requestAnimationFrame loop
- No layout shifts (text container sized to final text)
