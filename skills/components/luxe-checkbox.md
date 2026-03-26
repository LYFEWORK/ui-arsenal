---
name: luxe-checkbox
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-checkbox
category: components
tags: checkbox, form, animated, spring, toggle, check
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LuxeCheckbox

> Checkbox with a satisfying spring-animated checkmark that bounces into place on toggle.

## When to Use
- Form checkboxes for terms acceptance, newsletter opt-in, or preferences
- Todo/task lists where checking items should feel rewarding
- Settings panels with toggle options presented as checkboxes
- Multi-select filters on portfolio or service listing pages
- Onboarding checklists where progress visualization matters

## When NOT to Use
- Binary on/off toggles — use luxe-switch instead for clearer semantics
- Radio button scenarios where only one option can be selected
- Dense data tables with checkboxes on every row — spring animation is excessive
- Non-interactive display of checked/unchecked states

## Pairs Well With
- `luxe-input` - consistent Luxe form element family for cohesive forms
- `luxe-switch` - use checkbox for multi-select, switch for on/off in same form
- `multi-step-modal` - animated checkboxes inside modal form steps
- `animated-content` - stagger-animate a list of checkboxes on scroll

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| checked | boolean | false | Controlled checked state |
| onCheckedChange | (checked: boolean) => void | — | Callback on toggle |
| label | string | — | Associated label text |
| className | string | — | Additional CSS classes |
| disabled | boolean | false | Disable the checkbox |
| id | string | — | Input element ID |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-checkbox"
```

## Usage Example
```jsx
import { LuxeCheckbox } from "@/components/ui/luxe-checkbox";
import { useState } from "react";

export function ConsentForm() {
  const [agreed, setAgreed] = useState(false);
  const [newsletter, setNewsletter] = useState(false);

  return (
    <div className="space-y-4 lyf-glass rounded-[12px] p-6 bg-[#0a0a0a]/80">
      <LuxeCheckbox
        checked={agreed}
        onCheckedChange={setAgreed}
        label="I agree to the terms of service"
        className="text-white font-manrope font-400 accent-[#ff642a]"
      />
      <LuxeCheckbox
        checked={newsletter}
        onCheckedChange={setNewsletter}
        label="Send me practice growth tips"
        className="text-white font-manrope font-400 accent-[#ff642a]"
      />
      <button
        disabled={!agreed}
        className="w-full py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white disabled:opacity-40"
      >
        Continue
      </button>
    </div>
  );
}
```

## Lyfework Customization Notes
- Checked state color: `accent-[#ff642a]` or custom check SVG with brand orange
- Label text: `font-manrope font-400 text-white` on dark backgrounds
- Wrap in `lyf-glass rounded-[12px]` containers for form sections
- Checkmark SVG path should animate with spring physics via framer-motion
- GHL form compatible — maps to standard checkbox input element
- Disabled state uses `opacity-40` for consistent Lyfework disabled styling

## Performance Notes
- Spring animation runs only on toggle — no idle computation
- SVG path animation is GPU-accelerated via framer-motion
- Single motion.path element — minimal DOM footprint
- Animation completes in ~400ms — fast enough to not block interaction
- Works with React Hook Form controlled/uncontrolled patterns
