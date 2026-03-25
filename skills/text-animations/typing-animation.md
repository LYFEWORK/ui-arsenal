---
name: typing-animation
source: ReactBits
source_url: https://reactbits.dev/text-animations/typing-animation
category: text-animations
tags: text, typing, typewriter, cursor, terminal, code
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# TypingAnimation

> Classic typewriter effect. Text appears character by character with a blinking cursor. Can type, pause, delete, and type new text in sequence.

## When to Use

- Terminal or code-themed hero sections
- Rotating messages that type out and delete (chat simulation)
- Developer or tech product landing pages
- "We build..." sequences that type different completions
- Anywhere the typewriter aesthetic fits the brand

## When NOT to Use

- Elegant or luxury brands (typewriter feels too techy)
- Long paragraphs (animation takes forever)
- More than one typing instance per viewport
- Content that needs to be read instantly

## Pairs Well With

- `particles` - Particle background + typing text for tech heroes
- `letter-glitch` - Glitch background with typewriter foreground
- `noise` - Noise overlay for full terminal aesthetic
- `rotating-text` - Choose one: RotatingText for word swap, TypingAnimation for character-by-character

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| sequences | string[] | [] | Array of strings to type in order |
| typeSpeed | number | 50 | Typing speed in ms per character |
| deleteSpeed | number | 30 | Delete speed in ms per character |
| pauseTime | number | 2000 | Pause between sequences in ms |
| loop | boolean | true | Loop through sequences |
| showCursor | boolean | true | Show blinking cursor |
| cursorChar | string | "|" | Cursor character |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TypingAnimation-TS-TW
```

## Usage Example

```jsx
import TypingAnimation from '@/components/ui/TypingAnimation';

function DevHero() {
  return (
    <h1 className="text-4xl font-mono text-white">
      <span className="text-gray-500">$ </span>
      <TypingAnimation
        sequences={['lyfework install --clinic', 'lyfework deploy --all', 'lyfework status --live']}
        typeSpeed={60}
        deleteSpeed={30}
        pauseTime={2500}
        cursorChar="_"
        className="text-green-400"
      />
    </h1>
  );
}
```

## Lyfework Customization Notes

- Use monospace font for terminal aesthetic, Manrope for brand-consistent typing
- `typeSpeed` of 40-70ms feels natural. Below 30 is too fast to read. Above 100 tests patience.
- Cursor: `"|"` for modern, `"_"` for terminal, `"█"` for retro
- Cursor blink rate: standard 530ms CSS animation
- Works in GHL (pure DOM text manipulation)
- Great for Guildeon builds (developer brand)

## Performance Notes

- Zero dependencies, vanilla JS setTimeout chain
- Single DOM element text update per tick
- No layout shifts (container pre-sized to longest sequence)
- Works on all devices
