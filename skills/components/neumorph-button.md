---
name: neumorph-button
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/neumorph-button
category: components
tags: button, neumorphism, soft-ui, shadow, tactile
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# NeumorphButton

> Neumorphic soft-shadow button with pressed/unpressed states and tactile depth.

## When to Use
- Soft UI design systems with neumorphic visual language
- Dashboard action buttons with tactile press feedback
- Settings or toggle-style buttons needing depth cues
- Creative portfolios with unique button aesthetics
- Dark-themed interfaces where shadows create dimension

## When NOT to Use
- Standard marketing CTAs where gradient buttons convert better
- High-contrast accessibility-critical interfaces
- Light backgrounds where neumorphic shadows are most effective (unless adapted)
- GHL embed pages where subtle shadows may not render consistently

## Pairs Well With
- `neumorph-eyebrow` - Matching neumorphic eyebrow labels with neumorphic buttons
- `animated-content` - Buttons animating in with neumorphic depth
- `spotlight-card` - Neumorphic buttons inside spotlight-lit cards
- `dock` - Neumorphic action buttons within a floating dock

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| variant | 'raised' \| 'pressed' \| 'flat' | 'raised' | Neumorphic depth state |
| size | 'sm' \| 'md' \| 'lg' | 'md' | Button size |
| color | string | '#1a1a1a' | Base surface color for shadow calculation |
| intensity | number | 0.3 | Shadow intensity |
| onClick | () => void | - | Click handler |
| disabled | boolean | false | Disabled state |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Button content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/neumorph-button"
```

## Usage Example
```jsx
import { NeumorphButton } from "@/components/ui/neumorph-button";

export function DashboardActions() {
  return (
    <div className="bg-[#0a0a0a] p-8 flex gap-4">
      <NeumorphButton
        variant="raised"
        color="#151515"
        intensity={0.25}
        className="font-manrope font-700"
      >
        Save Changes
      </NeumorphButton>
      <NeumorphButton
        variant="pressed"
        color="#151515"
        intensity={0.25}
        className="font-manrope font-700"
      >
        Active Filter
      </NeumorphButton>
    </div>
  );
}
```

## Lyfework Customization Notes
- Set color to #151515 or #1a1a1a for shadow calculation against #0a0a0a
- Manrope 700 text at 14-16px for button labels
- Use rounded-[8px] to match button radius standard
- For primary CTAs, prefer gradient buttons; use neumorphic for secondary actions
- Pair with brand accent text color #ff642a for important secondary actions

## Performance Notes
- Pure CSS box-shadow implementation with no JavaScript animation
- Pressed state transition uses CSS transition (0.15s ease)
- Zero runtime JavaScript cost -- shadows are static CSS
- No repaints triggered on hover (only box-shadow change)
- Sub-1KB component size with no dependencies
