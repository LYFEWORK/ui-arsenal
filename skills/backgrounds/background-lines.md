---
name: background-lines
source: Aceternity UI
source_url: https://ui.aceternity.com/components/background-lines
category: backgrounds
tags: lines, background, minimal, vertical, pattern, subtle, clean
dependencies: none
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# BackgroundLines

> Minimal vertical lines background pattern that adds subtle texture and depth to sections without overwhelming content.

## When to Use
- Clean hero sections that need subtle visual texture
- Background for pricing or feature comparison grids
- Minimal section dividers with linear pattern depth
- Professional landing pages where restraint is the aesthetic
- Any section needing structured background without distraction

## When NOT to Use
- When a completely flat background is preferred
- On sections with dense grid layouts where lines create visual noise
- When other line-based elements (timeline, tracing beam) already exist

## Pairs Well With
- `gradient-text` - Gradient headings over the lined background
- `animated-content` - Content animation on the structured background
- `spotlight-card` - Cards floating over the line pattern
- `floating-navbar` - Clean navbar on lined hero background

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered over the lines |
| className | string | - | Classes for the container |
| lineColor | string | "rgba(255,255,255,0.05)" | Color of the background lines |
| lineSpacing | number | 80 | Spacing between lines in pixels |

## Installation
```bash
npx aceternity-ui@latest add background-lines
```

## Usage Example
```jsx
import { BackgroundLines } from "@/components/ui/background-lines";

export function PricingSection() {
  return (
    <BackgroundLines className="bg-[#0a0a0a] py-24 px-6">
      <div className="max-w-6xl mx-auto text-center relative z-10">
        <h2 className="font-[Manrope] font-800 text-4xl text-white mb-4">
          Simple, Transparent{" "}
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">Pricing</span>
        </h2>
        <p className="font-[Manrope] font-400 text-neutral-400 text-lg mb-16">
          No hidden fees. No long-term contracts. Just results.
        </p>
        {/* Pricing cards go here */}
      </div>
    </BackgroundLines>
  );
}
```

## Lyfework Customization Notes
- Line color `rgba(255,255,255,0.05)` for barely-visible structure on #0a0a0a
- Increase to `rgba(255,100,42,0.03)` for subtle brand-tinted lines
- Content needs `relative z-10` to sit above the line pattern
- Manrope 800 for headings, 400 for subtext, consistent with design system
- Zero dependencies; instant GHL compatibility with pure CSS rendering

## Performance Notes
- Pure CSS implementation using `repeating-linear-gradient`, zero JavaScript
- Renders as a single background property, no additional DOM elements
- Zero GPU overhead beyond standard background painting
- Works on all browsers including Safari without any fallback needed
- Can be combined with other background effects without performance conflict
