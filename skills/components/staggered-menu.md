---
name: staggered-menu
source: ReactBits
source_url: https://reactbits.dev/components/staggered-menu
category: components
tags: menu, staggered, entrance, animation, navigation, reveal
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# StaggeredMenu

> A menu where items enter with staggered animation, each appearing slightly after the previous one. Creates an elegant cascading reveal effect for navigation items, lists, or any sequential content. Supports multiple entrance directions and timing curves.

## When to Use

- Mobile hamburger menu overlays where items cascade in on open
- Full-screen navigation menus with dramatic sequential reveal
- Footer navigation links that animate on scroll into view
- Sidebar menus that reveal items when a panel opens
- Any list or menu that benefits from sequential entrance rather than all-at-once

## When NOT to Use

- Menus that are always visible (stagger on every page load gets annoying)
- Quick-access navigation where speed matters more than style
- Dense menus with 15+ items (stagger takes too long to complete)
- Contexts where `prefers-reduced-motion` should disable all entrance animation

## Pairs Well With

- `flowing-menu` - Flowing hover + staggered entrance for premium double-effect
- `gradient-text` - Gradient text on menu items for extra polish
- `blur-text` - Each menu item blur-reveals as part of the stagger
- `click-spark` - Spark effect when a staggered menu item is selected

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | MenuItem[] | required | Array of menu items with label, href, icon |
| staggerDelay | number | 0.08 | Delay between each item's entrance (seconds) |
| direction | "up" \| "down" \| "left" \| "right" | "up" | Direction items enter from |
| distance | number | 20 | Distance items travel during entrance in px |
| isOpen | boolean | true | Controls when the stagger animation triggers |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/StaggeredMenu-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import StaggeredMenu from '@/components/ui/StaggeredMenu';

function MobileMenu() {
  const [isOpen, setIsOpen] = useState(false);

  const menuItems = [
    { label: 'Home', href: '/' },
    { label: 'Services', href: '/services' },
    { label: 'Our Work', href: '/work' },
    { label: 'About Us', href: '/about' },
    { label: 'Blog', href: '/blog' },
    { label: 'Contact', href: '/contact' },
  ];

  return (
    <>
      <button
        onClick={() => setIsOpen(!isOpen)}
        className="fixed top-6 right-6 z-50 text-white p-2"
      >
        {isOpen ? 'Close' : 'Menu'}
      </button>

      {isOpen && (
        <div className="fixed inset-0 z-40 bg-[#0a0a0a]/95 backdrop-blur-xl flex items-center justify-center">
          <StaggeredMenu
            items={menuItems}
            staggerDelay={0.08}
            direction="up"
            distance={30}
            isOpen={isOpen}
            className="text-center space-y-6"
          />
        </div>
      )}
    </>
  );
}
```

## Lyfework Customization Notes

- Menu item font: `Manrope` 800, large size (text-4xl to text-6xl) for full-screen menus
- Item color: `text-white` with `hover:text-[#ff642a]` transition for brand hover state
- Overlay background: `bg-[#0a0a0a]/95 backdrop-blur-xl` for immersive dark glass overlay
- Stagger delay: `0.08s` feels fast and intentional; `0.12s` for a more dramatic reveal
- Entrance direction: `"up"` is standard; `"left"` works well for sidebar-style menus
- GHL compatible via React code embed; pairs well with GHL mobile menu triggers

## Performance Notes

- Framer Motion `variants` with `staggerChildren` for efficient sequenced animation
- Each item animates `opacity` and `translateY/X`, both GPU-composited
- `AnimatePresence` handles clean mount/unmount when the menu opens and closes
- Menu items are simple text/link elements; no heavy content in the animation pipeline
- Respects `prefers-reduced-motion` media query when properly configured
