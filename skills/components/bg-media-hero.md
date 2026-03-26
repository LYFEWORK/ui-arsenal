---
name: bg-media-hero
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/bg-media-hero
category: components
tags: hero, video, image, background, media, full-bleed
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# BgMediaHero

> Full-bleed background media hero with video or image support and overlay controls.

## When to Use
- Landing pages with cinematic video backgrounds
- Clinic or spa sites showcasing facility imagery
- SaaS product pages with demo video as hero background
- Real estate or portfolio sites with full-bleed visuals
- Campaign pages with brand video content

## When NOT to Use
- Mobile-first pages where video adds significant data cost
- Pages needing fast LCP scores (video delays first paint)
- Accessibility-critical pages without proper media alternatives

## Pairs Well With
- `blur-text` - Text blur-in reveal over video background creates cinematic entrance
- `shimmer-button` - CTA shimmer over dark video overlay draws action
- `animated-content` - Staggered content entrance over media background
- `gradient-text` - Gradient heading over darkened video hero

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| src | string | '' | Video or image source URL |
| type | 'video' \| 'image' | 'video' | Media type |
| overlay | boolean | true | Enable dark overlay |
| overlayOpacity | number | 0.5 | Overlay darkness (0-1) |
| poster | string | '' | Video poster image for loading state |
| autoPlay | boolean | true | Auto-play video |
| loop | boolean | true | Loop video playback |
| muted | boolean | true | Mute video (required for autoplay) |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/bg-media-hero"
```

## Usage Example
```jsx
import { BgMediaHero } from "@/components/ui/bg-media-hero";

export function ClinicVideoHero() {
  return (
    <BgMediaHero
      src="/videos/clinic-tour.mp4"
      type="video"
      poster="/images/clinic-poster.jpg"
      overlay={true}
      overlayOpacity={0.6}
      className="min-h-screen"
    >
      <div className="flex flex-col items-center justify-center min-h-screen px-6 text-center">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Welcome to Better Care
        </h1>
        <p className="font-manrope font-400 text-white/70 mt-4 max-w-lg">
          Experience world-class treatment in a modern facility.
        </p>
        <button className="mt-8 px-8 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white">
          Book a Tour
        </button>
      </div>
    </BgMediaHero>
  );
}
```

## Lyfework Customization Notes
- Set overlayOpacity to 0.5-0.7 so Manrope headings remain readable
- Use brand gradient CTA buttons over darkened media for contrast
- Provide poster image for fast LCP before video loads
- GHL compatible when using image mode; video may need lazy-loading
- Apply `lyf-glass` to floating content cards over media background

## Performance Notes
- Video uses lazy loading with poster fallback for fast initial paint
- Muted autoplay does not require user interaction to start
- Use compressed MP4 (H.264) under 5MB for hero videos
- Image mode uses object-fit: cover with loading="eager" for LCP
- IntersectionObserver pauses video when scrolled out of view
