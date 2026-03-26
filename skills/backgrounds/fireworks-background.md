---
name: fireworks-background
source: Animate UI
source_url: https://animate-ui.com/docs/components/backgrounds/fireworks-background
category: backgrounds
tags: fireworks, celebration, burst, particles, festive, background
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# FireworksBackground

> Animated fireworks burst celebration background with colorful particle explosions and trailing spark effects.

## When to Use
- Product launch or milestone celebration pages
- New Year or holiday-themed landing pages
- Success/completion screens after booking or purchase
- Event countdown pages that transition to fireworks at zero
- Achievement or reward reveal moments in gamified UX

## When NOT to Use
- Everyday landing pages — fireworks should feel special, not routine
- Professional medical or legal sites where celebration feels out of place
- Content-heavy pages where bursting particles obscure readability
- Mobile-heavy audiences where particle animations drain battery rapidly
- Pages viewed for extended periods — fireworks are a moment, not a state

## Pairs Well With
- `gradient-text` - celebration headline with fireworks exploding behind it
- `number-ticker` - milestone counter ticking up with fireworks as it reaches target
- `blur-text` - reveal text through clearing fireworks smoke
- `shimmer-button` - celebratory shimmer CTA amid fireworks

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#ff642a", "#ff0301", "#fff"] | Firework particle colors |
| frequency | number | 3 | Bursts per second |
| particleCount | number | 30 | Particles per burst |
| spread | number | 180 | Burst spread angle in degrees |
| className | string | — | Container CSS classes |
| autoStart | boolean | true | Start fireworks on mount |
| duration | number | — | Stop after N seconds (undefined = continuous) |
| gravity | number | 0.5 | Particle fall speed |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/fireworks-background"
```

## Usage Example
```jsx
import { FireworksBackground } from "@/components/ui/fireworks-background";

export function LaunchCelebration() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a] overflow-hidden">
      <FireworksBackground
        colors={["#ff642a", "#ff0301", "#ffffff", "#ffa500"]}
        frequency={2}
        particleCount={25}
        duration={10}
        className="absolute inset-0"
      />
      <div className="relative z-10 text-center space-y-6">
        <h1 className="font-manrope font-800 text-7xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          We're Live!
        </h1>
        <p className="font-manrope font-400 text-gray-300 text-xl">
          Lyfework 2.0 has officially launched
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Color palette: `["#ff642a", "#ff0301", "#ffffff", "#ffa500"]` for brand-aligned fireworks
- Use `duration={10}` to auto-stop — never leave fireworks running indefinitely
- Reduce `frequency` to 1-2 for a dignified celebration, not a rave
- Content: `relative z-10` to layer above fireworks
- GHL compatible — canvas-based rendering works in iframe embeds
- On `#0a0a0a` backgrounds, warm firework colors pop beautifully

## Performance Notes
- Canvas-based rendering — all particles drawn in a single paint operation
- Auto-stop via `duration` prop prevents indefinite CPU usage
- Particle cleanup on each frame — no memory accumulation
- Reduce `particleCount` and `frequency` on mobile for 60fps
- RequestAnimationFrame loop with automatic cleanup on unmount
