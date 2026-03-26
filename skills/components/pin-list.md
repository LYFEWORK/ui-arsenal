---
name: pin-list
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/pin-list
category: components
tags: pin, list, reorder, drag, prioritize, bookmarks
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# PinList

> Pinnable list items with reorder animation, allowing users to pin important items to the top with smooth layout transitions.

## When to Use
- Dashboard task lists where users pin priority items
- Bookmark or favorites lists with pinned items at the top
- CRM contact lists with VIP/priority patient pinning
- Resource libraries where users pin frequently accessed items
- Settings pages with pinnable quick-access preferences

## When NOT to Use
- Static lists without user personalization — use a standard list
- Ordered lists where the order is fixed by data (chronological, alphabetical)
- Very short lists (2-3 items) where pinning adds no organizational value
- Mobile lists where pin/unpin gestures conflict with scroll behavior

## Pairs Well With
- `luxe-checkbox` - checkbox for multi-select alongside pin toggle
- `notification-list` - pinnable notifications that stay at the top
- `management-bar` - bulk pin/unpin actions via the management toolbar
- `animated-content` - stagger-animate the list items on first load

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | PinListItem[] | — | Array of list items with pin state |
| onPinChange | (id: string, pinned: boolean) => void | — | Callback on pin toggle |
| onReorder | (items: PinListItem[]) => void | — | Callback on drag reorder |
| className | string | — | Container CSS classes |
| renderItem | (item: PinListItem) => ReactNode | — | Custom item renderer |
| pinnedClassName | string | — | CSS classes for pinned items |
| enableDragReorder | boolean | true | Enable drag-to-reorder |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/pin-list"
```

## Usage Example
```jsx
import { PinList } from "@/components/ui/pin-list";
import { Pin } from "lucide-react";

export function PatientPriorityList() {
  const [patients, setPatients] = useState([
    { id: "1", name: "Sarah Chen", status: "Follow-up due", pinned: true },
    { id: "2", name: "Mark Rivera", status: "New patient", pinned: false },
    { id: "3", name: "Lisa Thompson", status: "Appointment today", pinned: true },
    { id: "4", name: "David Kim", status: "Lab results ready", pinned: false },
  ]);

  return (
    <div className="lyf-glass rounded-[12px] p-6 bg-[#0a0a0a]/80">
      <h3 className="font-manrope font-700 text-white mb-4">Priority Patients</h3>
      <PinList
        items={patients}
        onPinChange={(id, pinned) => togglePin(id, pinned)}
        onReorder={setPatients}
        pinnedClassName="border-l-2 border-[#ff642a] bg-[#ff642a]/5"
        renderItem={(item) => (
          <div className="flex items-center justify-between py-3 px-4">
            <div>
              <p className="font-manrope font-700 text-white text-sm">{item.name}</p>
              <p className="font-manrope font-400 text-gray-400 text-xs">{item.status}</p>
            </div>
          </div>
        )}
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Pinned item accent: `border-l-2 border-[#ff642a]` with `bg-[#ff642a]/5` background tint
- Pin icon: `text-[#ff642a]` when pinned, `text-gray-500` when unpinned
- Item text: `font-manrope font-700` for names, `font-manrope font-400` for descriptions
- Container: `lyf-glass rounded-[12px] bg-[#0a0a0a]/80`
- GHL compatible — list state can sync with GHL custom fields for patient priority
- Use `rounded-[8px]` on individual list items for consistent border radius

## Performance Notes
- Layout animations via framer-motion Reorder — smooth position transitions
- Only pinned/unpinned items re-sort — no full list re-render
- Drag handle uses pointer events — no scroll blocking
- Virtual scrolling recommended for lists with 50+ items
- Pin state changes are batched to prevent animation conflicts
