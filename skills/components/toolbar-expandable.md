---
name: toolbar-expandable
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/toolbar-expandable
category: components
tags: toolbar, expandable, actions, animated, menu
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ToolbarExpandable

> Expandable toolbar with animated items that collapse and expand to reveal actions.

## When to Use
- Floating action toolbars in dashboard or editor interfaces
- Compact navigation bars that expand on interaction
- Mobile-friendly action menus saving screen space
- Context-specific tool palettes for content editing
- Bottom bars with expandable option sets

## When NOT to Use
- Primary site navigation (use proper nav components)
- Toolbar with fewer than 3 items (no benefit from expansion)
- Pages where all actions must be persistently visible

## Pairs Well With
- `floating-panel` - Toolbar items that open floating panels
- `family-button` - Nested expandable within toolbar items
- `dock` - Alternative compact navigation pattern
- `animated-content` - Content that responds to toolbar state changes

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | { icon: ReactNode; label: string; onClick: () => void }[] | [] | Toolbar action items |
| expanded | boolean | false | Controlled expansion state |
| onToggle | (expanded: boolean) => void | - | Expansion toggle handler |
| position | 'top' \| 'bottom' \| 'left' \| 'right' | 'bottom' | Toolbar position |
| orientation | 'horizontal' \| 'vertical' | 'horizontal' | Item layout direction |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/toolbar-expandable"
```

## Usage Example
```jsx
import { ToolbarExpandable } from "@/components/ui/toolbar-expandable";
import { Edit, Image, Type, Palette, Settings } from "lucide-react";

export function EditorToolbar() {
  return (
    <div className="bg-[#0a0a0a] min-h-screen relative">
      <ToolbarExpandable
        items={[
          { icon: <Edit size={18} />, label: "Edit", onClick: () => {} },
          { icon: <Image size={18} />, label: "Media", onClick: () => {} },
          { icon: <Type size={18} />, label: "Text", onClick: () => {} },
          { icon: <Palette size={18} />, label: "Theme", onClick: () => {} },
          { icon: <Settings size={18} />, label: "Settings", onClick: () => {} },
        ]}
        position="bottom"
        orientation="horizontal"
        className="lyf-glass rounded-[12px] border border-white/10"
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Container: lyf-glass, 12px radius, border-white/10
- Icons: white/60 default, #ff642a active/hover state
- Labels: Manrope 400 text-xs, appear on expansion
- Position at bottom for mobile-friendly thumb-reach
- GHL compatible for simple dashboard toolbars

## Performance Notes
- Framer Motion staggered animation for item reveals
- Collapsed state renders only the toggle button
- Spring animation for natural expansion feel
- Click-outside detection with passive event listener
- Total animation affects 3-6 elements -- lightweight
