---
name: animated-modal
source: Aceternity UI
source_url: https://ui.aceternity.com/components/animated-modal
category: components
tags: modal, dialog, popup, overlay, spring, animation, framer-motion
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# AnimatedModal

> Spring-animated modal/dialog with smooth open/close transitions, backdrop blur, and customizable content areas.

## When to Use
- Booking or appointment scheduling forms on clinic sites
- Product detail quick-view modals on SaaS landing pages
- Video or demo preview overlays on portfolio pages
- Confirmation dialogs for form submissions
- Feature detail expansion from card grids

## When NOT to Use
- For inline content that should remain visible in the flow
- When the modal content is too long (use a dedicated page instead)
- On pages where multiple overlapping modals are needed simultaneously

## Pairs Well With
- `animated-content` - Stagger content appearance inside the modal
- `spotlight-card` - Use as the trigger card that opens the modal
- `blur-text` - Animate modal headline text on open
- `click-spark` - Add spark effect on modal trigger button click

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Modal trigger, body, and footer via compound components |
| className | string | - | Classes for the modal container |

## Installation
```bash
npx aceternity-ui@latest add animated-modal
```

## Usage Example
```jsx
import { Modal, ModalBody, ModalContent, ModalFooter, ModalTrigger } from "@/components/ui/animated-modal";

export function BookingModal() {
  return (
    <Modal>
      <ModalTrigger className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-8 py-3 rounded-[8px]">
        Book a Free Consultation
      </ModalTrigger>
      <ModalBody className="bg-[#0a0a0a] border border-white/10 rounded-[12px]">
        <ModalContent>
          <h2 className="font-[Manrope] font-800 text-3xl text-white mb-4">
            Schedule Your Visit
          </h2>
          <p className="font-[Manrope] font-400 text-neutral-400 mb-6">
            Pick a time that works for you. Our AI assistant will prepare your consultation.
          </p>
          <form className="space-y-4">
            <input
              type="text"
              placeholder="Full Name"
              className="w-full bg-white/5 border border-white/10 rounded-[8px] px-4 py-3 text-white font-[Manrope] font-400"
            />
            <input
              type="email"
              placeholder="Email Address"
              className="w-full bg-white/5 border border-white/10 rounded-[8px] px-4 py-3 text-white font-[Manrope] font-400"
            />
          </form>
        </ModalContent>
        <ModalFooter>
          <button className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-8 py-3 rounded-[8px] w-full">
            Confirm Booking
          </button>
        </ModalFooter>
      </ModalBody>
    </Modal>
  );
}
```

## Lyfework Customization Notes
- Set modal background to `bg-[#0a0a0a]` with `border border-white/10` for dark theme consistency
- Use `rounded-[12px]` on ModalBody, `rounded-[8px]` on inputs and buttons
- Apply Manrope 800 for modal titles, 700 for buttons, 400 for body text
- Gradient CTA buttons use `from-[#ff642a] to-[#ff0301]`
- For GHL compatibility, ensure modal uses `portal` rendering to escape iframe stacking contexts

## Performance Notes
- Spring animation uses framer-motion's optimized spring physics, not CSS transitions
- Backdrop blur is GPU-composited but may lag on older mobile GPUs; test on target devices
- Modal content is unmounted when closed by default, saving DOM memory
- Focus trap is built-in for accessibility compliance
- Preload form components if modal contains complex forms to avoid jank on open
