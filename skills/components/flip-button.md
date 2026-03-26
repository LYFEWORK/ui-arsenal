---
name: flip-button
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/flip-button
category: components
tags: button, flip, confirm, 3d, rotation, action
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# FlipButton

> Button that performs a 3D flip animation to reveal a confirmation state or secondary action on the reverse side.

## When to Use
- Delete or destructive actions that need a "Are you sure?" confirmation step
- Add-to-cart buttons that flip to show "Added!" confirmation
- Follow/subscribe buttons flipping between follow and following states
- Booking confirmation buttons that flip to reveal success state
- Any two-state action where the flip creates a satisfying micro-interaction

## When NOT to Use
- Simple navigation buttons without state changes
- Forms with standard submit behavior
- Actions requiring more than two states — use a multi-step flow
- Mobile contexts where 3D transforms can cause rendering artifacts

## Pairs Well With
- `luxe-card` - flip button as the action inside an interactive card
- `notification-list` - flip-to-confirm actions on notification items
- `animated-content` - stagger-animate multiple flip buttons in a grid
- `spotlight-card` - flip button CTA at the bottom of a spotlight card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| frontContent | ReactNode | — | Content shown on the front face |
| backContent | ReactNode | — | Content shown on the back face |
| onFlip | () => void | — | Callback when flip is triggered |
| onConfirm | () => void | — | Callback when back face action is clicked |
| className | string | — | Additional CSS classes |
| flipDuration | number | 0.5 | Flip animation duration in seconds |
| autoReset | number | — | Auto-reset to front after N milliseconds |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/flip-button"
```

## Usage Example
```jsx
import { FlipButton } from "@/components/ui/flip-button";

export function AppointmentAction() {
  return (
    <FlipButton
      className="rounded-[8px] font-manrope font-700"
      flipDuration={0.4}
      autoReset={3000}
      frontContent={
        <span className="px-6 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white block rounded-[8px]">
          Cancel Appointment
        </span>
      }
      backContent={
        <span className="px-6 py-3 bg-red-600 text-white block rounded-[8px]">
          Confirm Cancel?
        </span>
      }
      onConfirm={() => console.log("Appointment cancelled")}
    />
  );
}
```

## Lyfework Customization Notes
- Front face: `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` for primary actions
- Back face: contextual color (red for destructive, green for success confirmations)
- Use `font-manrope font-700` on both faces for brand consistency
- Apply `rounded-[8px]` to match Lyfework button radius standard
- GHL compatible — 3D transform is CSS-only, works in iframe contexts
- Use `autoReset={3000}` to return to front face if user doesn't confirm

## Performance Notes
- 3D flip uses CSS perspective and rotateY — GPU-accelerated transform
- Only two elements in DOM (front + back) — minimal footprint
- Backface-visibility hidden prevents rendering both sides simultaneously
- Framer-motion handles the flip interpolation with spring physics
- Auto-reset timer cleans up on unmount — no memory leaks
