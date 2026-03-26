---
name: images-badge
source: Aceternity UI
source_url: https://ui.aceternity.com/components/images-badge
category: components
tags: badge, avatar, floating, decorative, images, social-proof
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# ImagesBadge

> Floating avatar or image badges scattered as decorative elements around content, creating social proof or visual interest.

## When to Use
- Social proof displays showing user avatars near testimonials
- Floating team member photos around an "about us" section
- Decorative client logos or partner badges around CTAs
- Visual interest around hero headings with floating user faces
- Community size showcases with scattered member avatars

## When NOT to Use
- When badges overlap critical content or CTAs
- On minimal/clean layouts where floating elements add clutter
- For structured avatar grids (use a standard grid layout instead)

## Pairs Well With
- `animated-content` - Stagger badge entrance animations
- `count-up` - Pair floating avatars with "1,000+ users" counter
- `marquee` - Scrolling badges alongside a logo marquee
- `aurora` - Background aurora behind scattered badges

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| images | array | - | Array of image URLs for the badges |
| className | string | - | Classes for the badge container |
| badgeClassName | string | - | Classes for individual badge elements |

## Installation
```bash
npx aceternity-ui@latest add images-badge
```

## Usage Example
```jsx
import { ImagesBadge } from "@/components/ui/images-badge";

const avatars = [
  "/avatars/user1.webp", "/avatars/user2.webp", "/avatars/user3.webp",
  "/avatars/user4.webp", "/avatars/user5.webp", "/avatars/user6.webp",
];

export function SocialProofHero() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-6 text-center relative overflow-hidden">
      <ImagesBadge images={avatars} className="absolute inset-0" />
      <div className="relative z-10">
        <h2 className="font-[Manrope] font-800 text-5xl text-white">
          Trusted by <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">500+</span> Clinics
        </h2>
        <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-4">
          Join the healthcare providers who chose Lyfework for their digital presence.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Avatar images should be 48x48px or 64x64px WebP with circular crop
- Add `border-2 border-[#ff642a]/30` to badges for brand-colored outlines
- Section uses `overflow-hidden` to contain floating badges within bounds
- Use Manrope 800 for the headline, 400 for subtext on #0a0a0a background
- Zero JS dependencies means full GHL iframe compatibility

## Performance Notes
- Pure CSS positioning with no JavaScript, zero runtime cost
- Avatar images are small (48-64px) so total payload is minimal
- CSS animations for floating use `will-change: transform` for GPU compositing
- No layout recalculation during floating animation
- Safe to use alongside other decorative components without performance conflict
