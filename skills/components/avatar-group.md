---
name: avatar-group
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/avatar-group
category: components
tags: avatar, group, stack, team, users, overlap
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# AvatarGroup

> Animated stacked avatar group that expands on hover to reveal individual team members with smooth spring transitions.

## When to Use
- Team or staff sections showing clinic practitioners or agency members
- Social proof elements displaying recent customers or active users
- Collaboration indicators showing who is working on a project
- Testimonial sections with multiple reviewer avatars
- Comment or activity feeds showing participant avatars

## When NOT to Use
- Single user profile displays — use a standard avatar component
- Lists requiring names and details alongside avatars — use a user list
- Situations with 20+ avatars — use a count badge instead of stacking
- Static print layouts where hover expansion is unavailable

## Pairs Well With
- `marquee` - scrolling avatar groups for social proof or team showcases
- `spotlight-card` - avatar group header on team member spotlight cards
- `animated-content` - stagger-animate the avatar group on scroll entry
- `number-ticker` - "+42 more" counter that ticks up alongside the avatar group

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| avatars | AvatarItem[] | — | Array of avatar data (src, alt, fallback) |
| max | number | 5 | Maximum avatars to show before "+N" counter |
| size | "sm" \| "md" \| "lg" | "md" | Avatar size preset |
| className | string | — | Container CSS classes |
| expandOnHover | boolean | true | Enable hover expansion animation |
| borderColor | string | "bg-background" | Ring color around each avatar |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/avatar-group"
```

## Usage Example
```jsx
import { AvatarGroup } from "@/components/ui/avatar-group";

export function TeamSection() {
  const team = [
    { src: "/team/dr-sarah.jpg", alt: "Dr. Sarah Chen", fallback: "SC" },
    { src: "/team/dr-james.jpg", alt: "Dr. James Park", fallback: "JP" },
    { src: "/team/maria.jpg", alt: "Maria Lopez", fallback: "ML" },
    { src: "/team/david.jpg", alt: "David Kim", fallback: "DK" },
    { src: "/team/aisha.jpg", alt: "Aisha Patel", fallback: "AP" },
  ];

  return (
    <section className="py-16 bg-[#0a0a0a] text-center">
      <p className="font-manrope font-400 text-gray-400 mb-4">Trusted by our team</p>
      <div className="flex justify-center">
        <AvatarGroup
          avatars={team}
          max={5}
          size="lg"
          borderColor="#0a0a0a"
          className="[&_span]:ring-2 [&_span]:ring-[#0a0a0a]"
        />
      </div>
      <p className="font-manrope font-700 text-white mt-4">5 Specialists Ready to Help</p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `borderColor` to `"#0a0a0a"` to match dark background seamlessly
- Fallback initials should use `font-manrope font-700` with brand gradient background
- Surrounding text uses `font-manrope font-400` (labels) and `font-700` (emphasis)
- "+N more" counter should use brand orange `text-[#ff642a]` for accent
- GHL compatible — standard img elements with CSS overlap, no layout issues
- On `lyf-glass` containers, set border color to transparent for glass-through effect

## Performance Notes
- Images loaded lazily — only visible avatars are fetched
- Hover expansion uses CSS transform — no layout recalculation
- Fallback initials rendered via CSS — no extra image requests
- Spring animation via framer-motion is lightweight on 5-8 avatars
- Consider fixed max of 5-6 for optimal visual balance and performance
