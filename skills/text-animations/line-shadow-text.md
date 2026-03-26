---
name: line-shadow-text
source: Magic UI
source_url: https://magicui.design/docs/components/line-shadow-text
category: text-animations
tags: text, shadow, line, depth, elegant
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# LineShadowText

> Text with a cascading line shadow depth effect creating an elegant layered appearance.

## When to Use
- Hero section display headlines needing visual depth
- Portfolio or agency site bold headings
- Product name emphasis with 3D shadow feel
- Section dividers with impactful typography
- Dark-themed landing page hero text

## When NOT to Use
- Small text sizes where shadow lines become illegible
- Light backgrounds where shadow contrast is poor
- Body text or long passages
- When blur-text or gradient-text already provides sufficient emphasis

## Pairs Well With
- `aurora` - Aurora background behind the shadowed heading
- `animated-content` - Reveal the shadow text on scroll
- `particles` - Particle field behind the text section
- `gradient-text` - Combine gradient fill with line shadow effect

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Text content |
| shadowColor | string | "currentColor" | Color of the shadow lines |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/line-shadow-text"
```

## Usage Example
```jsx
import { LineShadowText } from "@/components/magicui/line-shadow-text";

export function AgencyHero() {
  return (
    <section className="bg-[#0a0a0a] py-32 text-center">
      <h1 className="font-manrope font-800 text-7xl text-white">
        We build{" "}
        <LineShadowText shadowColor="#ff642a">
          digital experiences
        </LineShadowText>
      </h1>
      <p className="font-manrope font-400 text-white/60 text-xl mt-8 max-w-lg mx-auto">
        Custom SaaS platforms, clinic portals, and AI-powered products.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `shadowColor="#ff642a"` to use brand orange for the shadow lines
- Use Manrope font-800 at text-6xl or larger for best visual impact
- Dark backgrounds (`#0a0a0a`) are essential for shadow visibility
- Limit to one line-shadow text instance per section
- GHL compatible — CSS text-shadow rendering, no JS dependencies

## Performance Notes
- Pure CSS `text-shadow` — rendered by the browser compositor
- Multiple shadow layers have minimal performance impact at large sizes
- No JavaScript animation or event listeners
- Static rendering — no continuous animation loop
- Text remains selectable and accessible to screen readers
