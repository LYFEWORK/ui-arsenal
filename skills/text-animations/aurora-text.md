---
name: aurora-text
source: Magic UI
source_url: https://magicui.design/docs/components/aurora-text
category: text-animations
tags: text, aurora, gradient, color, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# AuroraText

> Text with an animated aurora/gradient color effect that smoothly shifts through luminous hues.

## When to Use
- Hero section headline with eye-catching color animation
- Product name or brand name emphasis
- Feature titles that need premium visual treatment
- Landing page key phrases ("AI-powered", "Next-gen")
- Section headings requiring visual distinction

## When NOT to Use
- Body text or paragraphs (too distracting for long reads)
- Multiple aurora texts competing on the same page
- When the gradient-text component already achieves the desired effect
- Accessibility-critical text where color carries meaning

## Pairs Well With
- `animated-content` - Reveal the aurora text on scroll
- `particles` - Particle background behind the aurora heading
- `aurora` - Aurora background matching the text effect
- `spotlight-card` - Aurora text as a card heading

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Text content to apply aurora effect |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/aurora-text"
```

## Usage Example
```jsx
import { AuroraText } from "@/components/magicui/aurora-text";

export function HeroHeadline() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <h1 className="font-manrope font-800 text-6xl text-white">
        The future of{" "}
        <AuroraText>clinic management</AuroraText>
      </h1>
      <p className="font-manrope font-400 text-white/60 text-xl mt-6 max-w-xl mx-auto">
        AI-powered scheduling, patient engagement, and practice growth — all in one platform.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Customize aurora colors to include `#ff642a` and `#ff0301` in the gradient cycle
- Use on `#0a0a0a` dark backgrounds for maximum color vibrancy
- Apply with Manrope font-800 at large display sizes (text-5xl+)
- Use sparingly — one aurora text per section at most
- GHL compatible — CSS gradient animation with Framer Motion, no Web Components

## Performance Notes
- Framer Motion animates CSS `background-position` — GPU composited
- Color shifting uses smooth interpolation, not discrete steps
- Single text element has minimal performance impact
- Animation runs continuously — consider `prefers-reduced-motion`
- No DOM manipulation — gradient is applied via `background-clip: text`
