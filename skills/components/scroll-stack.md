---
name: scroll-stack
source: ReactBits
source_url: https://reactbits.dev/components/scroll-stack
category: components
tags: scroll, stack, cards, sticky, parallax, section
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ScrollStack

> Cards or sections that stack on top of each other as the user scrolls. Each card sticks to the viewport and gets pushed underneath by the next card, creating a layered, depth-rich scrolling experience. Perfect for storytelling and step-by-step reveals.

## When to Use

- "How it works" step-by-step sections on SaaS landing pages
- Case study walk-throughs where each card reveals a phase
- Feature deep-dives that unfold as the user scrolls
- Storytelling pages (about us, company journey, timeline)
- Any long-form content that benefits from progressive disclosure

## When NOT to Use

- Short pages where sticky stacking has no room to breathe
- Mobile-first designs where sticky positioning behaves unpredictably
- Content that users need to jump between (stacking enforces linear reading)
- Performance-constrained environments with many heavy card contents

## Pairs Well With

- `animated-content` - Animate content within each stacking card on reveal
- `gradient-text` - Gradient headings on each stacking card
- `count-up` - Animated stats that trigger as each card becomes active
- `spotlight-card` - Spotlight effect on the currently active/top card

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Stack card components |
| offset | number | 20 | Vertical offset between stacked cards in px |
| scaleReduction | number | 0.05 | Scale reduction per card layer (0-0.2) |
| stickyTop | number | 80 | Top position for sticky cards in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ScrollStack-TS-TW
```

## Usage Example

```jsx
import ScrollStack from '@/components/ui/ScrollStack';

function HowItWorksSection() {
  const steps = [
    {
      step: '01',
      title: 'Discovery Call',
      desc: 'We learn your goals, audit your current systems, and map out a 90-day plan.',
      color: 'from-[#ff642a]/10 to-transparent',
    },
    {
      step: '02',
      title: 'Build & Configure',
      desc: 'We build your CRM, automations, funnels, and AI chatbot. Everything integrated.',
      color: 'from-[#ff0301]/10 to-transparent',
    },
    {
      step: '03',
      title: 'Launch & Optimize',
      desc: 'Go live in 30 days. We monitor, A/B test, and continuously optimize performance.',
      color: 'from-[#ff642a]/10 to-transparent',
    },
    {
      step: '04',
      title: 'Scale & Grow',
      desc: 'As your practice grows, we add new automations, channels, and capabilities.',
      color: 'from-[#ff0301]/10 to-transparent',
    },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-20">
        How It Works
      </h2>
      <ScrollStack offset={24} scaleReduction={0.04} stickyTop={100} className="max-w-3xl mx-auto">
        {steps.map((s, i) => (
          <div key={i} className={`lyf-glass rounded-2xl p-10 bg-gradient-to-br ${s.color}`}>
            <span className="text-6xl font-extrabold text-[#ff642a]/20 font-[Manrope]">{s.step}</span>
            <h3 className="mt-4 text-2xl font-bold text-white font-[Manrope]">{s.title}</h3>
            <p className="mt-3 text-gray-400 text-lg leading-relaxed">{s.desc}</p>
          </div>
        ))}
      </ScrollStack>
    </section>
  );
}
```

## Lyfework Customization Notes

- Card backgrounds: `lyf-glass` with subtle gradient overlays using brand colors
- Step numbers: `text-[#ff642a]/20` large watermark-style numbers for visual interest
- Font: `Manrope` 800 for step titles, 400 for descriptions
- `stickyTop: 100` leaves room for the Lyfework fixed header navigation
- Border radius: `rounded-2xl` (16px) for panel-level stacking cards
- GHL: requires React + Framer Motion embed; the scroll-tracking JS is essential

## Performance Notes

- Uses CSS `position: sticky` for the stacking behavior; minimal JS for scale/opacity
- Framer Motion `useScroll` and `useTransform` handle scroll-linked animations
- Each card's `scale` and `opacity` are computed from scroll position, GPU-composited
- Keep card count to 4-6 for a clean stacking experience; more becomes tedious
- On mobile, consider disabling scale reduction and using simple sequential layout instead
