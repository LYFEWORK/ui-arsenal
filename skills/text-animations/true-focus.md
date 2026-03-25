---
name: true-focus
source: ReactBits
source_url: https://reactbits.dev/text-animations/true-focus
category: text-animations
tags: text, focus, highlight, border, attention, word-by-word
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# TrueFocus

> A text component where a focus border moves from word to word, highlighting each one in sequence. Creates a "reading along" effect where a border box travels between words.

## When to Use

- Taglines or slogans where each word deserves individual attention
- Feature headlines where words are the features themselves
- Mission statements or value propositions
- Hover-triggered word highlighting in interactive sections
- Builds where you want a unique text effect not commonly seen

## When NOT to Use

- Long sentences (border jumping becomes tedious)
- Body text or paragraphs
- Headlines where all words should read together as one phrase
- Multiple instances per page

## Pairs Well With

- `animated-content` - Reveal the section, then TrueFocus starts
- `spotlight-card` - TrueFocus headline inside a spotlight card
- `fade-content` - Supporting text fades in after TrueFocus completes

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display |
| borderColor | string | "#ff642a" | Focus border color |
| blurAmount | number | 5 | Blur on unfocused words (px) |
| animationDuration | number | 0.5 | Transition duration in seconds |
| pauseBetween | number | 1 | Pause on each word in seconds |
| hoverMode | boolean | false | Activate on hover instead of auto |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TrueFocus-TS-TW
```

## Usage Example

```jsx
import TrueFocus from '@/components/ui/TrueFocus';

function ValueProp() {
  return (
    <section className="py-24 text-center">
      <TrueFocus
        text="Infrastructure Excellence Delivered"
        borderColor="#ff642a"
        blurAmount={4}
        pauseBetween={1.2}
        className="text-5xl font-extrabold text-white"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Border color: `#ff642a` for Lyfework
- `blurAmount` of 3-5px. Unfocused words should be readable but de-emphasized.
- `pauseBetween` of 0.8-1.5s per word. Shorter for 2-3 word phrases, longer for 4+ words.
- Great for 3-4 word value propositions
- Works in GHL with framer-motion

## Performance Notes

- framer-motion layout animation for border movement
- CSS blur filter on unfocused words
- Lightweight, only a few elements animating
- GPU accelerated blur and transforms
