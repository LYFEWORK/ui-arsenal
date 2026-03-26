---
name: text-animate
source: Magic UI
source_url: https://magicui.design/docs/components/text-animate
category: text-animations
tags: text, animate, entrance, character, word
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# TextAnimate

> Character-by-character or word-by-word entrance animation wrapper for text content.

## When to Use
- Hero headline entrance animations
- Section heading reveals on scroll
- Staggered text appearance for storytelling sections
- Loading state text with sequential character reveals
- Any text needing a polished entrance animation

## When NOT to Use
- Large blocks of body text (too slow and distracting)
- Text that needs to be immediately readable (e.g., warnings)
- When blur-text from the arsenal already covers the animation need
- Real-time updating text that re-animates on every change

## Pairs Well With
- `animated-content` - Container-level reveal before text animates in
- `gradient-text` - Gradient text that animates character by character
- `particles` - Particle background behind the animated heading
- `aurora` - Aurora effect behind the revealed text

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | string | required | Text content to animate |
| type | "text" \| "word" \| "character" \| "line" | "text" | Animation granularity |
| animation | "blurIn" \| "fadeIn" \| "slideUp" \| "slideDown" \| "slideLeft" \| "slideRight" \| "scaleUp" | "fadeIn" | Animation variant |
| delay | number | 0 | Delay before animation starts |
| duration | number | 0.3 | Duration per element |
| staggerChildren | number | 0.05 | Delay between each child element |
| className | string | "" | Additional CSS classes |
| by | "character" \| "word" \| "line" | "word" | Split text by unit |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/text-animate"
```

## Usage Example
```jsx
import { TextAnimate } from "@/components/magicui/text-animate";

export function HeroSection() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <TextAnimate
        animation="blurIn"
        by="word"
        className="font-manrope font-800 text-5xl text-white"
      >
        Automate your clinic workflow
      </TextAnimate>
      <TextAnimate
        animation="fadeIn"
        by="word"
        delay={0.5}
        className="font-manrope font-400 text-white/60 text-xl mt-6 max-w-lg mx-auto"
      >
        Scheduling, patient engagement, and analytics in one platform.
      </TextAnimate>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use `blurIn` animation for hero headlines — matches `blur-text` aesthetic
- Apply Manrope font-800 for headings, font-400 for subheadings
- Stagger heading and subheading with `delay` offset (e.g., 0 and 0.5)
- Works on `#0a0a0a` backgrounds with white text
- GHL compatible — Framer Motion renders standard DOM elements

## Performance Notes
- Each character/word is a separate `<span>` — large texts create many DOM nodes
- Use `by="word"` for paragraphs (fewer nodes than `by="character"`)
- Framer Motion stagger is efficient — uses shared animation timeline
- Animation triggers once — no continuous loop or re-rendering
- Consider viewport intersection trigger for below-fold content
