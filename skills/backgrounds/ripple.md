---
name: ripple
source: ReactBits
source_url: https://reactbits.dev/backgrounds/ripple
category: backgrounds
tags: background, ripple, water, click, interactive, rings
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Ripple

> Concentric ripple rings that emanate from click or cursor position. Creates a water-drop effect on a dark surface. Can be ambient (auto-spawning) or interactive (click-triggered).

## When to Use

- Interactive hero backgrounds that respond to clicks
- Zen, wellness, or calm brand aesthetics
- Section backgrounds that need subtle interactive movement
- Behind CTA areas where clicks create visual ripple feedback
- Meditation, spa, or wellness client builds

## When NOT to Use

- Busy or energetic brand aesthetics (ripples are calm by nature)
- Over images or complex visuals
- Combined with other click-based interactions (ClickSpark)
- Pages with many click targets (ripples everywhere = noise)

## Pairs Well With

- `blur-text` - Calm text reveal over rippling surface
- `fade-content` - Soft fade matching the gentle ripple aesthetic
- `waves` - Waves at bottom + ripples as the main background
- `noise` - Subtle noise texture over the ripple surface

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| rippleColor | string | "rgba(255,255,255,0.1)" | Ripple ring color |
| maxRadius | number | 200 | Maximum ripple radius in px |
| speed | number | 2 | Ripple expansion speed |
| trigger | "click" \| "auto" \| "both" | "both" | When ripples spawn |
| autoInterval | number | 3000 | Auto-spawn interval in ms |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Ripple-TS-TW
```

## Lyfework Customization Notes

- Ripple color: `rgba(255,100,42,0.06)` for barely-there Lyfework brand tint
- `trigger="both"` for interactive + ambient. `"auto"` for no interaction needed.
- `autoInterval` of 2000-4000ms for calm ambient ripples
- Great for wellness, spa, and med spa client builds
- Works in GHL (Canvas or CSS animation based)

## Performance Notes

- Canvas-based ring drawing
- Each ripple is short-lived (created, expands, fades, removed)
- No memory buildup
- Works on all devices
