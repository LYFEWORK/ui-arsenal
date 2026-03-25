---
name: bubble-menu
source: ReactBits
source_url: https://reactbits.dev/components/bubble-menu
category: navigation
tags: navigation, bubble, floating, radial, menu, circular, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# BubbleMenu

> A floating circular menu that expands from a single button into radial options. Items bubble out in a circle or arc from the trigger point. Playful, space-efficient navigation.

## When to Use

- Floating action menus (like Material Design FAB but animated)
- Mobile-friendly quick-action menus
- Dashboard tool palettes
- Creative site navigation alternatives
- Compact action menus where space is limited

## When NOT to Use

- Primary site navigation (too hidden, users won't find it)
- More than 6-7 menu items (circle gets crowded)
- Accessibility-critical contexts (radial menus are hard to navigate with keyboard)
- Desktop-first sites where a standard nav works fine

## Pairs Well With

- `tooltip` - Tooltips on each bubble item
- `click-spark` - Sparks when opening the bubble menu
- `magnet` - Magnetic pull on the trigger button

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | MenuItem[] | [] | Array of menu items with icon and action |
| triggerIcon | ReactNode | required | Icon for the trigger button |
| radius | number | 80 | Expansion radius in px |
| arc | number | 360 | Arc angle in degrees (360 = full circle) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/BubbleMenu-TS-TW
```

## Lyfework Customization Notes

- Trigger button: Lyfework gradient background with white icon
- Item buttons: glass background matching `lyf-glass`
- `radius` of 70-100px. `arc` of 180 for half-circle (bottom trigger) or 360 for full.
- Spring animation on expand/collapse
- Works in GHL with framer-motion

## Performance Notes

- framer-motion spring animations for bubble expansion
- Only trigger + visible items in DOM when expanded
- Lightweight, no performance concerns
