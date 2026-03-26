---
name: card-nav
source: ReactBits
source_url: https://reactbits.dev/components/card-nav
category: components
tags: card, navigation, transition, animated, menu, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# CardNav

> Card-based navigation with animated transitions between items. Each nav item is a card that expands, highlights, or transforms on selection, creating an interactive menu experience. Ideal for service pages and feature explorers.

## When to Use

- Service pages where each offering needs a card-based selector
- Feature explorer sections where clicking a card reveals detail
- Multi-step wizards or onboarding flows with card-style steps
- Portfolio category navigation with visual card switching
- SaaS product tour sections with interactive card tabs

## When NOT to Use

- Simple top-bar or sidebar navigation (overkill for basic nav)
- Mobile-first designs where cards consume too much vertical space
- Pages with more than 6-8 nav items (cards don't scale well)
- Quick-access menus where speed matters more than visuals

## Pairs Well With

- `animated-content` - Reveal the card nav section on scroll
- `spotlight-card` - Add spotlight hover effect to each nav card
- `blur-text` - Blur-reveal the detail text when a card is selected
- `aurora` - Aurora background behind the card navigation section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | NavItem[] | required | Array of navigation items with label, content, icon |
| activeIndex | number | 0 | Currently active card index |
| onChange | (index: number) => void | required | Callback when a card is selected |
| orientation | "horizontal" \| "vertical" | "horizontal" | Layout direction |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CardNav-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import CardNav from '@/components/ui/CardNav';

function ServicesSection() {
  const [active, setActive] = useState(0);

  const services = [
    {
      label: 'CRM Setup',
      icon: '🔧',
      content: 'Full GoHighLevel CRM configuration with custom pipelines, automations, and integrations tailored to your business workflow.',
    },
    {
      label: 'AI Automation',
      icon: '🤖',
      content: 'Intelligent chatbots, lead scoring, and automated follow-up sequences that convert while you sleep.',
    },
    {
      label: 'Website Build',
      icon: '🌐',
      content: 'High-converting landing pages and full websites built with modern frameworks, deployed on edge infrastructure.',
    },
    {
      label: 'Analytics',
      icon: '📊',
      content: 'Real-time dashboards tracking every metric that matters. Attribution, ROI, pipeline velocity -- all in one view.',
    },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <h2 className="text-4xl font-extrabold text-white text-center font-[Manrope] mb-12">
        What We Build
      </h2>
      <CardNav
        items={services}
        activeIndex={active}
        onChange={setActive}
        orientation="horizontal"
        className="max-w-5xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Active card border: `border-[#ff642a]` with the Lyfework orange accent
- Inactive cards: `lyf-glass` background with `border-white/5` subtle border
- Card radius: `12px` standard, font: `Manrope` at 700 weight for card labels
- Transition: use Framer Motion `layoutId` for smooth shared-layout animation between states
- GHL embed: bundle as a single React component in a code embed widget
- For client builds, swap icons to Lucide or custom SVGs matching their brand

## Performance Notes

- Framer Motion `layout` animations use FLIP technique for 60fps transitions
- Only the active card renders its full content; others show summary only
- Intersection Observer delays mount until section is visible
- Keep items under 6 for optimal mobile experience
- Preload content for adjacent cards to eliminate transition delay
