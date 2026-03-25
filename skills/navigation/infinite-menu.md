---
name: infinite-menu
source: ReactBits
source_url: https://reactbits.dev/components/infinite-menu
category: navigation
tags: navigation, menu, infinite, scroll, creative, fullscreen, immersive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# InfiniteMenu

> A fullscreen menu with items arranged in a continuous scrolling loop. Items rotate infinitely with smooth momentum scrolling. Highly visual and immersive navigation experience.

## When to Use

- Portfolio or agency websites where navigation IS the experience
- Single-page sites with 4-6 major sections
- Creative/design agency landing pages
- Lyfework's own website or showcase builds
- Any build where the client wants "something nobody else has"

## When NOT to Use

- E-commerce or utility-focused sites (users need to find things fast)
- Sites with more than 8 navigation items
- Content-heavy sites where navigation should be invisible
- Mobile-first designs where this pattern doesn't translate well

## Pairs Well With

- `aurora` - Aurora background visible through the menu for atmosphere
- `gradient-text` - Menu item labels with animated gradient
- `blur-text` - Items blur-reveal as they rotate into the active position
- `splash-cursor` - Creative cursor effect over the infinite menu

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | MenuItem[] | [] | Array of menu items |
| speed | number | 1 | Scroll speed multiplier |
| gap | number | 20 | Gap between items in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/InfiniteMenu-TS-TW
```

## Usage Example

```jsx
import InfiniteMenu from '@/components/ui/InfiniteMenu';

function FullscreenNav() {
  const items = [
    { label: 'Services', href: '#services', image: '/img/nav-services.jpg' },
    { label: 'Work', href: '#work', image: '/img/nav-work.jpg' },
    { label: 'About', href: '#about', image: '/img/nav-about.jpg' },
    { label: 'Contact', href: '#contact', image: '/img/nav-contact.jpg' },
  ];

  return (
    <div className="fixed inset-0 z-50 bg-black/95">
      <InfiniteMenu
        items={items}
        speed={0.8}
        className="h-full"
      />
    </div>
  );
}
```

## Lyfework Customization Notes

- Use for Lyfework's own site or premium showcase builds only. Most client sites need conventional navigation.
- Pair with high-quality background images per menu item for maximum impact
- Menu text should be Manrope 800 at 5xl+ size
- Keep to 4-6 items maximum for this pattern
- Trigger via a hamburger icon that opens the fullscreen overlay
- For GHL: this is a complex component. Only use in React builds, not in raw GHL HTML sections.
- Consider this a "signature move" component that makes a site unforgettable

## Performance Notes

- framer-motion handles the infinite loop and momentum physics
- Images should be optimized and lazy-loaded
- The fullscreen overlay should use `will-change: transform` for smooth animation
- On mobile, this becomes a vertically scrolling fullscreen menu
- Heavier than standard nav components, only use when the design calls for it
