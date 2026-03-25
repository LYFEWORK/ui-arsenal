---
name: falling-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/falling-text
category: text-animations
tags: text, falling, gravity, physics, playful, dramatic
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FallingText

> Text characters that fall from their positions with gravity physics, then reassemble. Can trigger on load, scroll, or hover. Creates a dramatic collapse/rebuild effect.

## When to Use

- 404 pages where text "falls apart" to signal something's broken
- Dramatic section reveals where text assembles from chaos
- Interactive headings that collapse on hover and rebuild
- Storytelling moments (text falls, then a new message assembles)
- Creative builds that need a memorable text interaction

## When NOT to Use

- Primary headlines that need to be read immediately
- Professional/corporate contexts (too playful)
- Multiple instances per page
- Long text blocks (physics simulation gets heavy)

## Pairs Well With

- `pixel-transition` - Text falls, then pixel-transitions to new content
- `click-spark` - Click to make text fall, sparks fly
- `letter-glitch` - Glitch background with falling text overlay

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to animate |
| trigger | "load" \| "scroll" \| "hover" | "load" | When text falls/assembles |
| gravity | number | 1 | Gravity strength |
| bounce | number | 0.3 | Bounce factor on landing |
| stagger | number | 0.05 | Stagger between characters |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FallingText-TS-TW
```

## Lyfework Customization Notes

- `gravity` of 0.8-1.2. Higher = faster fall. Lower = floaty.
- `bounce` of 0.2-0.4 for subtle. Above 0.6 is very bouncy.
- `trigger="scroll"` for section reveals. `"hover"` for interactive headings.
- Great for 404 pages or creative transitions
- Keep to under 20 characters for performance
- Works in GHL for simple CSS animation implementations

## Performance Notes

- Physics simulation per character
- Each character is an absolutely positioned element
- Keep character count under 30 for smooth animation
- Can use CSS-only approximation or full JS physics
