---
name: floating-navbar
source: Aceternity UI
source_url: https://ui.aceternity.com/components/floating-navbar
category: navigation
tags: navbar, floating, scroll, shrink, navigation, sticky, header
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# FloatingNavbar

> Navbar that shrinks and floats as the user scrolls down, transitioning from full-width to a compact floating pill navigation.

## When to Use
- Primary site navigation on landing pages and marketing sites
- SaaS product pages with clean above-fold then persistent nav
- Portfolio sites where nav should minimize after hero scrolling
- Clinic websites with booking CTA that stays accessible
- Any page where persistent navigation should not dominate viewport

## When NOT to Use
- On single-screen applications without scrolling
- When a traditional fixed navbar is required for branding consistency
- For mobile-first sites where hamburger menu is preferred

## Pairs Well With
- `sticky-banner` - Announcement banner above the floating nav
- `dock` - Floating dock for secondary navigation below main nav
- `hero-highlight` - Hero section visible before nav floats
- `animated-content` - Page content animates below the floating nav

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| navItems | array | - | Array of { name, link, icon } navigation items |
| className | string | - | Classes for the navbar container |

## Installation
```bash
npx aceternity-ui@latest add floating-navbar
```

## Usage Example
```jsx
import { FloatingNav } from "@/components/ui/floating-navbar";

const navItems = [
  { name: "Home", link: "/" },
  { name: "Services", link: "/services" },
  { name: "Work", link: "/work" },
  { name: "About", link: "/about" },
  { name: "Contact", link: "/contact" },
];

export function SiteNavigation() {
  return (
    <FloatingNav
      navItems={navItems}
      className="bg-[#0a0a0a]/80 backdrop-blur-md border border-white/10 rounded-full"
    />
  );
}
```

## Lyfework Customization Notes
- Floating state uses `bg-[#0a0a0a]/80 backdrop-blur-md` for the glass pill effect
- Border `border-white/10` for subtle edge definition, `rounded-full` for pill shape
- Nav link text uses Manrope 400 in white, active state uses `text-[#ff642a]`
- CTA button in nav uses `from-[#ff642a] to-[#ff0301]` gradient with `rounded-[8px]`
- For GHL, ensure the navbar z-index is set to 50+ to sit above all page content

## Performance Notes
- Scroll detection uses `useScroll` with debounced threshold check, efficient
- Float transition uses framer-motion spring animation, single transition cycle
- Backdrop blur is GPU-composited but may impact Safari performance on large screens
- Nav is a fixed-position element; no layout recalculation during scroll
- Keep nav items to 5-7 for comfortable spacing in the floating pill state
