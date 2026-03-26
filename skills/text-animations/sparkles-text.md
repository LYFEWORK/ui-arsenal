---
name: sparkles-text
source: Magic UI
source_url: https://magicui.design/docs/components/sparkles-text
category: text-animations
tags: text, sparkle, glitter, particles, magical
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# SparklesText

> Text with floating sparkle/glitter particles that twinkle around the characters.

## When to Use
- "New" or "Featured" labels with eye-catching sparkle effect
- Premium product or plan name emphasis
- Hero headline keywords that need magical emphasis
- Special offer or promotion text highlights
- Portfolio accent text for creative projects

## When NOT to Use
- Body text or long paragraphs (sparkles obscure readability)
- Professional/corporate contexts requiring restrained design
- Multiple sparkle texts on the same viewport (visual clutter)
- Dark-on-light text where sparkles have poor contrast

## Pairs Well With
- `gradient-text` - Gradient text fill combined with sparkle overlay
- `animated-content` - Reveal the sparkle text on scroll
- `neon-gradient-card` - Sparkle text heading inside a neon card
- `aurora` - Aurora background matching the sparkle magic theme

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Text content |
| className | string | "" | Additional CSS classes |
| sparklesCount | number | 10 | Number of sparkle particles |
| colors | object | {first: "#9E7AFF", second: "#FE8BBB"} | Sparkle color pair |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/sparkles-text"
```

## Usage Example
```jsx
import { SparklesText } from "@/components/magicui/sparkles-text";

export function FeatureHighlight() {
  return (
    <section className="bg-[#0a0a0a] py-24 text-center">
      <h2 className="font-manrope font-800 text-4xl text-white">
        Introducing{" "}
        <SparklesText
          colors={{ first: "#ff642a", second: "#ff0301" }}
          className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent"
        >
          AI Scheduling
        </SparklesText>
      </h2>
      <p className="font-manrope font-400 text-white/60 mt-6 max-w-md mx-auto">
        Let our AI optimize your clinic calendar for maximum efficiency.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set sparkle `colors` to `{ first: "#ff642a", second: "#ff0301" }` for brand consistency
- Combine with `bg-clip-text text-transparent` gradient for full brand treatment
- Use Manrope font-800 at large display sizes for sparkle text
- Limit to 1-2 words of sparkle text per heading
- GHL compatible — CSS animations with absolutely positioned sparkle elements

## Performance Notes
- Sparkle particles use CSS `@keyframes` — lightweight per particle
- Default 10 sparkles is optimal; exceeding 20 adds unnecessary DOM nodes
- Particles are absolutely positioned — no layout shift
- Animation runs continuously — consider intersection observer for visibility
- No canvas or WebGL — pure DOM elements with CSS transforms
