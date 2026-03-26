---
name: pill-nav
source: ReactBits
source_url: https://reactbits.dev/components/pill-nav
category: components
tags: navigation, pill, tabs, indicator, sliding, animated
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# PillNav

> A pill-shaped sliding indicator navigation where a rounded highlight slides between items on selection. The active indicator morphs its width to match the selected item and glides smoothly using shared layout animation. Clean, minimal, and universally usable.

## When to Use

- Tab navigation within content sections (features, pricing tiers, FAQ categories)
- Filter bars for portfolio or blog categories
- Settings or preference toggles with multiple options
- Segmented controls in web app interfaces
- Any horizontal menu that needs a clear active state indicator

## When NOT to Use

- Vertical sidebar navigation (pill slides horizontally)
- Navigation with more than 6-7 items (pill gets too small to be meaningful)
- Contexts where a traditional underline tab style is expected
- Deeply nested or hierarchical navigation structures

## Pairs Well With

- `animated-content` - Content below the tabs animates on tab change
- `gradient-text` - Gradient text on the active pill item
- `blur-text` - Blur-transition content when switching tabs
- `spotlight-card` - Spotlight cards within the tab content panels

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | string[] | required | Array of tab/nav labels |
| activeIndex | number | 0 | Currently active item index |
| onChange | (index: number) => void | required | Callback on item selection |
| pillColor | string | "rgba(255,100,42,0.12)" | Background color of the pill indicator |
| textColor | string | "#ffffff" | Active item text color |
| inactiveColor | string | "#9ca3af" | Inactive item text color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/PillNav-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import PillNav from '@/components/ui/PillNav';

function PricingSection() {
  const [billing, setBilling] = useState(0);
  const plans = ['Monthly', 'Quarterly', 'Annual'];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-8">
        Simple, Transparent Pricing
      </h2>
      <div className="flex justify-center mb-12">
        <PillNav
          items={plans}
          activeIndex={billing}
          onChange={setBilling}
          pillColor="rgba(255,100,42,0.12)"
          textColor="#ffffff"
          inactiveColor="#6b7280"
          className="bg-white/[0.03] rounded-full p-1 border border-white/5"
        />
      </div>
      {/* Pricing cards change based on billing state */}
      <div className="max-w-5xl mx-auto">
        {billing === 0 && <p className="text-gray-400 text-center">Monthly pricing cards here</p>}
        {billing === 1 && <p className="text-gray-400 text-center">Quarterly pricing (save 10%)</p>}
        {billing === 2 && <p className="text-gray-400 text-center">Annual pricing (save 25%)</p>}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Pill indicator color: `rgba(255,100,42,0.12)` Lyfework orange at low opacity
- Container background: `bg-white/[0.03]` with `border border-white/5` and `rounded-full`
- Active text: `text-white font-bold`, inactive: `text-gray-500 font-medium`
- Font: `Manrope` 600 for nav items, 14px size
- Border radius: `rounded-full` for the outer container, pill shape for the indicator
- GHL compatible -- Framer Motion handles the pill slide, minimal bundle impact

## Performance Notes

- Framer Motion `layoutId` creates a single shared element that slides between positions
- Only one pill indicator element exists in the DOM; no duplicate rendering
- Width morphing uses `layout` animation with FLIP technique for 60fps
- CSS `will-change: transform` on the pill for compositor optimization
- Lightweight component; safe to render multiple PillNav instances on one page
