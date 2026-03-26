---
name: text-gif
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/text-gif
category: text-animations
tags: text, gif, mask, animated, creative, typography
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# TextGif

> Text filled with an animated GIF as a clipping mask, creating motion-filled typography.

## When to Use
- Hero headlines with visually striking animated fill
- Creative portfolio site names with branded motion
- Event or launch pages with high-impact text treatment
- Social media preview sections with attention-grabbing headers
- Brand name displays with signature animated texture

## When NOT to Use
- Body text or paragraphs (readability suffers with animated fill)
- Professional or corporate sites where GIF fill feels too playful
- Performance-sensitive pages where GIF assets add payload
- Accessibility-critical headings where motion reduces readability
- Mobile pages where GIF decoding impacts performance

## Pairs Well With
- `gradient-text` - Use TextGif for hero, gradient-text for sub-headings
- `particles` - Particles around GIF-filled text for cohesive motion
- `aurora` - Aurora background with GIF-masked text overlay
- `shimmer-button` - Shimmer CTA paired with animated text hero

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | '' | Display text |
| src | string | '' | GIF source URL |
| as | 'h1' \| 'h2' \| 'h3' \| 'span' | 'h1' | HTML element type |
| fallbackColor | string | '#ff642a' | Color when GIF fails to load |
| objectFit | 'cover' \| 'contain' \| 'fill' | 'cover' | GIF sizing within text |
| objectPosition | string | 'center' | GIF position within text mask |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/text-gif"
```

## Usage Example
```jsx
import { TextGif } from "@/components/ui/text-gif";

export function CreativeHero() {
  return (
    <section className="bg-[#0a0a0a] min-h-screen flex items-center justify-center px-6">
      <div className="text-center">
        <TextGif
          text="CREATE"
          src="/gifs/fire-gradient.gif"
          as="h1"
          fallbackColor="#ff642a"
          objectFit="cover"
          className="font-manrope font-800 text-[120px] leading-none"
        />
        <p className="font-manrope font-400 text-white/60 mt-6 max-w-md mx-auto text-lg">
          Bold ideas deserve bold execution.
        </p>
        <button className="mt-8 px-10 py-4 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white text-lg">
          Start Building
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use short, bold words (1-2) for maximum GIF visibility in text mask
- Manrope 800 at large sizes (80-120px+) for thick letter strokes
- Fire/lava GIFs with brand orange tones match #ff642a palette
- fallbackColor="#ff642a" provides brand-colored degradation
- Not recommended for GHL embeds -- use gradient-text as alternative

## Performance Notes
- CSS background-clip: text with background-image handles the masking
- GIF file size is the main performance concern -- keep under 500KB
- Use optimized GIFs with reduced frame count and color palette
- No JavaScript required -- pure CSS implementation
- Falls back to solid color if GIF fails to load (network resilience)
- Preload GIF asset for instant hero display on page load
