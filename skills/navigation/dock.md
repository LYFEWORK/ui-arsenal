---
name: dock
source: ReactBits
source_url: https://reactbits.dev/components/dock
category: navigation
tags: navigation, dock, menu, macOS, hover, magnification, bottom-bar
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Dock

> A macOS-style dock navigation bar with icon magnification on hover. Items scale up as the cursor approaches. Perfect for sticky bottom navigation or floating action menus.

## When to Use

- Floating bottom navigation on single-page websites
- Dashboard or web app navigation where space is limited
- Portfolio sites with minimal, elegant nav requirements
- Any layout where a traditional top navbar feels too heavy
- Mobile-first designs that need a thumb-friendly nav pattern

## When NOT to Use

- Sites with more than 7 navigation items (dock gets crowded)
- Traditional corporate sites where a standard header nav is expected
- E-commerce with complex mega-menus
- Sites where navigation labels are essential (dock is icon-first)

## Pairs Well With

- `aurora` - Floating dock over aurora hero for immersive single-page sites
- `animated-content` - Page sections that reveal as user navigates via dock
- `magnet` - Magnetic cursor effect that complements the dock's hover behavior
- `spotlight-card` - Content sections that the dock navigates to

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | DockItem[] | [] | Array of dock items with icon and action |
| magnification | number | 60 | Max icon size on hover (px) |
| baseSize | number | 40 | Default icon size (px) |
| distance | number | 140 | Mouse distance for magnification effect |
| position | "bottom" \| "top" \| "left" \| "right" | "bottom" | Dock position |
| className | string | "" | Additional CSS classes |

### DockItem Shape

```typescript
interface DockItem {
  icon: ReactNode;
  label: string;
  onClick: () => void;
}
```

## Installation

```bash
npx shadcn@latest add @react-bits/Dock-TS-TW
```

## Usage Example

```jsx
import Dock from '@/components/ui/Dock';
import { Home, Briefcase, User, Mail, Settings } from 'lucide-react';

function Navigation() {
  const scrollTo = (id) => {
    document.getElementById(id)?.scrollIntoView({ behavior: 'smooth' });
  };

  const items = [
    { icon: <Home size={18} />, label: 'Home', onClick: () => scrollTo('hero') },
    { icon: <Briefcase size={18} />, label: 'Services', onClick: () => scrollTo('services') },
    { icon: <User size={18} />, label: 'About', onClick: () => scrollTo('about') },
    { icon: <Mail size={18} />, label: 'Contact', onClick: () => scrollTo('contact') },
  ];

  return (
    <div className="fixed bottom-8 left-1/2 -translate-x-1/2 z-50">
      <Dock
        items={items}
        magnification={56}
        baseSize={36}
        distance={120}
        className="bg-black/60 backdrop-blur-xl border border-white/10 rounded-2xl px-4 py-2"
      />
    </div>
  );
}
```

## Lyfework Customization Notes

- Dock background: `bg-black/60 backdrop-blur-xl border border-white/10` (matches lyf-glass)
- Use Lucide React icons for consistency across Lyfework builds
- `magnification` of 52-60 and `baseSize` of 34-40 feels premium
- Always position at bottom-center with `fixed bottom-8 left-1/2 -translate-x-1/2 z-50`
- For GHL funnel pages: the dock may conflict with GHL's sticky footer elements. Test z-index stacking.
- On mobile, the magnification effect degrades. Consider a simpler bottom nav for mobile breakpoints.
- Add `rounded-2xl` to match Lyfework's 16px glass panel radius

## Performance Notes

- framer-motion handles the magnification spring animations
- Minimal CPU cost since it only animates on hover
- No scroll listeners, no intersection observers
- Works well as a fixed element without layout shift
- SSR compatible
