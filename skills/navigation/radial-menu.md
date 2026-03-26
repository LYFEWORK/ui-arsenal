---
name: radial-menu
source: Animate UI
source_url: https://animate-ui.com/docs/components/navigation/radial-menu
category: navigation
tags: radial, menu, circular, pie, animated, expansion
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# RadialMenu

> Circular radial menu with animated expansion that fans out action items in a ring pattern from a central trigger button.

## When to Use
- Quick-action menus where 4-8 actions fan out from a central trigger
- Creative tool palettes in design or editing interfaces
- Right-click or long-press context menus with visual flair
- Floating action buttons (FAB) with expanding action ring
- Dashboard quick-access shortcuts for power users

## When NOT to Use
- Primary navigation — radial menus are supplementary, not primary
- Menus with more than 8 items — the ring becomes too crowded
- Text-heavy menu items — radial works best with icons and short labels
- Accessibility-critical contexts where radial layout is hard to navigate via keyboard
- Mobile interfaces where the radial expansion covers too much content

## Pairs Well With
- `luxe-tooltip` - tooltips on each radial menu item showing the action name
- `cursor-follow` - custom cursor that transforms as it enters the radial zone
- `shimmer-button` - shimmer effect on the central trigger button
- `dock` - use radial menu for quick actions, dock for persistent navigation

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | RadialMenuItem[] | — | Array of menu items (icon, label, onClick) |
| trigger | ReactNode | — | Central trigger button element |
| radius | number | 80 | Distance of items from center in pixels |
| startAngle | number | 0 | Starting angle in degrees |
| endAngle | number | 360 | Ending angle in degrees |
| className | string | — | Container CSS classes |
| itemClassName | string | — | Individual item CSS classes |
| onOpenChange | (open: boolean) => void | — | Callback when menu opens/closes |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/radial-menu"
```

## Usage Example
```jsx
import { RadialMenu } from "@/components/ui/radial-menu";
import { Plus, Calendar, MessageSquare, Phone, FileText } from "lucide-react";

export function QuickActions() {
  return (
    <div className="fixed bottom-8 right-8 z-50">
      <RadialMenu
        radius={90}
        startAngle={-180}
        endAngle={0}
        trigger={
          <button className="w-14 h-14 rounded-full bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white flex items-center justify-center shadow-lg">
            <Plus className="w-6 h-6" />
          </button>
        }
        itemClassName="w-12 h-12 rounded-full lyf-glass bg-[#0a0a0a]/90 text-white flex items-center justify-center border border-white/10 hover:border-[#ff642a]/50"
        items={[
          { icon: <Calendar className="w-5 h-5" />, label: "Book", onClick: () => openBooking() },
          { icon: <MessageSquare className="w-5 h-5" />, label: "Chat", onClick: () => openChat() },
          { icon: <Phone className="w-5 h-5" />, label: "Call", onClick: () => openDialer() },
          { icon: <FileText className="w-5 h-5" />, label: "Form", onClick: () => openForm() },
        ]}
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Trigger button: `bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-full` brand FAB
- Menu items: `lyf-glass bg-[#0a0a0a]/90 border-white/10` with `hover:border-[#ff642a]/50`
- Use `startAngle={-180} endAngle={0}` for bottom-right FAB (fan upward)
- Icon color: `text-white` default, `text-[#ff642a]` on hover
- GHL compatible — perfect for embedding quick-action shortcuts in GHL pages
- Apply `font-manrope font-400` to any text labels on menu items

## Performance Notes
- Items are mounted on open, unmounted on close — no idle DOM footprint
- Spring stagger animation completes in ~300ms total
- Position calculated via trigonometry on mount — no per-frame computation
- Click-outside detection uses single document listener
- Framer-motion AnimatePresence handles clean enter/exit transitions
