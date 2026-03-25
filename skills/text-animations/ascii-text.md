---
name: ascii-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/ascii-text
category: text-animations
tags: text, ascii, art, retro, terminal, code, canvas
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# ASCIIText

> Renders text as ASCII art characters. Large block-letter text built from smaller characters. Retro terminal aesthetic with optional animation.

## When to Use

- Developer tool or API product hero sections
- Retro-themed or terminal-aesthetic builds
- 404 or error pages with personality
- Gaming or hacker brand aesthetics
- Easter egg sections or hidden interactive elements

## When NOT to Use

- Professional business landing pages
- Any brand that isn't explicitly tech/retro
- Mobile (ASCII art needs wide viewport to render properly)
- Long text (ASCII art is wide, even short words fill the screen)

## Pairs Well With

- `letter-glitch` - Glitch background behind ASCII text
- `typing-animation` - ASCII text types out character by character
- `particles` - Particle background behind terminal-style ASCII
- `noise` - Film grain over ASCII for full retro vibe

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to render as ASCII art |
| font | string | "standard" | ASCII art font style |
| color | string | "#ffffff" | Text color |
| animated | boolean | false | Animate the ASCII rendering |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ASCIIText-TS-TW
```

## Lyfework Customization Notes

- Tier 3 showcase only. For Guildeon brand or developer-focused builds.
- Color: `#ff642a` for Lyfework orange terminal text
- Use monospace font for proper character alignment
- Keep text to 1-2 short words max
- Not for standard Lyfework client builds

## Performance Notes

- Canvas or pre-computed text rendering
- Static once rendered (no ongoing animation cost unless animated=true)
- Large DOM footprint for complex ASCII art
