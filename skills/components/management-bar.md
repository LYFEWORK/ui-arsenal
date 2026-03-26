---
name: management-bar
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/management-bar
category: components
tags: toolbar, action bar, management, bulk actions, animated, selection
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ManagementBar

> Animated action management toolbar that slides in when items are selected, providing contextual bulk action controls.

## When to Use
- Dashboard list views with bulk selection actions (delete, archive, export)
- Email or notification inbox with multi-select management
- File manager interfaces with bulk operations toolbar
- CRM contact lists with batch action capabilities
- Admin panels managing multiple records simultaneously

## When NOT to Use
- Single-item action contexts — use inline actions or context menus
- Mobile layouts where a bottom bar conflicts with navigation
- Read-only views without any actionable operations
- Simple lists without selection capability

## Pairs Well With
- `notification-list` - management bar appears when notifications are selected
- `luxe-checkbox` - animated checkboxes for item selection triggering the bar
- `copy-button` - copy action within the management bar for selected items
- `animated-content` - slide-in animation for the bar entrance

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| visible | boolean | false | Control bar visibility |
| selectedCount | number | 0 | Number of selected items |
| actions | ActionItem[] | — | Array of action buttons to display |
| onClose | () => void | — | Callback when bar is dismissed |
| className | string | — | Additional CSS classes |
| position | "top" \| "bottom" | "bottom" | Bar position on screen |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/management-bar"
```

## Usage Example
```jsx
import { ManagementBar } from "@/components/ui/management-bar";
import { Trash2, Archive, Download } from "lucide-react";

export function PatientListManager({ selectedPatients }) {
  return (
    <ManagementBar
      visible={selectedPatients.length > 0}
      selectedCount={selectedPatients.length}
      position="bottom"
      className="lyf-glass rounded-[12px] border border-white/10 bg-[#0a0a0a]/95 font-manrope"
      onClose={() => clearSelection()}
      actions={[
        {
          icon: <Archive className="w-4 h-4" />,
          label: "Archive",
          onClick: () => archivePatients(selectedPatients),
          className: "text-gray-300 hover:text-[#ff642a]",
        },
        {
          icon: <Download className="w-4 h-4" />,
          label: "Export",
          onClick: () => exportPatients(selectedPatients),
          className: "text-gray-300 hover:text-[#ff642a]",
        },
        {
          icon: <Trash2 className="w-4 h-4" />,
          label: "Delete",
          onClick: () => deletePatients(selectedPatients),
          className: "text-gray-300 hover:text-red-400",
        },
      ]}
    />
  );
}
```

## Lyfework Customization Notes
- Bar container: `lyf-glass rounded-[12px] border-white/10 bg-[#0a0a0a]/95`
- Action button hover: `hover:text-[#ff642a]` for standard actions, `hover:text-red-400` for destructive
- Count text: `font-manrope font-700 text-white` for selected item count
- Action labels: `font-manrope font-400 text-gray-300`
- GHL compatible — fixed positioning works in embedded iframe contexts
- Use `position="bottom"` for consistency with mobile app patterns

## Performance Notes
- Bar rendered conditionally — not in DOM when no items selected
- Slide animation via framer-motion AnimatePresence — clean mount/unmount
- Action buttons are static — no continuous animation overhead
- Fixed positioning avoids layout recalculation of underlying content
- Handles rapid selection/deselection without animation jank
