---
name: family-drawer
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/family-drawer
category: components
tags: drawer, bottom-sheet, expandable, sections, mobile
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# FamilyDrawer

> Bottom drawer with expandable sections and nested content groups.

## When to Use
- Mobile-first action sheets with grouped options
- Bottom sheets with expandable category sections
- Settings drawers with collapsible option groups
- Navigation drawers with nested menu items
- Detail panels sliding up from bottom on mobile

## When NOT to Use
- Desktop-only interfaces (use side panel or modal)
- Simple single-action drawers (use basic drawer)
- Full-page content (use modal or page navigation)
- Drawers with more than 4-5 sections (overwhelming)

## Pairs Well With
- `family-button` - Button that triggers family drawer expansion
- `direction-aware-tabs` - Tabs inside drawer for category navigation
- `expandable-card` - Expandable cards within drawer sections
- `shimmer-button` - Primary action button at drawer bottom

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| open | boolean | false | Drawer visibility |
| onClose | () => void | - | Close handler |
| sections | { title: string; items: ReactNode[] }[] | [] | Grouped sections |
| snapPoints | number[] | [0.4, 0.8] | Height snap points (0-1) |
| showHandle | boolean | true | Show drag handle |
| overlay | boolean | true | Show backdrop overlay |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/family-drawer"
```

## Usage Example
```jsx
import { FamilyDrawer } from "@/components/ui/family-drawer";
import { useState } from "react";

export function MobileActions() {
  const [open, setOpen] = useState(false);

  return (
    <>
      <button
        onClick={() => setOpen(true)}
        className="px-6 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white"
      >
        Quick Actions
      </button>
      <FamilyDrawer
        open={open}
        onClose={() => setOpen(false)}
        snapPoints={[0.4, 0.85]}
        sections={[
          {
            title: "Appointments",
            items: [
              <button className="w-full text-left p-3 font-manrope font-400 text-white/80 hover:bg-white/5 rounded-[8px]">Book New</button>,
              <button className="w-full text-left p-3 font-manrope font-400 text-white/80 hover:bg-white/5 rounded-[8px]">View Upcoming</button>,
            ],
          },
          {
            title: "Account",
            items: [
              <button className="w-full text-left p-3 font-manrope font-400 text-white/80 hover:bg-white/5 rounded-[8px]">Profile</button>,
              <button className="w-full text-left p-3 font-manrope font-400 text-white/80 hover:bg-white/5 rounded-[8px]">Settings</button>,
            ],
          },
        ]}
        className="bg-[#0a0a0a] border-t border-white/10 rounded-t-[16px]"
      />
    </>
  );
}
```

## Lyfework Customization Notes
- Drawer bg: #0a0a0a with border-t border-white/10, rounded-t-[16px]
- Section titles: Manrope 700 text-white/40 uppercase text-xs tracking-wider
- Items: Manrope 400 text-white/80, hover bg-white/5 rounded-[8px]
- Drag handle: bg-white/20 centered bar, 40px wide
- GHL mobile views benefit from bottom drawer patterns

## Performance Notes
- Framer Motion drag with snap-to-point physics simulation
- Body scroll locked while drawer is open
- Overlay uses CSS opacity transition (not backdrop-filter)
- Only visible sections render their item content
- Gesture velocity determines snap point selection
