---
name: pixel-heading
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/pixel-heading
category: text-animations
tags: pixel, heading, text, animation, retro, character
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# PixelHeading

> Pixel-art style heading with character-by-character animation from pixelated to crisp.

## When to Use
- Creative hero sections with unique text entrance animation
- Gaming or retro-themed landing pages
- Portfolio sites demonstrating creative code abilities
- Loading or reveal states for heading text
- Event or campaign pages with distinctive typography

## When NOT to Use
- Professional or corporate pages where pixel style feels casual
- Long headings where character animation takes too long
- Accessibility-critical contexts where animated text is disorienting
- Mobile screens where pixel detail is lost at small sizes

## Pairs Well With
- `particles` - Pixel particles dissolving into/from heading text
- `background-texture` - Noise texture complementing pixel aesthetic
- `lightboard` - LED lightboard + pixel heading for full retro theme
- `aurora` - Modern aurora background contrasting with retro pixel text

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | '' | Heading text content |
| as | 'h1' \| 'h2' \| 'h3' | 'h1' | HTML heading element |
| pixelSize | number | 4 | Initial pixel block size |
| duration | number | 1.5 | Animation duration in seconds |
| delay | number | 0 | Animation start delay in seconds |
| trigger | 'viewport' \| 'mount' \| 'manual' | 'viewport' | When animation triggers |
| stagger | number | 50 | Delay between characters in ms |
| color | string | '#ffffff' | Text color |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/pixel-heading"
```

## Usage Example
```jsx
import { PixelHeading } from "@/components/ui/pixel-heading";

export function CreativeHero() {
  return (
    <section className="bg-[#0a0a0a] min-h-screen flex items-center justify-center px-6">
      <div className="text-center">
        <PixelHeading
          text="LYFEWORK"
          as="h1"
          pixelSize={6}
          duration={2}
          stagger={80}
          trigger="viewport"
          className="font-manrope font-800 text-7xl"
          color="#ffffff"
        />
        <p className="font-manrope font-400 text-white/60 mt-6 max-w-md mx-auto">
          Digital experiences that come to life.
        </p>
        <button className="mt-8 px-8 py-3 bg-gradient-to-r from-[#ff642a] to-[#ff0301] rounded-[8px] font-manrope font-700 text-white">
          See Our Work
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use Manrope 800 as the target crisp font for pixel-to-clear transition
- White text on #0a0a0a for maximum pixel visibility during animation
- Brand gradient CTA button below pixel heading for contrast
- Keep headings short (1-3 words) for best pixel animation effect
- Not ideal for GHL pages due to canvas-based pixel rendering

## Performance Notes
- Canvas renders pixel state; CSS renders final clear state
- Animation is one-shot -- no continuous rendering after completion
- IntersectionObserver triggers animation only when heading enters viewport
- Character stagger distributes rendering cost across frames
- Total animation runs for duration + (stagger * charCount) ms
