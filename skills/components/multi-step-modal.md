---
name: multi-step-modal
source: Luxe
source_url: https://www.luxeui.com/ui/multi-step-modal
category: components
tags: modal, wizard, multi-step, form, onboarding, dialog
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# MultiStepModal

> Multi-step animated modal wizard with smooth slide transitions between steps, progress tracking, and accessible focus management.

## When to Use
- Onboarding flows where users complete 3-5 setup steps
- Booking or scheduling wizards for clinic appointment flows
- Multi-step forms that benefit from focused, one-step-at-a-time UI
- Payment or checkout processes with shipping, billing, and confirmation
- Survey or quiz modals that walk users through questions sequentially

## When NOT to Use
- Simple confirmation dialogs that only need yes/no
- Single-field forms that don't warrant a modal
- Long forms with 10+ steps — use a dedicated page instead
- Mobile flows where full-page step views are more natural than modals

## Pairs Well With
- `luxe-input` - use Luxe animated inputs inside each modal step for consistent polish
- `animated-tabs` - tab-like step indicator at the top of the modal
- `shimmer-button` - shimmer CTA for the final "Complete" action step
- `number-ticker` - animated step counter showing progress (Step 2 of 4)

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| open | boolean | false | Controlled open state |
| onOpenChange | (open: boolean) => void | — | Callback when open state changes |
| steps | StepConfig[] | — | Array of step configurations |
| currentStep | number | 0 | Current active step index |
| onStepChange | (step: number) => void | — | Callback when step changes |
| showProgress | boolean | true | Show step progress indicator |
| className | string | — | Additional CSS classes for modal |
| closeOnOutsideClick | boolean | true | Close modal on backdrop click |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/multi-step-modal"
```

## Usage Example
```jsx
import { MultiStepModal } from "@/components/ui/multi-step-modal";
import { useState } from "react";

export function BookingWizard() {
  const [open, setOpen] = useState(false);
  const [step, setStep] = useState(0);

  return (
    <>
      <button
        onClick={() => setOpen(true)}
        className="px-6 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white"
      >
        Book Appointment
      </button>
      <MultiStepModal
        open={open}
        onOpenChange={setOpen}
        currentStep={step}
        onStepChange={setStep}
        className="lyf-glass rounded-[12px] bg-[#0a0a0a]/95 border border-white/10"
        steps={[
          {
            title: "Select Service",
            content: <ServiceSelector />,
          },
          {
            title: "Choose Time",
            content: <TimeSlotPicker />,
          },
          {
            title: "Your Details",
            content: <PatientInfoForm />,
          },
          {
            title: "Confirm",
            content: <BookingSummary />,
          },
        ]}
      />
    </>
  );
}
```

## Lyfework Customization Notes
- Apply `lyf-glass rounded-[12px]` to modal container for brand glass card styling
- Use `bg-[#0a0a0a]/95` backdrop for dark-theme modal consistency
- Step indicator should use brand gradient `from-[#ff642a] to-[#ff0301]` for active state
- All text inside steps should use `font-manrope` with appropriate weights (400/700/800)
- Ideal for GHL booking embeds — modal overlays work within iframe contexts
- Final step CTA should use `rounded-[8px]` with brand gradient background

## Performance Notes
- Only the active step is rendered — inactive steps are unmounted for memory efficiency
- Framer Motion AnimatePresence handles enter/exit with minimal re-renders
- Focus trap ensures keyboard accessibility without extra DOM listeners
- Backdrop uses CSS backdrop-filter — GPU-accelerated blur
- Step transitions are 300ms — fast enough to feel instant, slow enough to be noticed
