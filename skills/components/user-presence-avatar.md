---
name: user-presence-avatar
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/user-presence-avatar
category: components
tags: avatar, presence, online, status, indicator, real-time
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# UserPresenceAvatar

> Avatar component with animated online presence indicator showing real-time availability status with pulsing dot animation.

## When to Use
- Team directories showing who is currently available
- Chat or messaging interfaces displaying user online status
- Dashboard user lists with live availability indicators
- Clinic staff pages showing which practitioners are on-duty
- Collaboration tools indicating active participants

## When NOT to Use
- Static team pages without real-time status data
- Contexts where presence tracking raises privacy concerns
- Avatar displays where status is irrelevant (testimonials, about pages)
- Large grids where pulsing indicators on every avatar is overwhelming

## Pairs Well With
- `avatar-group` - presence indicators on stacked avatar groups
- `luxe-tooltip` - tooltip showing "Online" / "Away" / "Busy" on hover
- `notification-list` - presence-aware notifications showing sender status
- `spotlight-card` - team member cards with live presence indicators

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| src | string | — | Avatar image URL |
| alt | string | — | Avatar alt text |
| fallback | string | — | Fallback initials when image fails |
| status | "online" \| "away" \| "busy" \| "offline" | "offline" | Presence status |
| size | "sm" \| "md" \| "lg" | "md" | Avatar size preset |
| className | string | — | Additional CSS classes |
| pulse | boolean | true | Enable pulse animation on online status |
| showStatus | boolean | true | Show/hide the status indicator dot |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/user-presence-avatar"
```

## Usage Example
```jsx
import { UserPresenceAvatar } from "@/components/ui/user-presence-avatar";

export function StaffAvailability() {
  const staff = [
    { name: "Dr. Sarah Chen", src: "/team/sarah.jpg", status: "online", role: "Dentist" },
    { name: "Dr. James Park", src: "/team/james.jpg", status: "busy", role: "Orthodontist" },
    { name: "Maria Lopez", src: "/team/maria.jpg", status: "away", role: "Hygienist" },
  ];

  return (
    <section className="py-12 bg-[#0a0a0a]">
      <h3 className="font-manrope font-800 text-2xl text-white text-center mb-8">
        Available Now
      </h3>
      <div className="flex justify-center gap-8">
        {staff.map((s) => (
          <div key={s.name} className="text-center">
            <UserPresenceAvatar
              src={s.src}
              alt={s.name}
              fallback={s.name.split(" ").map(n => n[0]).join("")}
              status={s.status}
              size="lg"
              className="ring-2 ring-white/10"
            />
            <p className="font-manrope font-700 text-white text-sm mt-3">{s.name}</p>
            <p className="font-manrope font-400 text-[#ff642a] text-xs">{s.role}</p>
          </div>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Online dot: `bg-green-500` with pulse animation
- Busy dot: `bg-[#ff0301]` static (no pulse)
- Away dot: `bg-[#ff642a]` with slow pulse
- Avatar ring: `ring-2 ring-white/10` on `#0a0a0a` backgrounds
- Fallback initials: `font-manrope font-700` with `bg-gradient-to-r from-[#ff642a] to-[#ff0301]`
- GHL compatible — presence status can be driven by GHL user online status webhooks
- Name text: `font-manrope font-700 text-white`, role: `font-400 text-[#ff642a]`

## Performance Notes
- Pulse animation is CSS-only — no JavaScript animation loop
- Image loaded with lazy loading by default for off-screen avatars
- Fallback initials render instantly — no flash of empty state
- Status indicator is a pseudo-element — no additional DOM nodes
- Pulse animation uses `will-change: opacity` for GPU acceleration
