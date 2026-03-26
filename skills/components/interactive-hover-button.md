---
name: interactive-hover-button
source: Magic UI
source_url: https://magicui.design/docs/components/interactive-hover-button
category: components
tags: button, hover, animation, fill, interactive
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# InteractiveHoverButton

> Button with an animated fill effect on hover that slides in from the edge with a directional reveal.

## When to Use
- Primary CTA buttons on landing pages
- Navigation action buttons in hero sections
- Form submission buttons needing visual feedback
- "Get started" or "Learn more" interactive calls to action
- Portfolio project links

## When NOT to Use
- Subtle or minimal UI where hover effects distract
- Dense button groups where animation creates visual noise
- Icon-only buttons without text labels
- Disabled state buttons (animation implies interactivity)

## Pairs Well With
- `gradient-text` - Gradient heading above the CTA button
- `spotlight-card` - Button inside a spotlight-hover card
- `animated-content` - Fade in the button with the section
- `click-spark` - Add spark particles on click for extra feedback

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "Button" | Button label text |
| className | string | "" | Additional CSS classes |
| onClick | function | undefined | Click event handler |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/interactive-hover-button"
```

## Usage Example
```jsx
import { InteractiveHoverButton } from "@/components/magicui/interactive-hover-button";

export function CTASection() {
  return (
    <section className="bg-[#0a0a0a] py-24 text-center">
      <h2 className="font-manrope font-800 text-4xl text-white mb-6">
        Ready to transform your{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          clinic?
        </span>
      </h2>
      <p className="font-manrope font-400 text-white/60 mb-10 max-w-md mx-auto">
        Join 800+ healthcare professionals already using Lyfework.
      </p>
      <InteractiveHoverButton
        text="Start free trial"
        className="rounded-[8px] font-manrope font-700 text-base"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Apply `rounded-[8px]` for button border-radius convention
- Use Manrope font-700 for button text weight
- Hover fill color can be set to `#ff642a` via CSS custom properties
- Background should contrast with `#0a0a0a` — use white text on brand gradient fill
- GHL compatible — pure CSS animation with no JS framework conflicts

## Performance Notes
- CSS-only hover animation — zero JavaScript overhead
- No layout shift on hover (uses pseudo-element overlay)
- Transform and opacity animations are GPU-composited
- Works on touch devices with `:active` state fallback
