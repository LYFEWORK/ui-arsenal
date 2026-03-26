---
name: google-gemini-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/google-gemini-effect
category: animations
tags: gemini, svg, beam, hero, animated, google, premium, scroll
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 3
added: 2026-03-25
---

# GoogleGeminiEffect

> Google Gemini-style animated SVG beam hero with flowing, undulating lines that respond to scroll position.

## When to Use
- Premium AI product launch hero sections
- Technology-forward landing pages with cinematic intros
- SaaS product pages showcasing AI or ML capabilities
- Agency "innovation" or "technology" section headers
- Full-viewport animated hero sections for maximum impact

## When NOT to Use
- On pages where quick content access is more important than animation
- For performance-constrained environments or low-end devices
- When the brand aesthetic is minimal or restrained
- On pages with other heavy scroll-based animations

## Pairs Well With
- `gradient-text` - Animated headline text over the Gemini beams
- `blur-text` - Text entrance animation above the SVG beams
- `particles` - Complementary particles alongside beam animation
- `animated-content` - Content reveals as beams animate on scroll

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| pathLengths | array | - | Motion values for path animation progress |
| title | string | - | Main headline text |
| description | string | - | Supporting description text |
| className | string | - | Classes for the container |

## Installation
```bash
npx aceternity-ui@latest add google-gemini-effect
```

## Usage Example
```jsx
import { GoogleGeminiEffect } from "@/components/ui/google-gemini-effect";
import { useScroll, useTransform } from "framer-motion";
import { useRef } from "react";

export function AIHero() {
  const ref = useRef(null);
  const { scrollYProgress } = useScroll({ target: ref, offset: ["start start", "end start"] });
  const pathLengthFirst = useTransform(scrollYProgress, [0, 0.8], [0.2, 1.2]);
  const pathLengthSecond = useTransform(scrollYProgress, [0, 0.8], [0.15, 1.2]);
  const pathLengthThird = useTransform(scrollYProgress, [0, 0.8], [0.1, 1.2]);

  return (
    <section ref={ref} className="bg-[#0a0a0a] relative h-[300vh]">
      <div className="sticky top-0 h-screen overflow-hidden">
        <GoogleGeminiEffect
          pathLengths={[pathLengthFirst, pathLengthSecond, pathLengthThird]}
          title="AI-Powered Design"
          description="The future of clinic and SaaS web experiences, powered by Lyfework."
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- SVG beam colors can be customized to include `#ff642a` and `#ff0301` in the gradient
- Title and description use Manrope 800 and 400 respectively
- Background must be #0a0a0a for beam visibility against dark surface
- Section uses sticky positioning with 300vh height for scroll-driven animation
- In GHL, test scroll container behavior; sticky positioning needs correct scroll context

## Performance Notes
- SVG path animations with `stroke-dasharray` are GPU-composited
- Multiple animated paths (3-5) run simultaneously; keep total path count under 6
- Scroll-driven animation uses `useTransform` for efficient per-frame updates
- Section height of 300vh creates extended scroll area; balance with content needs
- Tier 3 complexity; use only as the primary hero, not in secondary sections
