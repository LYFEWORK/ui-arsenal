---
name: gradient-button-group
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/gradient-button-group
category: components
tags: button, group, gradient, shared, segmented
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# GradientButtonGroup

> Grouped buttons with a shared gradient that flows across the entire group.

## When to Use
- Segmented controls with unified gradient background
- Toggle button groups for view switching (grid/list, tabs)
- Filter button groups on dashboard or listing pages
- Pricing plan selection with visually connected options
- Any grouped actions that should feel unified

## When NOT to Use
- Individual standalone buttons (use single gradient button)
- More than 4-5 options (use tabs or dropdown instead)
- Form submit/cancel pairs where visual separation is important

## Pairs Well With
- `direction-aware-tabs` - Alternative navigation pattern for more complex cases
- `animated-content` - Content that changes based on button group selection
- `spotlight-card` - Button group controlling which card is spotlighted
- `number-ticker` - Stats that update based on selected button group option

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | { label: string; value: string; icon?: ReactNode }[] | [] | Button group items |
| value | string | '' | Currently selected value |
| onChange | (value: string) => void | - | Selection change handler |
| gradient | string[] | ['#ff642a', '#ff0301'] | Shared gradient colors |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Button size |
| rounded | boolean | true | Fully rounded group |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/gradient-button-group"
```

## Usage Example
```jsx
import { GradientButtonGroup } from "@/components/ui/gradient-button-group";
import { useState } from "react";

export function ViewToggle() {
  const [view, setView] = useState("monthly");

  return (
    <section className="bg-[#0a0a0a] py-24 px-6 text-center">
      <h2 className="font-manrope font-800 text-4xl text-white mb-8">
        Choose Your Plan
      </h2>
      <GradientButtonGroup
        items={[
          { label: "Monthly", value: "monthly" },
          { label: "Annually", value: "annually" },
        ]}
        value={view}
        onChange={setView}
        gradient={["#ff642a", "#ff0301"]}
        size="md"
        className="font-manrope font-700"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Brand gradient ["#ff642a", "#ff0301"] flows across entire group
- Manrope 700 for button labels, white text on gradient, white/60 inactive
- Use rounded-[8px] matching button radius standard
- Inactive segments: bg-white/5 on #0a0a0a background
- GHL compatible -- standard HTML buttons with CSS gradient

## Performance Notes
- Pure CSS gradient with no JavaScript animation
- Selection indicator slides via CSS transform (GPU-accelerated)
- Zero repaints on selection change (only transform update)
- No dependencies -- vanilla React component
- Sub-2KB component with no external requirements
