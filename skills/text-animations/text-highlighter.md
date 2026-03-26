---
name: text-highlighter
source: Magic UI
source_url: https://magicui.design/docs/components/text-highlighter
category: text-animations
tags: text, highlight, marker, underline, emphasis
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# TextHighlighter

> Text with an animated highlight/marker underline effect that draws across the text on scroll or mount.

## When to Use
- Emphasizing key phrases in feature descriptions
- Highlighting important terms in educational content
- Drawing attention to value propositions in sales copy
- Annotating key words in testimonials or quotes
- Interactive reading highlights on documentation pages

## When NOT to Use
- Full paragraphs where highlighting loses its emphasis
- When standard bold or gradient-text provides sufficient emphasis
- Multiple highlights competing in the same sentence
- Light backgrounds where yellow highlight has poor contrast

## Pairs Well With
- `animated-content` - Trigger highlight animation on scroll
- `blur-text` - Blur-reveal text before the highlight animates
- `gradient-text` - Gradient text paired with highlight underline
- `spotlight-card` - Highlighted text inside a spotlight card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Text content to highlight |
| className | string | "" | Additional CSS classes |
| highlightColor | string | "#fde047" | Color of the highlight marker |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/text-highlighter"
```

## Usage Example
```jsx
import { TextHighlighter } from "@/components/magicui/text-highlighter";

export function ValuePropSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <div className="mx-auto max-w-3xl text-center">
        <h2 className="font-manrope font-800 text-3xl text-white leading-relaxed">
          Clinics using Lyfework see a{" "}
          <TextHighlighter highlightColor="#ff642a40">
            40% reduction in no-shows
          </TextHighlighter>{" "}
          within the first month.
        </h2>
        <p className="font-manrope font-400 text-white/60 mt-6">
          Our AI scheduling engine optimizes every appointment slot.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `highlightColor="#ff642a40"` (brand orange at 25% opacity) for subtle brand highlighting
- Use Manrope font-800 for the highlighted heading text
- Highlight the most impactful phrase only — typically 3-6 words
- On `#0a0a0a` backgrounds, use semi-transparent highlight colors for best contrast
- GHL compatible — CSS background/decoration animation, no Web Components

## Performance Notes
- CSS animation for the highlight sweep — GPU composited
- Single highlight per text block has negligible performance cost
- No JavaScript event loops or animation frames
- Intersection Observer trigger is recommended for scroll-based activation
- Highlight is a CSS pseudo-element — no additional DOM nodes
