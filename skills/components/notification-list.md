---
name: notification-list
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/notification-list
category: components
tags: notification, list, toast, animated, enter, exit, stack
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# NotificationList

> Animated notification stack with smooth enter/exit transitions, supporting swipe-to-dismiss and auto-dismiss timers.

## When to Use
- Dashboard notification centers showing recent activity
- Real-time alert displays for form submissions or booking confirmations
- Activity feeds showing system events or user actions
- In-app notification panels that stack and animate
- Admin panels displaying queued tasks or pending reviews

## When NOT to Use
- Toast notifications — use a dedicated toast library (sonner)
- Static notification badge counts — use luxe-badge instead
- Email-style inboxes with complex threading — use a full inbox component
- Critical alerts requiring modal interruption — use a dialog

## Pairs Well With
- `luxe-badge` - unread count badge on the notification bell trigger
- `avatar-group` - user avatars on notification items showing who triggered the event
- `management-bar` - bulk actions bar when notifications are multi-selected
- `animated-content` - stagger-animate notification items on panel open

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| notifications | NotificationItem[] | — | Array of notification objects |
| onDismiss | (id: string) => void | — | Callback when notification is dismissed |
| onAction | (id: string, action: string) => void | — | Callback for notification action click |
| className | string | — | Container CSS classes |
| maxVisible | number | 5 | Maximum visible notifications |
| autoDismiss | boolean | false | Enable auto-dismiss after timeout |
| dismissTimeout | number | 5000 | Auto-dismiss timeout in ms |
| swipeToDismiss | boolean | true | Enable swipe-to-dismiss gesture |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/notification-list"
```

## Usage Example
```jsx
import { NotificationList } from "@/components/ui/notification-list";

export function DashboardNotifications() {
  const notifications = [
    {
      id: "1",
      title: "New Booking",
      message: "Sarah Chen booked a consultation for March 28",
      time: "2 min ago",
      type: "success",
    },
    {
      id: "2",
      title: "Review Received",
      message: "5-star review from Mark Rivera on Google",
      time: "15 min ago",
      type: "info",
    },
    {
      id: "3",
      title: "Follow-up Due",
      message: "Lisa Thompson's follow-up appointment is overdue",
      time: "1 hour ago",
      type: "warning",
    },
  ];

  return (
    <div className="w-96 lyf-glass rounded-[12px] p-4 bg-[#0a0a0a]/95 border border-white/10">
      <h3 className="font-manrope font-700 text-white mb-4">Notifications</h3>
      <NotificationList
        notifications={notifications}
        onDismiss={(id) => dismissNotification(id)}
        swipeToDismiss
        maxVisible={5}
        className="space-y-2"
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Container: `lyf-glass rounded-[12px] border border-white/10 bg-[#0a0a0a]/95`
- Notification title: `font-manrope font-700 text-white text-sm`
- Notification body: `font-manrope font-400 text-gray-400 text-xs`
- Type accent colors: success `border-l-green-500`, warning `border-l-[#ff642a]`, error `border-l-[#ff0301]`
- GHL compatible — notification data can come from GHL webhook events
- Timestamp text: `font-manrope font-400 text-gray-500 text-xs`

## Performance Notes
- AnimatePresence handles enter/exit — only visible items are in DOM
- Swipe-to-dismiss uses gesture detection with velocity threshold
- Auto-dismiss timers are cleared on component unmount — no memory leaks
- Height animation uses framer-motion layout — smooth collapse on dismiss
- Handles rapid add/remove without animation queue buildup
