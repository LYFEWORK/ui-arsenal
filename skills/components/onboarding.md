---
name: onboarding
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/onboarding
category: components
tags: onboarding, wizard, steps, flow, multi-step, tutorial
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# Onboarding

> Multi-step onboarding flow with animated transitions, progress tracking, and step validation.

## When to Use
- SaaS product first-run experience and setup wizards
- Clinic patient intake forms with multiple steps
- Account creation flows with progressive disclosure
- Feature tours introducing new functionality
- GHL funnel multi-step lead capture forms

## When NOT to Use
- Simple single-page forms that don't need steps
- Information-only pages without user input
- Checkout flows (use dedicated checkout components)

## Pairs Well With
- `animated-content` - Step content entrance animations for polish
- `shimmer-button` - Shimmer CTA for "Complete Setup" final step
- `number-ticker` - Progress percentage animation between steps
- `direction-aware-tabs` - Tab-style step navigation alternative

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| steps | { title: string; description?: string; content: ReactNode }[] | [] | Step definitions |
| currentStep | number | 0 | Active step index |
| onStepChange | (step: number) => void | - | Step change callback |
| onComplete | () => void | - | Completion callback |
| showProgress | boolean | true | Show progress indicator |
| allowSkip | boolean | false | Allow skipping steps |
| animation | 'slide' \| 'fade' \| 'scale' | 'slide' | Transition animation type |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/onboarding"
```

## Usage Example
```jsx
import { Onboarding } from "@/components/ui/onboarding";

export function PatientIntake() {
  const steps = [
    {
      title: "Personal Information",
      description: "Tell us about yourself",
      content: (
        <div className="space-y-4">
          <input className="w-full p-3 bg-white/5 border border-white/10 rounded-[8px] font-manrope text-white" placeholder="Full Name" />
          <input className="w-full p-3 bg-white/5 border border-white/10 rounded-[8px] font-manrope text-white" placeholder="Email" type="email" />
        </div>
      ),
    },
    {
      title: "Health History",
      description: "Help us understand your needs",
      content: <div>{/* Health form fields */}</div>,
    },
    {
      title: "Preferences",
      description: "Customize your experience",
      content: <div>{/* Preference selections */}</div>,
    },
  ];

  return (
    <div className="min-h-screen bg-[#0a0a0a] flex items-center justify-center p-6">
      <div className="lyf-glass rounded-[12px] p-8 max-w-xl w-full">
        <Onboarding
          steps={steps}
          animation="slide"
          showProgress={true}
          onComplete={() => console.log("Intake complete")}
        />
      </div>
    </div>
  );
}
```

## Lyfework Customization Notes
- Wrap in `lyf-glass` container with 12px radius on #0a0a0a background
- Use Manrope 700 for step titles, 400 for descriptions
- Brand gradient for progress bar: from-[#ff642a] to-[#ff0301]
- Input fields: bg-white/5, border-white/10, rounded-[8px]
- GHL compatible for multi-step funnel lead capture forms

## Performance Notes
- Framer Motion AnimatePresence handles step transitions efficiently
- Only active step content is rendered (lazy step mounting)
- Progress indicator is pure CSS with gradient fill
- Step validation runs only on step change, not on every keystroke
- Bundle addition is minimal when Framer Motion is already in the project
