---
name: confetti
source: Magic UI
source_url: https://magicui.design/docs/components/confetti
category: animations
tags: confetti, celebration, burst, particles, event
dependencies: canvas-confetti
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Confetti

> Celebration confetti burst effect triggered by user actions like form submissions or milestone achievements.

## When to Use
- Form submission success celebrations
- Achievement unlocked or milestone reached moments
- Successful payment or subscription confirmation
- Onboarding completion celebrations
- Contest or giveaway winner announcements

## When NOT to Use
- Frequent or repetitive actions (confetti fatigue)
- Error or failure states (confetti implies success)
- Background ambient animations (confetti is event-driven)
- Professional medical contexts where celebration feels inappropriate

## Pairs Well With
- `click-spark` - Spark on click followed by confetti burst
- `pulsating-button` - Pulsing CTA that triggers confetti on success
- `number-ticker` - Count-up animation ending with confetti
- `gradient-text` - "Congratulations!" heading with gradient

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| particleCount | number | 50 | Number of confetti particles |
| spread | number | 360 | Spread angle in degrees |
| startVelocity | number | 30 | Initial launch velocity |
| decay | number | 0.9 | Velocity decay rate |
| colors | string[] | ["#ff642a", "#ff0301", "#fff"] | Particle colors |
| origin | object | {x: 0.5, y: 0.5} | Launch origin point (0-1) |
| gravity | number | 1 | Gravity multiplier |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/confetti"
```

## Usage Example
```jsx
import { Confetti } from "@/components/magicui/confetti";
import { useRef } from "react";

export function BookingSuccess() {
  const confettiRef = useRef(null);

  return (
    <section className="bg-[#0a0a0a] py-24 text-center relative">
      <Confetti
        ref={confettiRef}
        className="absolute inset-0 pointer-events-none z-50"
      />
      <div className="lyf-glass rounded-[12px] p-12 mx-auto max-w-md">
        <h2 className="font-manrope font-800 text-3xl text-white mb-4">
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Booking confirmed!
          </span>
        </h2>
        <p className="font-manrope font-400 text-white/60 mb-8">
          Your appointment has been scheduled. Check your email for details.
        </p>
        <button
          onClick={() => confettiRef.current?.fire({ particleCount: 100, spread: 70, colors: ["#ff642a", "#ff0301", "#ffffff"] })}
          className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-manrope font-700 px-8 py-3 rounded-[8px]"
        >
          Celebrate!
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set confetti `colors` to `["#ff642a", "#ff0301", "#ffffff"]` for brand palette
- Trigger on meaningful actions only — booking confirmations, plan upgrades, milestones
- Use `lyf-glass` card for the success message container
- Manrope font-800 for celebration headings, font-400 for supporting text
- GHL compatible — canvas-confetti renders on a `<canvas>` overlay, no DOM conflicts

## Performance Notes
- Canvas-confetti uses a dedicated `<canvas>` element — separate paint layer
- Particle simulation runs for ~2-3 seconds then stops — no ongoing CPU cost
- Each burst creates and destroys particles — memory is freed after animation
- Multiple rapid bursts stack — limit to one burst per action
- Canvas is positioned with `pointer-events: none` — no interaction blocking
