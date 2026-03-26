---
name: morphing-text
source: Magic UI
source_url: https://magicui.design/docs/components/morphing-text
category: text-animations
tags: text, morph, transition, words, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# MorphingText

> Text that smoothly morphs between different words or phrases with fluid letter transitions.

## When to Use
- Hero headlines cycling through value propositions
- Dynamic taglines ("We build _websites_ / _apps_ / _brands_")
- Feature sections rotating through capability descriptions
- Product showcases cycling through use cases
- Landing page headers with A/B tested phrases

## When NOT to Use
- Static content that should remain fixed for SEO
- When the cycling speed makes text unreadable
- Long sentences that morph into other long sentences (use text-animate instead)
- Critical information that users must read completely

## Pairs Well With
- `aurora` - Aurora background behind the morphing headline
- `particles` - Particle effects around the morphing text
- `animated-content` - Reveal section before morphing begins
- `gradient-text` - Static gradient text paired with morphing words

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| texts | string[] | required | Array of words/phrases to morph between |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/morphing-text"
```

## Usage Example
```jsx
import { MorphingText } from "@/components/magicui/morphing-text";

export function HeroCyclingHeadline() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <h1 className="font-manrope font-800 text-5xl text-white">
        Lyfework helps you{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          <MorphingText texts={["schedule", "engage", "retain", "grow"]} />
        </span>
      </h1>
      <p className="font-manrope font-400 text-white/60 text-lg mt-8 max-w-lg mx-auto">
        The all-in-one clinic management platform designed for modern healthcare.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Wrap in a gradient span for brand-colored morphing text
- Use Manrope font-800 for the morphing display text
- Keep word list short (3-5 items) and similar in character length
- Morphing words should all be relevant to the Lyfework value proposition
- GHL compatible — Framer Motion renders standard DOM, no Shadow DOM

## Performance Notes
- Framer Motion handles letter-by-letter transitions — moderate CPU usage
- SVG filter morphing is more expensive than simple opacity crossfades
- Limit to one morphing text instance per viewport
- Animation is continuous — consider pausing when not in viewport
- Text remains accessible via aria-label with all options listed
