---
name: follow-cursor
source: ReactBits
source_url: https://reactbits.dev/animations/follow-cursor
category: animations
tags: cursor, follow, eyes, tracking, interactive, playful
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FollowCursor

> An element (typically eyes, an icon, or a pointer) that tracks and follows the cursor position. The classic "eyes follow your mouse" pattern, but configurable for any element.

## When to Use

- Mascot or character elements that watch the user
- Interactive illustrations or infographics
- Playful brand pages (pets, characters, avatars)
- 404 error pages that need personality
- Fun micro-interactions on about pages

## When NOT to Use

- Professional B2B landing pages (too playful)
- Pages with many interactive elements already
- Mobile (no cursor to follow)
- Any context where the tracking feels creepy rather than fun

## Pairs Well With

- `animated-content` - Reveal the follow element on scroll
- `blob-cursor` - Blob cursor + following eyes = full character page
- `aurora` - Soft background behind a playful following element

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element that follows cursor |
| offset | {x: number, y: number} | {x:0, y:0} | Position offset |
| speed | number | 0.1 | Follow speed (0-1, lower = laggier) |
| range | number | 30 | Max movement range in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FollowCursor-TS-TW
```

## Lyfework Customization Notes

- `speed` of 0.08-0.15 for a natural lag. 1.0 = instant (no lag, feels robotic).
- `range` of 20-40px for subtle. Above 60 looks exaggerated.
- Great for 404 pages, mascot interactions, or playful client brands
- Not a standard component for most Lyfework client builds
- Works in GHL for simple CSS transform implementations

## Performance Notes

- CSS transform on mousemove event
- requestAnimationFrame throttled
- Zero dependencies possible (vanilla JS + CSS)
- Negligible cost
