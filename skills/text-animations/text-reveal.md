---
name: text-reveal
source: Magic UI
source_url: https://magicui.design/docs/components/text-reveal
category: text-animations
tags: text, reveal, scroll, mask, progressive
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# TextReveal

> Text revealed progressively by scroll position, where each word highlights as the user scrolls through.

## When to Use
- Long-form storytelling sections on landing pages
- Manifesto or mission statement reveals
- Product philosophy or "why we built this" sections
- Immersive scrollytelling experiences
- Brand story sections with dramatic pacing

## When NOT to Use
- Content that users need to read quickly or scan
- Mobile experiences where scroll-tied animation feels janky
- Short text (fewer than 10 words — not enough scroll distance)
- Pages with heavy scroll-based animations already

## Pairs Well With
- `particles` - Particle background behind the revealing text
- `aurora` - Aurora gradient visible through the reveal mask
- `animated-content` - Container entrance before scroll reveal begins
- `gradient-text` - Key words in gradient after reveal

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | required | Full text content to reveal |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/text-reveal"
```

## Usage Example
```jsx
import { TextReveal } from "@/components/magicui/text-reveal";

export function MissionSection() {
  return (
    <section className="bg-[#0a0a0a]">
      <div className="mx-auto max-w-4xl">
        <TextReveal
          text="We believe every clinic deserves the tools to deliver exceptional patient experiences. Lyfework exists to make that possible — with AI-powered scheduling, seamless communication, and insights that drive growth."
          className="font-manrope font-700 text-3xl"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use Manrope font-700 at text-3xl for the reveal text
- Revealed words appear white, unrevealed remain `text-white/20` on `#0a0a0a`
- Content should reflect the Lyfework mission or product value proposition
- Keep text to 2-3 sentences for optimal scroll pacing
- GHL compatible — Framer Motion scroll-linked animation, standard DOM rendering

## Performance Notes
- Framer Motion `useScroll` and `useTransform` — optimized scroll listener
- Each word opacity is computed from scroll progress — efficient interpolation
- No requestAnimationFrame loop — piggybacks on scroll events
- Container height determines scroll distance — adjust for comfortable reading speed
- Consider `will-change: opacity` on individual word spans for paint optimization
