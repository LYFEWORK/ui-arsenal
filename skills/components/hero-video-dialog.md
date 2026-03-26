---
name: hero-video-dialog
source: Magic UI
source_url: https://magicui.design/docs/components/hero-video-dialog
category: components
tags: video, modal, dialog, hero, thumbnail
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# HeroVideoDialog

> Video modal with an animated thumbnail trigger — click to expand into a full-screen video player overlay.

## When to Use
- Hero sections with a product demo video
- Case study pages with client testimonial videos
- Feature showcase with a walkthrough video
- Landing pages where video increases conversion
- Portfolio project detail pages

## When NOT to Use
- Inline video players that should play without a modal
- Background ambient videos (use a regular video element)
- Audio-only content or podcast embeds

## Pairs Well With
- `spotlight-card` - Spotlight glow around the video thumbnail
- `animated-content` - Fade in the thumbnail on scroll
- `shimmer-button` - "Watch demo" shimmer CTA below the thumbnail
- `blur-text` - Blur-reveal heading above the video section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| videoSrc | string | required | Video URL (YouTube, Vimeo, or direct) |
| thumbnailSrc | string | required | Thumbnail image URL |
| thumbnailAlt | string | "Video thumbnail" | Alt text for thumbnail |
| animationStyle | "from-bottom" \| "from-center" \| "from-top" \| "fade" | "from-center" | Modal entrance animation |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/hero-video-dialog"
```

## Usage Example
```jsx
import { HeroVideoDialog } from "@/components/magicui/hero-video-dialog";

export function DemoSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <div className="mx-auto max-w-4xl text-center">
        <h2 className="font-manrope font-800 text-4xl text-white mb-4">
          See{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
            Lyfework
          </span>{" "}
          in action
        </h2>
        <p className="font-manrope font-400 text-white/60 mb-12">
          Watch how clinics cut no-shows by 40% with automated scheduling.
        </p>
        <HeroVideoDialog
          videoSrc="https://www.youtube.com/embed/dQw4w9WgXcQ"
          thumbnailSrc="/images/demo-thumbnail.jpg"
          thumbnailAlt="Lyfework product demo video"
          animationStyle="from-center"
          className="rounded-[12px] border border-white/10"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Add `rounded-[12px] border border-white/10` to match card styling conventions
- Play button overlay can be tinted with `#ff642a` for brand consistency
- Thumbnail should be optimized (WebP, 1280x720) for fast LCP
- Modal backdrop uses blur — complements the `lyf-glass` design language
- GHL compatible — dialog uses React Portal, renders outside GHL container safely

## Performance Notes
- Video iframe only loads when modal opens — no initial bandwidth cost
- Thumbnail image is the only initial paint — optimize for LCP
- Framer Motion animation runs on GPU-composited properties (opacity, transform)
- Modal unmounts when closed, freeing video player memory
- Use `loading="lazy"` on the thumbnail image if below the fold
