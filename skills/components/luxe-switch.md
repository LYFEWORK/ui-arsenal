---
name: luxe-switch
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-switch
category: components
tags: switch, toggle, form, spring, on-off, settings
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LuxeSwitch

> Toggle switch with satisfying spring physics animation and smooth thumb transition.

## When to Use
- Settings panels for on/off toggles (dark mode, notifications, features)
- Pricing page monthly/yearly billing toggle
- Dashboard feature flags or preference switches
- Form sections toggling optional fields on/off
- Any binary toggle where the switch metaphor is clearest

## When NOT to Use
- Multi-option selections — use radio buttons or animated-tabs instead
- Checkbox lists where multiple items are independently togglable
- Actions that trigger immediately and are irreversible — use a confirmation dialog
- Very small UI contexts where the switch thumb is hard to tap

## Pairs Well With
- `luxe-checkbox` - use switch for on/off, checkbox for agree/accept in same form
- `luxe-input` - switch toggles visibility of conditional input fields
- `animated-tabs` - switch for binary, tabs for 3+ option toggles
- `number-ticker` - animate price change when toggling monthly/yearly billing

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| checked | boolean | false | Controlled toggle state |
| onCheckedChange | (checked: boolean) => void | — | Callback on toggle |
| label | string | — | Associated label text |
| className | string | — | Additional CSS classes |
| disabled | boolean | false | Disable the switch |
| size | "sm" \| "md" \| "lg" | "md" | Switch size preset |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-switch"
```

## Usage Example
```jsx
import { LuxeSwitch } from "@/components/ui/luxe-switch";
import { useState } from "react";

export function PricingToggle() {
  const [yearly, setYearly] = useState(false);

  return (
    <div className="flex items-center justify-center gap-4 py-8 bg-[#0a0a0a]">
      <span className={`font-manrope font-700 ${!yearly ? "text-white" : "text-gray-500"}`}>
        Monthly
      </span>
      <LuxeSwitch
        checked={yearly}
        onCheckedChange={setYearly}
        className="data-[state=checked]:bg-gradient-to-r data-[state=checked]:from-[#ff642a] data-[state=checked]:to-[#ff0301]"
      />
      <span className={`font-manrope font-700 ${yearly ? "text-white" : "text-gray-500"}`}>
        Yearly
        <span className="ml-2 text-xs text-[#ff642a]">Save 20%</span>
      </span>
    </div>
  );
}
```

## Lyfework Customization Notes
- Active/checked background: `bg-gradient-to-r from-[#ff642a] to-[#ff0301]`
- Inactive background: `bg-white/10` on dark backgrounds
- Thumb color should be white for contrast on brand gradient track
- Label text: `font-manrope font-700` for clear readability
- GHL compatible — renders as accessible switch role element
- On `#0a0a0a` backgrounds, add subtle `ring-1 ring-white/10` for inactive state definition

## Performance Notes
- Spring animation on thumb uses framer-motion layout animation — single element
- Track color transition uses CSS transition — no JS overhead
- Completes toggle animation in ~250ms for snappy feedback
- Accessible — properly implements switch role with keyboard support
- No layout shift — thumb moves via transform within fixed-size track
