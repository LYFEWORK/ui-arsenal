---
name: lanyard
source: ReactBits
source_url: https://reactbits.dev/components/lanyard
category: components
tags: lanyard, badge, 3d, card, physics, interactive, spring
dependencies: three.js, react-three-fiber
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# Lanyard

> A 3D badge/card hanging from a lanyard string with physics-based swinging. Responds to mouse interaction with realistic spring dynamics. The badge rotates and swings when dragged.

## When to Use

- Contact or profile cards with a playful twist
- Conference or event landing pages
- Team member "badges" on about pages
- Creative personal portfolio sites
- Interactive business card displays

## When NOT to Use

- Standard business websites (too playful)
- Mobile-first designs (3D interaction is limited on touch)
- Dense layouts with multiple cards
- Fast-loading pages where Three.js overhead isn't justified

## Pairs Well With

- `aurora` - Lanyard badge swinging over an aurora background
- `galaxy` - Badge floating in a star field
- `blur-text` - Name blur-reveals on the badge

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| cardContent | ReactNode | required | Badge face content |
| stringColor | string | "#ffffff" | Lanyard string color |
| stringLength | number | 200 | String length in px |
| cardWidth | number | 250 | Badge width |
| cardHeight | number | 350 | Badge height |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Lanyard-TS-TW
```

## Usage Example

```jsx
import Lanyard from '@/components/ui/Lanyard';

function ContactBadge() {
  return (
    <Lanyard
      stringColor="#ff642a"
      cardWidth={280}
      cardHeight={380}
      cardContent={
        <div className="p-8 text-center bg-[#111] rounded-2xl h-full flex flex-col justify-center">
          <img src="/team/justyn.jpg" className="w-20 h-20 rounded-full mx-auto" />
          <h3 className="mt-4 text-lg font-bold text-white">Justyn Cruz</h3>
          <p className="text-sm text-gray-400">Founder, Lyfework</p>
        </div>
      }
    />
  );
}
```

## Lyfework Customization Notes

- String color: `#ff642a` for Lyfework brand
- Tier 3 showcase. Use for the Lyfework contact page or creative client builds.
- Three.js + React Three Fiber are heavy dependencies. Only load for this specific page.
- Not for GHL (requires Three.js)
- Desktop-focused. Provide static card fallback on mobile.

## Performance Notes

- Three.js + React Three Fiber (~200kb combined)
- Physics simulation runs on requestAnimationFrame
- Heavy for a single component. Only justify on pages where this IS the experience.
- Lazy load the component to prevent blocking page render
