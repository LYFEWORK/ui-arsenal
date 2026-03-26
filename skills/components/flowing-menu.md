---
name: flowing-menu
source: ReactBits
source_url: https://reactbits.dev/components/flowing-menu
category: components
tags: menu, flowing, liquid, hover, navigation, smooth
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# FlowingMenu

> A navigation menu with flowing, liquid-style hover transitions. When the user hovers between items, a highlight shape smoothly morphs and slides to follow the cursor, creating a fluid, organic navigation feel.

## When to Use

- Main navigation bars on SaaS landing pages or agency sites
- Tab-style navigation within feature sections
- Service category selectors where hover feedback matters
- Footer navigation with a premium interactive feel
- Any horizontal menu that needs to feel more alive than static hover states

## When NOT to Use

- Dropdown or mega-menu navigation (flowing effect doesn't translate to nested items)
- Mobile navigation (hover doesn't exist on touch)
- Dense navigation with 10+ items (flowing highlight becomes jumpy)
- Accessibility-strict contexts where motion-reduced users need static states

## Pairs Well With

- `gradient-text` - Gradient-colored active menu item text
- `animated-content` - Scroll-reveal the navigation bar
- `blur-text` - Blur-reveal menu items on page load
- `click-spark` - Spark effect on menu item click/selection

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | MenuItem[] | required | Array of menu items with label, href, icon |
| activeIndex | number | 0 | Currently active menu item |
| highlightColor | string | "rgba(255,100,42,0.1)" | Background color of the flowing highlight |
| borderRadius | string | "8px" | Border radius of the highlight shape |
| onChange | (index: number) => void | undefined | Callback on item click |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FlowingMenu-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import FlowingMenu from '@/components/ui/FlowingMenu';

function SiteHeader() {
  const [active, setActive] = useState(0);

  const navItems = [
    { label: 'Home', href: '/' },
    { label: 'Services', href: '/services' },
    { label: 'Work', href: '/work' },
    { label: 'About', href: '/about' },
    { label: 'Contact', href: '/contact' },
  ];

  return (
    <header className="fixed top-0 w-full z-50 bg-[#0a0a0a]/80 backdrop-blur-xl border-b border-white/5">
      <nav className="max-w-6xl mx-auto px-8 py-4 flex items-center justify-between">
        <span className="text-xl font-extrabold text-white font-[Manrope]">
          Lyfework
        </span>
        <FlowingMenu
          items={navItems}
          activeIndex={active}
          onChange={setActive}
          highlightColor="rgba(255,100,42,0.08)"
          borderRadius="8px"
        />
        <a
          href="/book"
          className="px-5 py-2 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white text-sm font-bold rounded-lg"
        >
          Book a Call
        </a>
      </nav>
    </header>
  );
}
```

## Lyfework Customization Notes

- Highlight color: `rgba(255,100,42,0.08)` for Lyfework brand orange at low opacity
- Active item text: `text-white font-bold`, inactive: `text-gray-400 font-medium`
- Border radius on highlight: `8px` matches Lyfework button radius standard
- Header background: `bg-[#0a0a0a]/80 backdrop-blur-xl` for the frosted glass nav bar
- Font: `Manrope` 700 for brand name, 500 for nav items
- GHL: works in custom code headers; ensure Framer Motion is available in the bundle

## Performance Notes

- Flowing highlight uses Framer Motion `layout` animation with `layoutId` for FLIP transitions
- Only one highlight element exists in the DOM; it morphs position via GPU transforms
- Hover detection uses pointer events, not mousemove listeners
- Animation duration: 300-400ms with spring physics for natural feel
- Degrades gracefully without JS to a standard CSS hover underline
