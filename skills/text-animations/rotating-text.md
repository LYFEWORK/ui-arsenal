---
name: rotating-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/rotating-text
category: text-animations
tags: text, rotating, cycling, typewriter, swap, headline
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# RotatingText

> A text element that cycles through multiple strings with animated transitions. Words rotate in and out with slide, fade, or flip animations. The classic "We build [websites / systems / futures]" pattern.

## When to Use

- Hero headlines with rotating value propositions
- "We help [dentists / chiropractors / med spas]" ICP targeting
- Feature highlights that cycle through benefits
- Any headline where one word changes to show range or versatility

## When NOT to Use

- Headlines where the rotating word isn't meaningfully different each time
- More than one rotating text per viewport (visual chaos)
- Body text or secondary content
- Headlines where the full message matters for SEO (search engines may only index one variant)

## Pairs Well With

- `aurora` - Aurora background + rotating headline in the hero
- `animated-content` - Reveal supporting content after rotating text settles
- `gradient-text` - The rotating word rendered in gradient
- `magnet` - Magnetic CTA below the rotating headline

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| words | string[] | [] | Array of words to cycle through |
| interval | number | 3000 | Time between rotations in ms |
| transition | "slide" \| "fade" \| "flip" | "slide" | Animation style |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/RotatingText-TS-TW
```

## Usage Example

```jsx
import RotatingText from '@/components/ui/RotatingText';

function Hero() {
  return (
    <h1 className="text-5xl md:text-7xl font-extrabold text-white text-center">
      We Build Systems for{' '}
      <RotatingText
        words={['Clinics', 'Med Spas', 'Dental Offices', 'Chiropractors']}
        interval={2500}
        transition="slide"
        className="text-transparent bg-clip-text bg-gradient-to-r from-[#ff642a] to-[#ff0301]"
      />
    </h1>
  );
}
```

## Lyfework Customization Notes

- Interval of 2000-3000ms gives readers time to absorb each word
- `transition="slide"` for most builds. `"flip"` for more energetic brands.
- Apply the Lyfework gradient to the rotating word for emphasis
- Keep to 3-5 rotating words. More than 6 means the cycle takes too long.
- For ClinicOS pages: rotate through ICP verticals (Clinics, Med Spas, Dental, Chiro)
- Works in GHL with framer-motion loaded

## Performance Notes

- framer-motion AnimatePresence for transitions
- Only two DOM elements active at once (entering and exiting)
- Lightweight, no performance concerns
- SSR: renders first word statically, rotates on client
