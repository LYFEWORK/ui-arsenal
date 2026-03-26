---
name: dynamic-island
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/dynamic-island
category: components
tags: dynamic-island, notification, adaptive, apple, animated, status
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# DynamicIsland

> Apple Dynamic Island-inspired adaptive notification component that morphs between states.

## When to Use
- Persistent notification bar that morphs to show different content
- Status indicators transitioning between compact and expanded states
- Music player or media controls in a Dynamic Island pattern
- Toast/notification replacement with morphing animation
- SaaS dashboard status bar with adaptive content

## When NOT to Use
- Standard toast notifications without morph behavior
- Mobile apps (this is a web component mimicking the pattern)
- Pages where floating UI elements are inappropriate
- Content that must remain in fixed position without animation

## Pairs Well With
- `animated-content` - Content within island morphing between states
- `number-ticker` - Animated counters inside dynamic island
- `shimmer-button` - Action buttons within expanded island
- `blur-text` - Text transitions within the island

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| size | 'compact' \| 'expanded' \| 'minimal' \| 'long' | 'compact' | Island display size |
| children | ReactNode | - | Island content |
| onSizeChange | (size: string) => void | - | Size change callback |
| position | 'top' \| 'bottom' | 'top' | Screen position |
| animated | boolean | true | Enable morph animations |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/dynamic-island"
```

## Usage Example
```jsx
import { DynamicIsland } from "@/components/ui/dynamic-island";
import { useState } from "react";

export function StatusBar() {
  const [size, setSize] = useState("compact");

  return (
    <div className="bg-[#0a0a0a] min-h-screen pt-4">
      <DynamicIsland
        size={size}
        onSizeChange={setSize}
        position="top"
        className="mx-auto"
      >
        {size === "compact" ? (
          <div className="flex items-center gap-2 px-4 py-1">
            <div className="w-2 h-2 bg-[#ff642a] rounded-full animate-pulse" />
            <span className="font-manrope font-700 text-white text-xs">3 new bookings</span>
          </div>
        ) : (
          <div className="p-4">
            <h4 className="font-manrope font-700 text-white text-sm">New Bookings</h4>
            <ul className="mt-2 space-y-1">
              <li className="font-manrope font-400 text-white/60 text-xs">Sarah C. - 2:00 PM</li>
              <li className="font-manrope font-400 text-white/60 text-xs">Mike T. - 3:30 PM</li>
              <li className="font-manrope font-400 text-white/60 text-xs">Dr. Patel - 4:00 PM</li>
            </ul>
          </div>
        )}
      </DynamicIsland>
    </div>
  );
}
```

## Lyfework Customization Notes
- Island bg: #1a1a1a with subtle border-white/10 on #0a0a0a page
- Status dot: brand orange #ff642a with animate-pulse
- Compact text: Manrope 700, expanded content: Manrope 400
- Morph between states on click or programmatic trigger
- Creative notification pattern for SaaS dashboards; test GHL z-index

## Performance Notes
- Framer Motion layout animation for smooth size morphing
- Only current size state content is rendered
- Border-radius animates with spring physics for natural feel
- Single element resizing -- no DOM tree restructuring
- Total animation cost is minimal (one element, transform + dimensions)
