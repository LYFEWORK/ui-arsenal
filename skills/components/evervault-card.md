---
name: evervault-card
source: Aceternity UI
source_url: https://ui.aceternity.com/components/evervault-card
category: components
tags: card, matrix, encrypted, hover, reveal, text, interactive
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# EvervaultCard

> Card with encrypted matrix text effect that reveals readable content on hover, inspired by Evervault's design.

## When to Use
- Security or encryption product feature cards
- AI/tech product showcases emphasizing data processing
- Creative agency portfolio cards with reveal-on-hover mystery
- SaaS feature cards where the "magic" of data transformation is the story
- Interactive landing page sections for developer-facing products

## When NOT to Use
- When card content must be immediately readable for accessibility
- On non-tech audiences who may not understand the matrix metaphor
- For mobile-primary pages where hover is not available

## Pairs Well With
- `spotlight-card` - Layer spotlight glow under the matrix card
- `particles` - Add particle effects to enhance the tech aesthetic
- `gradient-text` - Reveal gradient-colored text on hover
- `aurora` - Use aurora background behind a grid of evervault cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | - | Text to reveal on hover |
| className | string | - | Additional classes for the card |

## Installation
```bash
npx aceternity-ui@latest add evervault-card
```

## Usage Example
```jsx
import { EvervaultCard, Icon } from "@/components/ui/evervault-card";

export function SecurityFeature() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-sm mx-auto">
        <div className="lyf-glass rounded-[12px] border border-white/10 p-8 relative">
          <Icon className="absolute h-6 w-6 -top-3 -left-3 text-[#ff642a]" />
          <Icon className="absolute h-6 w-6 -bottom-3 -left-3 text-[#ff642a]" />
          <Icon className="absolute h-6 w-6 -top-3 -right-3 text-[#ff0301]" />
          <Icon className="absolute h-6 w-6 -bottom-3 -right-3 text-[#ff0301]" />
          <EvervaultCard text="HIPAA Compliant" />
          <h3 className="font-[Manrope] font-700 text-white text-xl mt-4">End-to-End Encryption</h3>
          <p className="font-[Manrope] font-400 text-neutral-400 text-sm mt-2">
            Patient data is encrypted at rest and in transit. Your clinic site meets every compliance standard.
          </p>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `lyf-glass` with `border border-white/10` for the card container
- Corner icons colored with `text-[#ff642a]` and `text-[#ff0301]` to match brand gradient
- Set `rounded-[12px]` on the card, Manrope 700 for titles, 400 for descriptions
- Matrix text color can be customized to the orange gradient spectrum
- Works in GHL embeds but requires mouse events; provide static fallback for mobile

## Performance Notes
- Matrix text animation uses canvas or CSS character randomization, moderate CPU usage
- Limit to 1-2 evervault cards per viewport to avoid excessive text recalculation
- Hover-only activation means zero overhead when not interacting
- Text randomization interval should be capped at 50ms for smooth but efficient animation
- Consider `IntersectionObserver` to pause animation when card is off-screen
