---
name: colourful-text
source: Aceternity UI
source_url: https://ui.aceternity.com/components/colourful-text
category: text-animations
tags: text, color, rainbow, per-character, animation, gradient, chromatic
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# ColourfulText

> Text with per-character rainbow color animation that cycles through vibrant hues, creating eye-catching chromatic effects.

## When to Use
- Hero headlines that need maximum visual impact
- Feature section headers with playful energy
- Brand name or product name emphasis
- Creative portfolio or agency landing pages
- Celebration or launch announcement text

## When NOT to Use
- For body text or long paragraphs (distracting and hard to read)
- On professional/corporate pages where restraint is needed
- When brand colors must remain consistent throughout

## Pairs Well With
- `gradient-text` - Use alongside gradient text for variety in emphasis styles
- `blur-text` - Blur entrance before color animation starts
- `animated-content` - Section entrance before text colors activate
- `aurora` - Aurora background complementing the chromatic text

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | - | Text to apply the color animation to |
| className | string | - | Additional classes for the text |
| colors | array | rainbow | Custom color array for the animation |

## Installation
```bash
npx aceternity-ui@latest add colourful-text
```

## Usage Example
```jsx
import { ColourfulText } from "@/components/ui/colourful-text";

export function LaunchHero() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-6 text-center">
      <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
        Build Something{" "}
        <ColourfulText text="Beautiful" colors={["#ff642a", "#ff4500", "#ff0301", "#ff6b35", "#ff8c42"]} />
      </h1>
      <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6 max-w-2xl mx-auto">
        AI-powered web design that turns visitors into patients and users into customers.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Override default rainbow with brand colors: `["#ff642a", "#ff4500", "#ff0301", "#ff6b35", "#ff8c42"]`
- Use Manrope 800 for colorful text headings at 5xl-7xl scale
- Best on #0a0a0a dark backgrounds where colors pop against the dark surface
- Limit to 1-2 words for maximum impact; full sentences lose readability
- GHL compatible as animation uses standard CSS color transitions

## Performance Notes
- Per-character color cycling uses individual `span` elements with staggered CSS animations
- CPU cost scales linearly with character count; keep text short (1-3 words ideal)
- Color transitions are GPU-composited via `color` property animation
- Framer Motion handles stagger timing efficiently with shared animation config
- Consider `will-change: color` on character spans for smoother rendering
