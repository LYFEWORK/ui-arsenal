---
name: draggable-card
source: Aceternity UI
source_url: https://ui.aceternity.com/components/draggable-card
category: components
tags: drag, card, physics, interactive, gesture, framer-motion, playful
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# DraggableCard

> Drag-to-move interactive card with spring physics, inertia, and boundary constraints for playful UI interactions.

## When to Use
- Interactive onboarding or tutorial card sequences
- Playful portfolio showcases with scattered card layouts
- Drag-to-dismiss notification or tip cards
- Interactive mood boards or visual brainstorming layouts
- Gamified UI elements like drag-to-rank features

## When NOT to Use
- For standard card grids where drag adds no value
- On critical conversion pages where drag may confuse users
- When cards contain forms or inputs that conflict with drag gestures

## Pairs Well With
- `tilted-card` - Combine tilt with drag for enhanced physicality
- `click-spark` - Spark effect when card is dropped
- `animated-content` - Entrance animation before drag becomes active
- `spotlight-card` - Spotlight glow follows the dragged card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Card content |
| className | string | - | Additional classes for the card |
| dragConstraints | object | - | Bounds for drag movement { top, left, right, bottom } |
| dragElastic | number | 0.1 | Elasticity when dragging past constraints |

## Installation
```bash
npx aceternity-ui@latest add draggable-card
```

## Usage Example
```jsx
import { DraggableCard } from "@/components/ui/draggable-card";

export function InteractiveShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24 relative min-h-[600px]">
      <h2 className="font-[Manrope] font-800 text-4xl text-white text-center mb-16">
        Drag to <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Explore</span>
      </h2>
      <div className="relative max-w-4xl mx-auto h-[400px]">
        <DraggableCard className="absolute top-10 left-10 lyf-glass rounded-[12px] p-6 w-64 cursor-grab active:cursor-grabbing">
          <h3 className="font-[Manrope] font-700 text-white">Web Design</h3>
          <p className="font-[Manrope] font-400 text-neutral-400 text-sm mt-2">Custom sites for clinics</p>
        </DraggableCard>
        <DraggableCard className="absolute top-20 right-20 lyf-glass rounded-[12px] p-6 w-64 cursor-grab active:cursor-grabbing">
          <h3 className="font-[Manrope] font-700 text-white">AI Integration</h3>
          <p className="font-[Manrope] font-400 text-neutral-400 text-sm mt-2">Smart automation tools</p>
        </DraggableCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `lyf-glass` with `rounded-[12px]` for consistent card styling
- Use `cursor-grab` and `active:cursor-grabbing` for clear interaction affordance
- Manrope 700 for card titles, 400 for descriptions on #0a0a0a backgrounds
- Set drag constraints to prevent cards from leaving the viewport in GHL embeds
- Add subtle `shadow-lg shadow-[#ff642a]/10` for brand-colored depth

## Performance Notes
- Framer Motion drag uses `onPan` events with requestAnimationFrame, 60fps on modern devices
- Spring physics calculations are lightweight, single card overhead is negligible
- Avoid more than 8 simultaneous draggable cards to prevent gesture conflicts
- Touch events are natively supported; works on mobile with drag gestures
- Card position resets on unmount unless state is persisted externally
