---
name: side-panel
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/side-panel
category: navigation
tags: panel, sidebar, slide, navigation, drawer, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# SidePanel

> Animated side panel for secondary content, navigation, or contextual information.

## When to Use
- Slide-out navigation menus on mobile and tablet
- Settings or filter panels sliding from the side
- Shopping cart or order summary side panels
- Detail panels in list-detail layouts
- Contextual help or documentation panels

## When NOT to Use
- Primary page navigation on desktop (use persistent sidebar)
- Quick tooltips or popovers (use popover component)
- Full-screen takeovers (use modal or expandable-screen)
- Tiny content snippets (use drawer or toast)

## Pairs Well With
- `dock` - Dock item that opens a side panel on click
- `animated-content` - Content inside panel with staggered entrance
- `direction-aware-tabs` - Tabbed navigation within side panel
- `expandable-card` - Expandable sections within side panel content

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| open | boolean | false | Panel visibility |
| onClose | () => void | - | Close handler |
| side | 'left' \| 'right' | 'right' | Panel position |
| width | number \| string | 400 | Panel width |
| overlay | boolean | true | Show backdrop overlay |
| closeOnOverlayClick | boolean | true | Close on backdrop click |
| closeOnEscape | boolean | true | Close on Escape key |
| title | string | '' | Panel header title |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Panel content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/side-panel"
```

## Usage Example
```jsx
import { SidePanel } from "@/components/ui/side-panel";
import { useState } from "react";
import { Menu } from "lucide-react";

export function MobileNav() {
  const [open, setOpen] = useState(false);

  return (
    <>
      <button onClick={() => setOpen(true)} className="p-2 text-white">
        <Menu size={24} />
      </button>
      <SidePanel
        open={open}
        onClose={() => setOpen(false)}
        side="left"
        width={300}
        title="Navigation"
        className="bg-[#0a0a0a] border-r border-white/10"
      >
        <nav className="p-6 space-y-2">
          {["Home", "Services", "About", "Contact"].map((item) => (
            <a
              key={item}
              href={`/${item.toLowerCase()}`}
              className="block py-3 px-4 font-manrope font-700 text-white/80 hover:text-white hover:bg-white/5 rounded-[8px] transition-colors"
            >
              {item}
            </a>
          ))}
          <button className="w-full mt-6 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white">
            Book Now
          </button>
        </nav>
      </SidePanel>
    </>
  );
}
```

## Lyfework Customization Notes
- Panel bg: #0a0a0a with border-white/10 side border
- Nav links: Manrope 700, text-white/80, hover bg-white/5 rounded-[8px]
- CTA button: brand gradient from-[#ff642a] to-[#ff0301], rounded-[8px]
- Title: Manrope 700 with close X button in white/40
- GHL compatible for mobile navigation overlays

## Performance Notes
- Framer Motion slide animation uses GPU-accelerated translateX
- Body scroll is locked while panel is open
- Overlay fade uses CSS opacity transition
- Content is conditionally rendered (unmounted when closed)
- Escape key listener added/removed with panel open state
- Focus trap implemented for keyboard accessibility
