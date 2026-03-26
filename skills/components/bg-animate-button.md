---
name: bg-animate-button
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/bg-animate-button
category: components
tags: button, animated, gradient, background, motion
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# BgAnimateButton

> Button with animated background gradient that shifts and flows on hover/focus.

## When to Use
- Primary CTA buttons needing eye-catching animation
- Hero section action buttons with visual dynamism
- Pricing page "Get Started" buttons with subtle motion
- Launch or campaign CTAs that need to draw attention
- Dark-themed pages where gradient motion adds life

## When NOT to Use
- Forms with multiple buttons where animation causes distraction
- Accessibility-sensitive contexts where motion is disorienting
- Pages with many animated elements already competing for attention
- Subtle or minimal design systems

## Pairs Well With
- `gradient-text` - Matching gradient animation on text and button
- `aurora` - Aurora background with gradient-animated CTA
- `animated-content` - Button animates in alongside content entrance
- `spotlight-card` - Animated button inside spotlight card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| gradient | string[] | ['#ff642a', '#ff0301'] | Gradient color stops |
| speed | number | 3 | Animation cycle duration in seconds |
| angle | number | 45 | Gradient angle in degrees |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Button size |
| animateOn | 'hover' \| 'always' | 'hover' | When to animate |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Button content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/bg-animate-button"
```

## Usage Example
```jsx
import { BgAnimateButton } from "@/components/ui/bg-animate-button";

export function HeroCTA() {
  return (
    <div className="bg-[#0a0a0a] p-8 flex justify-center">
      <BgAnimateButton
        gradient={["#ff642a", "#ff0301", "#ff642a"]}
        speed={4}
        size="lg"
        animateOn="always"
        className="font-manrope font-700 rounded-[8px] text-white px-10 py-4"
      >
        Start Free Trial
      </BgAnimateButton>
    </div>
  );
}
```

## Lyfework Customization Notes
- Use brand gradient ["#ff642a", "#ff0301", "#ff642a"] for seamless loop
- Manrope 700, rounded-[8px], white text on animated gradient
- Set animateOn="always" for hero CTAs, "hover" for secondary buttons
- 4-5s speed creates subtle, non-distracting motion
- GHL compatible -- pure CSS animation with no JS dependency

## Performance Notes
- CSS background-position animation is GPU-accelerated
- Zero JavaScript runtime cost -- animation is pure CSS keyframes
- background-size: 200% creates the sliding effect without repaints
- No layout shifts during animation
- Battery-friendly on mobile with CSS animation
