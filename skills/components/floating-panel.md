---
name: floating-panel
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/floating-panel
category: components
tags: panel, floating, draggable, overlay, widget
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# FloatingPanel

> Floating draggable panel overlay for secondary content, tools, or contextual information.

## When to Use
- Floating help or chat widgets on application pages
- Draggable tool palettes in dashboard interfaces
- Contextual info panels that don't block main content
- Mini-player or preview panels floating over content
- Persistent action panels users can reposition

## When NOT to Use
- Primary content that should be inline (use cards instead)
- Mobile layouts where floating panels block too much screen
- Simple tooltips or popovers (use popover component)
- Modal dialogs requiring user attention (use modal)

## Pairs Well With
- `dock` - Dock that opens floating panels on item click
- `family-button` - Family button triggering floating panel
- `animated-content` - Content inside floating panel with entrance animation
- `toolbar-expandable` - Expandable toolbar inside floating panel

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | '' | Panel header title |
| open | boolean | false | Panel visibility |
| onClose | () => void | - | Close handler |
| draggable | boolean | true | Enable drag repositioning |
| position | { x: number; y: number } | { x: 20, y: 20 } | Initial position |
| width | number \| string | 320 | Panel width |
| resizable | boolean | false | Enable resize handles |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Panel content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/floating-panel"
```

## Usage Example
```jsx
import { FloatingPanel } from "@/components/ui/floating-panel";
import { useState } from "react";

export function HelpWidget() {
  const [open, setOpen] = useState(false);

  return (
    <>
      <button
        onClick={() => setOpen(true)}
        className="fixed bottom-6 right-6 w-12 h-12 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-full flex items-center justify-center text-white font-manrope font-700 z-50"
      >
        ?
      </button>
      <FloatingPanel
        title="Need Help?"
        open={open}
        onClose={() => setOpen(false)}
        position={{ x: window.innerWidth - 360, y: window.innerHeight - 420 }}
        width={340}
        className="lyf-glass rounded-[12px] border border-white/10"
      >
        <div className="p-4">
          <p className="font-manrope font-400 text-white/70 text-sm">
            Search our knowledge base or chat with support.
          </p>
          <input
            className="mt-3 w-full p-2 bg-white/5 border border-white/10 rounded-[8px] font-manrope text-white text-sm"
            placeholder="Search for help..."
          />
        </div>
      </FloatingPanel>
    </>
  );
}
```

## Lyfework Customization Notes
- Panel: lyf-glass, 12px radius, border-white/10 on #0a0a0a
- Title: Manrope 700, close button with white/40 hover white/80
- Trigger: brand gradient circle button in fixed bottom-right
- Input fields: bg-white/5, border-white/10, rounded-[8px]
- Test z-index stacking with GHL chat widgets if both are present

## Performance Notes
- Framer Motion drag uses GPU-accelerated transforms
- Panel content renders only when open (conditional mounting)
- Drag constraints prevent panel from leaving viewport
- No continuous animation -- only responds to user drag input
- Resizable mode adds resize observer (minimal overhead)
