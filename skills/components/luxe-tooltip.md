---
name: luxe-tooltip
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-tooltip
category: components
tags: tooltip, popover, hover, spring, info, hint
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LuxeTooltip

> Tooltip with smooth spring-animated enter and exit transitions, supporting multiple placement positions.

## When to Use
- Icon buttons that need contextual labels on hover
- Dashboard elements with abbreviated text needing full descriptions
- Form fields with helper text that appears on focus/hover
- Navigation items with supplementary information
- Feature cards with "i" icons revealing additional details

## When NOT to Use
- Long content that should be in a popover or modal instead
- Mobile-primary interfaces where hover tooltips are inaccessible
- Critical information that must be visible without interaction
- Interactive content with links or buttons — use a popover instead

## Pairs Well With
- `dock` - tooltips on dock items showing labels on hover
- `luxe-input` - tooltip on info icon next to form field labels
- `luxe-badge` - tooltip on badge explaining the status meaning
- `spotlight-card` - tooltip on card icons for feature descriptions

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| content | ReactNode | — | Tooltip content |
| children | ReactNode | — | Trigger element |
| side | "top" \| "bottom" \| "left" \| "right" | "top" | Placement side |
| align | "start" \| "center" \| "end" | "center" | Alignment on the side |
| delay | number | 200 | Delay before showing (ms) |
| className | string | — | Tooltip content CSS classes |
| sideOffset | number | 4 | Distance from trigger in pixels |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-tooltip"
```

## Usage Example
```jsx
import { LuxeTooltip } from "@/components/ui/luxe-tooltip";
import { Info } from "lucide-react";

export function FeatureWithTooltip() {
  return (
    <div className="flex items-center gap-2 bg-[#0a0a0a] p-6">
      <h3 className="font-manrope font-700 text-white">HIPAA Compliant</h3>
      <LuxeTooltip
        content="All patient data is encrypted at rest and in transit with SOC2 certified infrastructure."
        side="top"
        className="lyf-glass rounded-[8px] px-3 py-2 font-manrope font-400 text-sm text-white max-w-xs"
      >
        <Info className="w-4 h-4 text-[#ff642a] cursor-help" />
      </LuxeTooltip>
    </div>
  );
}
```

## Lyfework Customization Notes
- Tooltip container: `lyf-glass rounded-[8px]` for brand glass styling
- Text: `font-manrope font-400 text-sm text-white` for readability
- Icon triggers should use `text-[#ff642a]` brand orange color
- Background matches `#0a0a0a` theme with glass blur overlay
- GHL compatible — tooltip renders as a portal, works in iframe contexts
- Arrow/caret should match the glass background for seamless appearance

## Performance Notes
- Tooltip content is lazily mounted — not in DOM until triggered
- Spring animation uses framer-motion AnimatePresence for clean enter/exit
- Delay prop prevents accidental tooltip flashing during cursor movement
- Portal rendering avoids overflow clipping from parent containers
- Auto-cleanup on unmount — no orphaned tooltip elements
