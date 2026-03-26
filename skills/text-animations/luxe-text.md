---
name: luxe-text
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-text
category: text-animations
tags: text, gradient, reveal, animation, typography, heading
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LuxeText

> Elegant text component with animated gradient coloring and character-by-character reveal animation.

## When to Use
- Hero section headings that need dramatic entrance animations
- Section titles where gradient text reinforces brand identity
- Feature highlights where animated text draws the eye
- About page statements with cinematic reveal effects
- Landing page taglines that need to feel premium and intentional

## When NOT to Use
- Body text or paragraphs — animation on long text is distracting
- Navigation labels or UI text that should be instantly readable
- Content-heavy pages where multiple animated texts compete
- SEO-critical headings where rendering delay impacts crawlers

## Pairs Well With
- `blur-text` - luxe-text for gradient color, blur-text for reveal mechanics
- `aurora` - gradient text over aurora background creates a cohesive color story
- `spotlight-card` - animated text heading inside a spotlight card
- `particles` - character-reveal text amid floating particles for immersive heroes

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | string | — | Text content to animate |
| className | string | — | Additional CSS classes |
| gradient | string | — | CSS gradient value for text coloring |
| animation | "reveal" \| "fade" \| "slide" | "reveal" | Animation style |
| delay | number | 0 | Animation start delay in seconds |
| duration | number | 0.8 | Total animation duration in seconds |
| stagger | number | 0.03 | Delay between each character |
| as | ElementType | "span" | Render as different element |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-text"
```

## Usage Example
```jsx
import { LuxeText } from "@/components/ui/luxe-text";

export function HeroHeading() {
  return (
    <section className="min-h-[70vh] flex items-center justify-center bg-[#0a0a0a]">
      <div className="text-center space-y-6">
        <LuxeText
          as="h1"
          className="font-manrope font-800 text-6xl md:text-7xl"
          gradient="linear-gradient(90deg, #ff642a, #ff0301)"
          animation="reveal"
          stagger={0.02}
        >
          Transform Your Practice
        </LuxeText>
        <p className="font-manrope font-400 text-gray-400 text-xl max-w-2xl mx-auto">
          AI-powered tools that help healthcare professionals grow their patient base.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `gradient` to `"linear-gradient(90deg, #ff642a, #ff0301)"` for brand gradient text
- Use `font-manrope font-800` for hero headings, `font-700` for section titles
- On `#0a0a0a` backgrounds, the gradient text pops with maximum contrast
- Consider `delay={0.3}` to let the page settle before text reveals
- GHL compatible — text renders as standard elements after animation completes
- Combine with a static subtitle in `font-manrope font-400 text-gray-400` below

## Performance Notes
- Character-level animation creates individual span elements — keep text short (< 50 chars)
- Uses framer-motion stagger for efficient batched animations
- After animation completes, component can be set to static to reduce DOM nodes
- Gradient is applied via CSS `background-clip: text` — GPU-accelerated
- Intersection Observer can trigger animation only when in viewport
