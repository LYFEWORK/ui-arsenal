---
name: animated-list
source: ReactBits
source_url: https://reactbits.dev/components/animated-list
category: components
tags: list, animated, stagger, feed, notifications, activity, framer-motion
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# AnimatedList

> A list component where items animate in sequentially with staggered entrance. New items slide in from the top or bottom with smooth spring animations. Ideal for live feeds, notification lists, or feature breakdowns.

## When to Use

- Feature lists on landing pages (benefits, capabilities, included items)
- Activity feeds or notification displays in web apps
- Testimonial streams that add new items dynamically
- Process steps or timeline sequences
- Any list of items where sequential reveal adds storytelling value

## When NOT to Use

- Static lists that don't need animation (simple FAQ lists, nav menus)
- Tables or data-heavy displays
- Lists with 20+ items visible at once (animation becomes meaningless)
- Anywhere the animation would delay access to critical information

## Pairs Well With

- `spotlight-card` - Each list item rendered as a spotlight card
- `animated-content` - Wrap the entire AnimatedList in AnimatedContent for scroll-triggered start
- `blur-text` - Animate the section headline, then trigger the list animation
- `count-up` - CountUp numbers as part of each list item

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | ReactNode[] | [] | Array of items to render |
| delay | number | 1000 | Delay between each item in ms |
| direction | "up" \| "down" | "up" | Direction items enter from |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/AnimatedList-TS-TW
```

## Usage Example

```jsx
import AnimatedList from '@/components/ui/AnimatedList';

function WhatYouGet() {
  const features = [
    <div className="flex items-center gap-4 p-4 lyf-glass rounded-xl">
      <span className="text-2xl">🔧</span>
      <div>
        <h4 className="font-bold text-white">Full System Build</h4>
        <p className="text-sm text-gray-400">CRM, automations, and workflows. Done in 30 days.</p>
      </div>
    </div>,
    <div className="flex items-center gap-4 p-4 lyf-glass rounded-xl">
      <span className="text-2xl">🤖</span>
      <div>
        <h4 className="font-bold text-white">5 AI Modules</h4>
        <p className="text-sm text-gray-400">Intake, routing, follow-up, reviews, reactivation.</p>
      </div>
    </div>,
    <div className="flex items-center gap-4 p-4 lyf-glass rounded-xl">
      <span className="text-2xl">📊</span>
      <div>
        <h4 className="font-bold text-white">Live Dashboard</h4>
        <p className="text-sm text-gray-400">Every metric you need. Nothing you don't.</p>
      </div>
    </div>,
  ];

  return (
    <section className="py-24 px-8 max-w-2xl mx-auto">
      <h2 className="text-3xl font-extrabold text-white text-center mb-12">
        What's Included
      </h2>
      <AnimatedList
        items={features}
        delay={800}
        direction="up"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Delay of 600-1000ms between items feels deliberate and premium
- Each list item should use `lyf-glass` styling for consistent Lyfework look
- For feature lists, use icon + title + description layout inside each item
- For GHL pages: the AnimatedList renders all items in the DOM, animation is visual only. No SEO concerns.
- On mobile, reduce delay to 500ms to keep pace moving
- Always pair with a strong section headline above the list

## Performance Notes

- framer-motion AnimatePresence handles item transitions
- Items are pre-rendered in DOM, animation is transform/opacity only
- No layout shifts since items have reserved space
- Light memory footprint, suitable for lists up to 15-20 items
- SSR: items render statically, animate on client hydration
