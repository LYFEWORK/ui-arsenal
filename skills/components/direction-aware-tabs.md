---
name: direction-aware-tabs
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/direction-aware-tabs
category: components
tags: tabs, navigation, direction, indicator, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# DirectionAwareTabs

> Tabs with direction-aware sliding indicator that tracks from the previous to next tab position.

## When to Use
- Content section tabbed navigation with polished transitions
- Feature comparison views with multiple categories
- Dashboard view switching with smooth tab indicators
- Settings pages with categorized option panels
- Any tabbed interface wanting premium sliding animation

## When NOT to Use
- More than 6 tabs (use scrollable tabs or dropdown)
- Full-page navigation (use proper route-based navigation)
- Very narrow mobile layouts where tabs don't fit

## Pairs Well With
- `animated-content` - Tab content with entrance/exit animations
- `gradient-text` - Active tab title in gradient text
- `spotlight-card` - Content cards inside each tab panel
- `number-ticker` - Animated stats that change per tab

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| tabs | { label: string; value: string; content: ReactNode }[] | [] | Tab definitions |
| defaultValue | string | '' | Initially active tab |
| onChange | (value: string) => void | - | Tab change handler |
| variant | 'line' \| 'pill' \| 'enclosed' | 'line' | Tab style variant |
| indicatorColor | string | '#ff642a' | Active tab indicator color |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/direction-aware-tabs"
```

## Usage Example
```jsx
import { DirectionAwareTabs } from "@/components/ui/direction-aware-tabs";

export function ServiceTabs() {
  const tabs = [
    {
      label: "Web Design",
      value: "design",
      content: (
        <div className="p-6">
          <h3 className="font-manrope font-700 text-2xl text-white">Custom Web Design</h3>
          <p className="font-manrope font-400 text-white/60 mt-3">
            Pixel-perfect designs tailored to your brand and conversion goals.
          </p>
        </div>
      ),
    },
    {
      label: "Development",
      value: "dev",
      content: (
        <div className="p-6">
          <h3 className="font-manrope font-700 text-2xl text-white">Full-Stack Development</h3>
          <p className="font-manrope font-400 text-white/60 mt-3">
            Next.js, React, and GHL integrations for scalable solutions.
          </p>
        </div>
      ),
    },
    {
      label: "Marketing",
      value: "marketing",
      content: (
        <div className="p-6">
          <h3 className="font-manrope font-700 text-2xl text-white">Growth Marketing</h3>
          <p className="font-manrope font-400 text-white/60 mt-3">
            Data-driven campaigns that fill your pipeline consistently.
          </p>
        </div>
      ),
    },
  ];

  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <DirectionAwareTabs
        tabs={tabs}
        defaultValue="design"
        variant="line"
        indicatorColor="#ff642a"
        className="max-w-4xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Indicator color: brand orange #ff642a for active tab underline
- Tab labels: Manrope 700, inactive text-white/40, active text-white
- Tab content: Manrope 400 body text on #0a0a0a background
- Use variant="line" for most cases; "pill" for compact toolbars
- GHL compatible -- standard tab navigation pattern

## Performance Notes
- Framer Motion layoutId creates smooth FLIP indicator transitions
- Only active tab content is rendered (lazy panel mounting)
- Direction detection uses simple index comparison (no complex math)
- Tab indicator uses GPU-accelerated transform and width animation
- Keyboard navigation (arrow keys) included for accessibility
