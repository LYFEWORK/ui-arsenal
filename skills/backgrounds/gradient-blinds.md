---
name: gradient-blinds
source: ReactBits
source_url: https://reactbits.dev/backgrounds/gradient-blinds
category: backgrounds
tags: background, gradient, blinds, strips, reveal, transition
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GradientBlinds

> Venetian blind strips with gradient animation that open and close to reveal content beneath. Creates a unique reveal/transition effect for section entrances and page loads.

## When to Use

- Page load animations where content is "revealed" through opening blinds
- Section transitions on scroll for a cinematic reveal effect
- Behind hero content for a dramatic entrance animation
- Portfolio project reveal sections where each blind reveals a preview
- Pricing or feature section entrances for visual impact

## When NOT to Use

- Backgrounds that need to remain static and persistent
- Fast-loading pages where the reveal animation adds unnecessary delay
- Mobile-heavy pages where the horizontal strips may feel cramped
- Sections that users will revisit frequently (the reveal gets old fast)

## Pairs Well With

- `split-text` - Text splitting in sync with the blinds opening is a powerful combo
- `animated-content` - Content fading in after the blinds reveal creates a two-stage entrance
- `blur-text` - Blur text reveal timed after the blinds open for a layered effect
- `spotlight-card` - Cards appearing as blinds open section by section

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| slats | number | 10 | Number of blind strips |
| colors | string[] | ["#1a1a1a","#2a2a2a"] | Gradient colors for the blind strips |
| direction | string | "horizontal" | Blind orientation: "horizontal" or "vertical" |
| duration | number | 1.5 | Animation duration in seconds |
| stagger | number | 0.1 | Delay between each slat opening |
| trigger | string | "onView" | When to trigger: "onView", "onLoad", "manual" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GradientBlinds-TS-TW
```

## Usage Example

```jsx
import GradientBlinds from '@/components/ui/GradientBlinds';
import BlurText from '@/components/ui/BlurText';

function SaaSHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <GradientBlinds
        slats={12}
        colors={['#0a0a0a', '#1a0a2e', '#ff642a']}
        direction="horizontal"
        duration={1.8}
        stagger={0.08}
        trigger="onLoad"
      />

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Automate. Scale. Dominate."
          delay={1800}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-2xl mx-auto font-[Manrope]">
          Business infrastructure that runs itself.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework blinds palette: `['#0a0a0a', '#1a0a2e', '#ff642a']` for a dark-to-brand reveal
- Time the BlurText `delay` to match the total blinds animation (`duration` + `slats * stagger`)
- `stagger` of 0.06-0.1 per slat feels cinematic. Below 0.04 and the blinds open too uniformly.
- For client builds, use their brand accent as the final color in the gradient
- GHL: the blinds effect can be approximated with CSS clip-path animations on stacked divs
- Use `trigger="onView"` for scroll-based reveals, `trigger="onLoad"` only for hero sections

## Performance Notes

- CSS transform animations on individual slat elements
- The stagger creates sequential repaints, keep slat count under 15 for smooth animation
- No canvas or WebGL dependency
- After the reveal animation completes, the component can be removed from DOM
- SSR-compatible, renders in closed state and animates on client
