---
name: stateful-button
source: Aceternity UI
source_url: https://ui.aceternity.com/components/stateful-button
category: components
tags: button, loading, success, error, state, animation, feedback
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# StatefulButton

> Button with animated loading, success, and error state transitions, providing clear visual feedback for async actions.

## When to Use
- Form submission buttons on contact or booking pages
- CTA buttons that trigger API calls or database operations
- Newsletter signup buttons with success/error feedback
- Payment or checkout buttons with processing states
- Any async action that needs user-facing progress indication

## When NOT to Use
- For simple navigation links that do not trigger actions
- When state feedback is handled by a separate toast/notification system
- For buttons with instant, synchronous actions

## Pairs Well With
- `click-spark` - Add spark effect on initial click before loading state
- `animated-content` - Fade in the button with section content
- `gradient-text` - Gradient text inside the button label
- `animated-modal` - Stateful button inside modal forms

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| state | string | "idle" | Current state: "idle", "loading", "success", "error" |
| onClick | function | - | Click handler function |
| children | ReactNode | - | Button label content |
| className | string | - | Additional classes for the button |
| loadingText | string | "Processing..." | Text shown during loading state |
| successText | string | "Done!" | Text shown on success |
| errorText | string | "Try again" | Text shown on error |

## Installation
```bash
npx aceternity-ui@latest add stateful-button
```

## Usage Example
```jsx
import { StatefulButton } from "@/components/ui/stateful-button";
import { useState } from "react";

export function BookingButton() {
  const [state, setState] = useState("idle");

  const handleBooking = async () => {
    setState("loading");
    try {
      const res = await fetch("/api/book-appointment", { method: "POST" });
      if (!res.ok) throw new Error();
      setState("success");
    } catch {
      setState("error");
    }
    setTimeout(() => setState("idle"), 3000);
  };

  return (
    <StatefulButton
      state={state}
      onClick={handleBooking}
      className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px] text-lg"
      loadingText="Booking..."
      successText="Appointment Confirmed!"
      errorText="Something went wrong"
    >
      Book Free Consultation
    </StatefulButton>
  );
}
```

## Lyfework Customization Notes
- Default button uses `from-[#ff642a] to-[#ff0301]` gradient with `rounded-[8px]`
- Manrope 700 for button text, consistent with Lyfework button typography
- Loading spinner color should match white text for contrast on gradient background
- Success state can flash green briefly before returning to idle
- Fully compatible with GHL form submission workflows

## Performance Notes
- State transitions use framer-motion `AnimatePresence` for smooth swaps
- Spinner animation is CSS-only, no JS frame loop
- Button disables during loading to prevent double-submission
- Text swap animation is a simple opacity/y transition, GPU-composited
- No external dependencies beyond framer-motion
