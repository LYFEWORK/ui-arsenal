---
name: cosmic-button
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/cosmic-button
category: components
tags: button, cosmic, particles, space, premium, animated
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# CosmicButton

> Button with cosmic space particle animation, starfield effects, and nebula glow.

## When to Use
- Premium product launch CTAs with maximum visual impact
- Creative portfolio hero sections with dramatic action buttons
- Gaming or entertainment site call-to-actions
- Dark-themed pages where cosmic effects shine brightest
- Special campaign or event page featured buttons

## When NOT to Use
- Professional or corporate interfaces where cosmic feels off-brand
- Healthcare or clinic sites where grounded aesthetics are preferred
- Pages with many buttons (reserve cosmic for single primary CTA)
- Performance-critical mobile pages

## Pairs Well With
- `particles` - Cosmic button with surrounding particle field
- `aurora` - Nebula-like aurora background with cosmic CTA
- `gradient-text` - Cosmic heading text paired with cosmic button
- `blur-text` - Dramatic text reveal leading to cosmic CTA

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| particleCount | number | 30 | Number of cosmic particles |
| colors | string[] | ['#ff642a', '#ff0301', '#ffffff'] | Particle and glow colors |
| glowIntensity | number | 0.6 | Outer glow strength |
| speed | number | 1 | Particle animation speed |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Button size |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Button content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/cosmic-button"
```

## Usage Example
```jsx
import { CosmicButton } from "@/components/ui/cosmic-button";

export function LaunchHero() {
  return (
    <div className="bg-[#0a0a0a] min-h-screen flex items-center justify-center">
      <div className="text-center">
        <h1 className="font-manrope font-800 text-6xl text-white mb-8">
          Something Extraordinary
        </h1>
        <CosmicButton
          particleCount={25}
          colors={["#ff642a", "#ff0301", "#ffffff"]}
          glowIntensity={0.5}
          size="lg"
          className="font-manrope font-700 rounded-[8px] px-12 py-4"
        >
          Launch Now
        </CosmicButton>
      </div>
    </div>
  );
}
```

## Lyfework Customization Notes
- Use brand colors ["#ff642a", "#ff0301"] with white star particles
- Reduce glowIntensity to 0.3-0.5 for sophisticated (not overwhelming) effect
- Manrope 800 heading + 700 button text with cosmic accent
- Reserve for single hero CTA -- don't use multiple cosmic buttons
- Not recommended for GHL funnel pages due to canvas requirements

## Performance Notes
- Canvas-based particle system runs in separate animation loop
- particleCount directly impacts render cost -- keep under 40
- Uses requestAnimationFrame with visibility check
- Glow effect uses CSS box-shadow (GPU-accelerated)
- Falls back to gradient button on devices without canvas support
