---
name: avatar-circles
source: Magic UI
source_url: https://magicui.design/docs/components/avatar-circles
category: components
tags: avatar, social-proof, users, team, overlap
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# AvatarCircles

> Overlapping stacked avatar circles for displaying users, team members, or social proof counts.

## When to Use
- Social proof sections showing "500+ users trust us"
- Team member displays on about pages
- Testimonial headers with reviewer avatars
- Showing active users on a SaaS landing page
- Community/user count badges

## When NOT to Use
- When you need detailed user profiles with bios
- Single avatar display (use a standard avatar component)
- When avatar images are not available and fallbacks look poor

## Pairs Well With
- `count-up` - Animated number next to avatar stack for user counts
- `animated-content` - Fade in the avatar group on scroll
- `gradient-text` - Gradient heading like "Join 1,200+ clients"
- `spotlight-card` - Avatar circles inside testimonial spotlight cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| avatarUrls | string[] | required | Array of image URLs for avatars |
| numPeople | number | 0 | Extra count shown as "+N" badge |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/avatar-circles"
```

## Usage Example
```jsx
import { AvatarCircles } from "@/components/magicui/avatar-circles";

const clientAvatars = [
  "https://avatars.githubusercontent.com/u/1",
  "https://avatars.githubusercontent.com/u/2",
  "https://avatars.githubusercontent.com/u/3",
  "https://avatars.githubusercontent.com/u/4",
];

export function SocialProofBar() {
  return (
    <section className="bg-[#0a0a0a] py-12">
      <div className="mx-auto max-w-xl flex items-center justify-center gap-4">
        <AvatarCircles avatarUrls={clientAvatars} numPeople={847} />
        <p className="font-manrope font-400 text-white/70 text-sm">
          clinic owners already using{" "}
          <span className="font-700 bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Lyfework
          </span>
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Add a subtle `ring-2 ring-[#0a0a0a]` on each avatar to match dark background overlap
- Use Manrope font-400 for supporting text, font-700 for the brand name
- The "+N" badge can be styled with the `#ff642a` gradient background for brand consistency
- Works seamlessly inside GHL funnels — no JS framework conflicts
- Pair with `count-up` for an animated version of the numPeople value

## Performance Notes
- Pure CSS overlap with negative margins — zero JS overhead
- Images should be small (40-48px circles), use optimized thumbnails
- Lazy-load avatar images if used below the fold
- No animation frame usage — safe for any device
