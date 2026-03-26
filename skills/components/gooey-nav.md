---
name: gooey-nav
source: ReactBits
source_url: https://reactbits.dev/components/gooey-nav
category: components
tags: navigation, gooey, sticky, liquid, svg, filter, playful
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GooeyNav

> A gooey, sticky liquid navigation where menu items blend and merge with an SVG filter effect. When hovered, the active indicator stretches and morphs between items with a viscous, organic feel. Uses SVG `feGaussianBlur` and `feColorMatrix` filters.

## When to Use

- Creative agency or studio sites that want a playful, unique navigation
- Portfolio sites where personality and experimentation are valued
- Social or community platforms with fun, casual brand identities
- Experimental landing pages that prioritize "wow factor" over convention
- Bottom navigation bars in web apps with a mobile-app feel

## When NOT to Use

- Corporate or professional sites where gooey effects feel unprofessional
- Accessibility-focused interfaces where organic morphing confuses screen readers
- Dense navigation with many items (gooey effect gets messy with 7+ items)
- Performance-constrained environments (SVG filters can be expensive)

## Pairs Well With

- `click-spark` - Spark effect on gooey nav item click
- `gradient-text` - Gradient-colored active nav item text
- `animated-content` - Scroll-reveal the navigation bar on load
- `blur-text` - Blur-reveal nav labels on page enter

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | NavItem[] | required | Array of menu items with label, href, icon |
| activeIndex | number | 0 | Currently active item |
| onChange | (index: number) => void | undefined | Callback on item selection |
| blobColor | string | "#ff642a" | Color of the gooey indicator blob |
| intensity | number | 10 | Gooey filter blur intensity |
| position | "top" \| "bottom" | "bottom" | Navigation position |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GooeyNav-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import GooeyNav from '@/components/ui/GooeyNav';
import { Home, Briefcase, FolderOpen, User, Mail } from 'lucide-react';

function BottomNav() {
  const [active, setActive] = useState(0);

  const items = [
    { label: 'Home', href: '/', icon: <Home size={20} /> },
    { label: 'Services', href: '/services', icon: <Briefcase size={20} /> },
    { label: 'Work', href: '/work', icon: <FolderOpen size={20} /> },
    { label: 'About', href: '/about', icon: <User size={20} /> },
    { label: 'Contact', href: '/contact', icon: <Mail size={20} /> },
  ];

  return (
    <nav className="fixed bottom-0 w-full z-50 bg-[#0a0a0a]/90 backdrop-blur-xl border-t border-white/5 py-2">
      <GooeyNav
        items={items}
        activeIndex={active}
        onChange={setActive}
        blobColor="#ff642a"
        intensity={12}
        position="bottom"
        className="max-w-md mx-auto"
      />
    </nav>
  );
}
```

## Lyfework Customization Notes

- Blob color: `#ff642a` Lyfework orange for the gooey indicator
- Nav background: `bg-[#0a0a0a]/90 backdrop-blur-xl` for frosted dark glass bar
- Active icon: `text-white`, inactive: `text-gray-500`
- SVG filter is inline in the component; no external SVG file needed
- Font: `Manrope` 600 for nav labels, 12px size for bottom nav text
- GHL compatible as a standalone code snippet; SVG filter is self-contained

## Performance Notes

- SVG filter (`feGaussianBlur` + `feColorMatrix`) runs on the GPU in modern browsers
- Filter is applied to a single indicator element, not to all nav items
- Position transitions use CSS `transform: translateX()` for compositor-only animation
- Keep items to 5 or fewer for optimal gooey visual effect
- The SVG filter definition is rendered once and referenced via `filter: url(#gooey)`
