---
name: family-button
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/family-button
category: components
tags: button, expandable, group, fan, actions, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# FamilyButton

> Expandable button group that fans out additional action options on interaction.

## When to Use
- Compact action menus that expand on click/hover
- Mobile-friendly action groups saving horizontal space
- Dashboard quick-action buttons with multiple sub-actions
- Creative navigation patterns with fanning menu items
- Social sharing buttons that expand from a single trigger

## When NOT to Use
- When all actions should be visible simultaneously
- Forms with critical actions that shouldn't be hidden
- Accessibility-critical contexts where hidden actions are problematic
- Simple two-button layouts where expansion adds unnecessary complexity

## Pairs Well With
- `shimmer-button` - Primary trigger button with shimmer effect
- `animated-content` - Content that responds to button expansion state
- `dock` - Family button integrated into a floating dock
- `floating-panel` - Expanded actions triggering floating panel content

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| trigger | ReactNode | - | Primary button content |
| actions | { label: string; icon?: ReactNode; onClick: () => void }[] | [] | Expandable action items |
| direction | 'up' \| 'down' \| 'left' \| 'right' | 'up' | Fan expansion direction |
| spacing | number | 8 | Gap between fanned items in pixels |
| expandOn | 'click' \| 'hover' | 'click' | Expansion trigger |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/family-button"
```

## Usage Example
```jsx
import { FamilyButton } from "@/components/ui/family-button";
import { Share2, Twitter, Linkedin, Mail } from "lucide-react";

export function ShareActions() {
  return (
    <div className="bg-[#0a0a0a] p-8">
      <FamilyButton
        trigger={
          <span className="flex items-center gap-2 font-manrope font-700">
            <Share2 size={16} /> Share
          </span>
        }
        actions={[
          { label: "Twitter", icon: <Twitter size={16} />, onClick: () => {} },
          { label: "LinkedIn", icon: <Linkedin size={16} />, onClick: () => {} },
          { label: "Email", icon: <Mail size={16} />, onClick: () => {} },
        ]}
        direction="up"
        expandOn="click"
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Trigger button: brand gradient background, Manrope 700, rounded-[8px]
- Fanned items: bg-white/10 with hover bg-white/20 on #0a0a0a
- Use direction="up" for bottom-positioned action bars
- Manrope 400 labels for individual action items
- GHL compatible for compact action menus in funnel pages

## Performance Notes
- Framer Motion spring animations for natural fanning motion
- Only visible items participate in layout (AnimatePresence)
- Click-outside listener cleans up on unmount
- Collapsed state renders only the trigger button
- Total animation cost is minimal -- 3-5 elements with transform only
