---
name: text-hover-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/text-hover-effect
category: text-animations
tags: text, hover, svg, mask, reveal, effect, interactive
dependencies: none
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# TextHoverEffect

> SVG-based text with a mask/reveal effect on hover, creating a gradient or image fill that appears as the cursor moves.

## When to Use
- Large display headings with interactive hover reveals
- Brand name or logo text with creative hover effects
- Hero sections with single impactful words
- Section dividers with decorative interactive text
- Portfolio headers with artistic text treatments

## When NOT to Use
- For readable body text or paragraphs
- When text needs to be selectable or copyable
- On mobile devices where hover is unavailable without fallback

## Pairs Well With
- `gradient-text` - Compare approaches for text emphasis in different sections
- `particles` - Background particles behind the hover text
- `aurora` - Aurora glow behind SVG text for atmosphere
- `lamp-effect` - Lamp accent above the interactive text

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | - | Text to render as SVG |
| className | string | - | Classes for the SVG container |

## Installation
```bash
npx aceternity-ui@latest add text-hover-effect
```

## Usage Example
```jsx
import { TextHoverEffect } from "@/components/ui/text-hover-effect";

export function BrandStatement() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-5xl mx-auto h-[300px] flex items-center justify-center">
        <TextHoverEffect text="LYFEWORK" />
      </div>
      <p className="font-[Manrope] font-400 text-neutral-400 text-center text-lg mt-4">
        Where design meets technology
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- SVG fill gradient can be set to `from-[#ff642a] to-[#ff0301]` for brand reveal color
- Use uppercase brand name "LYFEWORK" for maximum visual impact
- Container should be centered on #0a0a0a background with generous vertical padding
- Supporting text below uses Manrope 400 in neutral-400
- Zero dependencies means perfect GHL compatibility with no build requirements

## Performance Notes
- SVG text rendering is resolution-independent and crisp at any size
- Mask effect uses SVG `clipPath` or CSS `mask-image`, GPU-friendly
- Mouse tracking for reveal position is throttled to animation frame rate
- No canvas or WebGL; pure SVG + CSS for minimal resource usage
- Single instance per page recommended for best visual impact
