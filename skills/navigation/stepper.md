---
name: stepper
source: ReactBits
source_url: https://reactbits.dev/components/stepper
category: navigation
tags: stepper, steps, progress, wizard, multi-step, process
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Stepper

> An animated step indicator showing progress through a multi-step process. Steps light up with animated transitions as the user advances. Horizontal or vertical layout.

## When to Use

- "How it works" process sections on landing pages
- Multi-step forms or onboarding flows
- Project timelines or roadmaps
- Implementation process breakdowns (perfect for ClinicOS)
- Any content that follows a sequential 3-6 step process

## When NOT to Use

- Non-sequential content (steps imply order)
- More than 7 steps (stepper gets too wide/long)
- Content where steps aren't meaningfully different stages

## Pairs Well With

- `animated-content` - Reveal the stepper on scroll
- `blur-text` - Section headline above the stepper
- `spotlight-card` - Each step expands into a spotlight card with details
- `count-up` - Step numbers count up as they activate

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| steps | StepItem[] | [] | Array of step objects |
| activeStep | number | 0 | Currently active step |
| orientation | "horizontal" \| "vertical" | "horizontal" | Layout direction |
| accentColor | string | "#ff642a" | Active step color |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Stepper-TS-TW
```

## Usage Example

```jsx
import Stepper from '@/components/ui/Stepper';

function HowItWorks() {
  const steps = [
    { title: 'Discovery', description: 'We audit your current systems and map your workflows.' },
    { title: 'Build', description: 'Full system install in 30 days. CRM, automations, AI modules.' },
    { title: 'Launch', description: 'Go live with training and support. Everything tested.' },
    { title: 'Optimize', description: 'Ongoing refinement based on real performance data.' },
  ];

  return (
    <section className="py-24 px-8 max-w-4xl mx-auto">
      <h2 className="text-3xl font-extrabold text-white text-center mb-16">How It Works</h2>
      <Stepper steps={steps} activeStep={-1} orientation="horizontal" accentColor="#ff642a" />
    </section>
  );
}
```

## Lyfework Customization Notes

- Accent color: `#ff642a` for Lyfework brand
- `orientation="horizontal"` for desktop. Switch to `"vertical"` on mobile.
- Active step connector line should animate with the Lyfework gradient
- Step numbers: Manrope 800 in circles. Titles: Manrope 700. Descriptions: 400.
- Perfect for ClinicOS "How It Works" sections
- For scroll-triggered activation: each step lights up as user scrolls past it
- Works in GHL with React embeds

## Performance Notes

- framer-motion layout animations for step transitions
- Lightweight, only animates active step change
- No performance concerns
