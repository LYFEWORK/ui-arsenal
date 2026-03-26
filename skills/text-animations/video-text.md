---
name: video-text
source: Magic UI
source_url: https://magicui.design/docs/components/video-text
category: text-animations
tags: text, video, mask, clip, cinematic
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-25
---

# VideoText

> Text filled with video content using the text as a clipping mask, creating a cinematic effect.

## When to Use
- Hero headlines on creative agency or portfolio sites
- Product launch pages with high-impact visual treatment
- Brand name displays with ambient video fill
- Event or conference landing page headlines
- Artistic portfolio headers

## When NOT to Use
- Performance-critical pages where video loading delays LCP
- Mobile-first designs where video bandwidth is a concern
- Text that needs to be immediately readable (video distracts)
- Professional/medical contexts requiring conservative design
- Small text where the video fill is indistinguishable

## Pairs Well With
- `particles` - Particle overlay on top of the video text
- `aurora` - Aurora background beneath the video text section
- `animated-content` - Fade in the video text section
- `blur-text` - Blur-reveal supporting text below the video headline

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Text content to use as mask |
| src | string | required | Video source URL |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/video-text"
```

## Usage Example
```jsx
import { VideoText } from "@/components/magicui/video-text";

export function CinematicHero() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <VideoText
        src="/videos/abstract-gradient.mp4"
        className="font-manrope font-800 text-8xl uppercase tracking-tight"
      >
        LYFEWORK
      </VideoText>
      <p className="font-manrope font-400 text-white/60 text-xl mt-8 max-w-md mx-auto">
        The future of clinic management
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use an abstract gradient video with `#ff642a` to `#ff0301` tones for brand consistency
- Manrope font-800 at text-7xl or larger for the video-filled text
- Keep text to 1-2 words for maximum visual impact
- Video should loop seamlessly and be short (3-5 seconds)
- GHL note: Video autoplay requires `muted playsinline` attributes — test in GHL iframes

## Performance Notes
- Video element loads and plays — significant bandwidth and GPU cost
- Use compressed MP4 (H.264) at 720p or lower for the video source
- Video should be lazy-loaded and only play when in viewport
- `background-clip: text` is GPU composited but video decoding adds overhead
- Consider a fallback gradient for slow connections or unsupported browsers
- Set `preload="none"` and trigger load on intersection for below-fold placement
