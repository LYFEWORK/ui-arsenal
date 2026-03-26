---
name: ripple-button
source: Magic UI
source_url: https://magicui.design/docs/components/ripple-button
category: components
tags: button, ripple, click, material, feedback
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# RippleButton

> Button with a material-design-style ripple effect that emanates from the click point.

## When to Use
- Form submission buttons needing tactile click feedback
- Action buttons throughout a UI for consistent interaction feel
- Mobile-friendly buttons where touch feedback matters
- Dashboard action buttons (save, delete, confirm)
- Any button requiring immediate visual click acknowledgment

## When NOT to Use
- Decorative buttons that should not imply immediate action
- Ghost/text buttons where ripple effect obscures the label
- Contexts already using pulsating-button or shimmer-button
- Icon-only micro buttons where ripple extends beyond bounds

## Pairs Well With
- `animated-content` - Fade in button groups with stagger
- `spotlight-card` - Ripple buttons inside interactive cards
- `gradient-text` - Section headings above button groups
- `click-spark` - Layer spark particles on top of the ripple

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Button label content |
| className | string | "" | Additional CSS classes |
| rippleColor | string | "#ffffff" | Color of the ripple effect |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/ripple-button"
```

## Usage Example
```jsx
import { RippleButton } from "@/components/magicui/ripple-button";

export function BookingActions() {
  return (
    <section className="bg-[#0a0a0a] py-16">
      <div className="mx-auto max-w-md lyf-glass rounded-[12px] p-8">
        <h3 className="font-manrope font-700 text-xl text-white mb-6">Confirm your appointment</h3>
        <div className="flex gap-4">
          <RippleButton
            rippleColor="#ffffff40"
            className="flex-1 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 py-3 rounded-[8px]"
          >
            Confirm
          </RippleButton>
          <RippleButton
            rippleColor="#ff642a40"
            className="flex-1 border border-white/20 text-white font-manrope font-700 py-3 rounded-[8px]"
          >
            Reschedule
          </RippleButton>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `rippleColor` to `#ffffff40` (white with opacity) for primary buttons
- Use `#ff642a40` (brand orange with opacity) for outline/secondary buttons
- Apply `rounded-[8px]` for button border-radius convention
- Manrope font-700 for button labels
- GHL compatible — click handler uses basic DOM events, no framework-specific APIs

## Performance Notes
- Ripple creates a temporary DOM element that auto-removes after animation
- CSS animation with `transform: scale()` — GPU composited
- Click event handler is lightweight — no continuous listeners
- Multiple rapid clicks queue ripples independently
- No memory leaks — ripple elements are garbage collected after animation end
