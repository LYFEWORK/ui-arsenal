---
name: tooltip
source: ReactBits
source_url: https://reactbits.dev/components/tooltip
category: components
tags: tooltip, hover, popup, info, help, contextual
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Tooltip

> Animated tooltip that appears on hover with spring physics. Supports multiple positions, custom content, and smooth enter/exit transitions.

## When to Use

- Icon buttons that need labels on hover
- Feature comparisons with info icons that explain details
- Pricing tables with "what's included" hover hints
- Navigation icons in a Dock or toolbar
- Any UI element where context needs to be surfaced without cluttering the layout

## When NOT to Use

- Critical information (tooltips are hidden by default)
- Mobile-first designs (no hover on touch)
- Long-form content (tooltips should be 1-2 sentences max)

## Pairs Well With

- `dock` - Tooltips on dock navigation icons
- `spotlight-card` - Info tooltips on feature card icons
- `tabs` - Tooltip hints on tab labels

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Trigger element |
| content | ReactNode | required | Tooltip content |
| position | "top" \| "bottom" \| "left" \| "right" | "top" | Tooltip position |
| delay | number | 200 | Delay before showing in ms |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Tooltip-TS-TW
```

## Usage Example

```jsx
import Tooltip from '@/components/ui/Tooltip';

function PricingFeature() {
  return (
    <div className="flex items-center gap-2">
      <span className="text-white">AI Follow-Up Engine</span>
      <Tooltip content="Automated SMS and email sequences triggered by patient behavior." position="top">
        <span className="text-gray-500 cursor-help">ⓘ</span>
      </Tooltip>
    </div>
  );
}
```

## Lyfework Customization Notes

- Tooltip background: `lyf-glass` styling (dark blur panel)
- Text: Manrope 400, 13px, white
- Keep content to 1-2 short sentences max
- `delay` of 150-300ms prevents accidental triggers
- Works in GHL with React embeds

## Performance Notes

- framer-motion AnimatePresence for enter/exit
- Portal rendering to avoid overflow clipping
- Minimal footprint
