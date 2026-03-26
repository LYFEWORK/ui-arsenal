---
name: pixel-paragraph
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/pixel-paragraph
category: text-animations
tags: pixel, paragraph, text, dissolve, animation, effect
dependencies: none
variants: both
license: MIT
tier: 3
added: 2026-03-26
---

# PixelParagraph

> Pixel-dissolve paragraph text effect that assembles or dissolves body text character by character.

## When to Use
- Creative portfolio sections with distinctive body text reveals
- Storytelling pages with progressive text assembly
- Product reveal sequences with dramatic text entrance
- Artistic landing pages where typography is a design element
- Interactive reading experiences with animated text progression

## When NOT to Use
- Long-form content where animation delays reading comprehension
- SEO-critical body text that must be immediately crawlable
- Accessibility-focused pages where animated body text is disorienting
- Performance-sensitive pages with multiple paragraph animations
- Any context where users need to quickly scan body text

## Pairs Well With
- `pixel-heading` - Matching pixel aesthetic from heading through body text
- `blur-text` - Alternative text reveal for contrasting sections
- `animated-content` - Container entrance followed by pixel paragraph reveal
- `background-texture` - Noise texture supporting pixel text aesthetic

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | '' | Paragraph text content |
| pixelSize | number | 3 | Pixel block size during animation |
| duration | number | 2 | Total animation duration in seconds |
| mode | 'assemble' \| 'dissolve' | 'assemble' | Animation direction |
| trigger | 'viewport' \| 'mount' \| 'manual' | 'viewport' | When animation triggers |
| lineDelay | number | 200 | Delay between lines in ms |
| color | string | '#ffffff' | Text color |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/pixel-paragraph"
```

## Usage Example
```jsx
import { PixelParagraph } from "@/components/ui/pixel-paragraph";

export function StorySection() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-2xl mx-auto">
        <h2 className="font-manrope font-800 text-4xl text-white mb-8">
          Our Story
        </h2>
        <PixelParagraph
          text="We started Lyfework with a simple belief: every business deserves a digital presence that works as hard as they do. From clinic websites to SaaS platforms, we build experiences that convert visitors into loyal customers."
          pixelSize={2}
          duration={3}
          mode="assemble"
          trigger="viewport"
          lineDelay={150}
          className="font-manrope font-400 text-lg text-white/70 leading-relaxed"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Target font: Manrope 400 at text-lg with leading-relaxed line height
- Text color: white/70 on #0a0a0a for comfortable body text reading
- Use mode="assemble" for entrance, "dissolve" for exit transitions
- Keep paragraphs under 100 words for reasonable animation duration
- Not recommended for GHL pages -- use standard text for body content

## Performance Notes
- Canvas-based pixel rendering transitions to DOM text on completion
- Higher pixelSize reduces computation cost (fewer pixels to animate)
- lineDelay staggers rendering across frames for smooth animation
- One-shot animation -- zero ongoing cost after assembly completes
- Final state is pure DOM text (accessible, selectable, indexable)
