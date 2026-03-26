---
name: hole-background
source: Animate UI
source_url: https://animate-ui.com/docs/components/backgrounds/hole-background
category: backgrounds
tags: hole, portal, reveal, expanding, background, transition
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# HoleBackground

> Background with an expanding hole/portal reveal effect that opens from a center point to unveil content beneath.

## When to Use
- Page load transitions revealing hero content through an expanding portal
- Section transitions creating a dramatic unveiling effect on scroll
- Product reveal moments where content emerges through the hole
- Creative landing pages with theatrical entrance animations
- Before/after comparisons where the "after" expands from center

## When NOT to Use
- Pages requiring instant content visibility for SEO or accessibility
- Mobile layouts where the hole animation is too slow for impatient users
- Content that needs to be immediately readable without waiting for reveals
- Multiple sections on one page — the effect loses impact with repetition

## Pairs Well With
- `gradient-text` - text reveals through the expanding hole for dramatic effect
- `aurora` - aurora background revealed through the opening portal
- `particles` - particles visible through the hole, creating depth layers
- `animated-content` - content animates in after the hole fully opens

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| color | string | "#0a0a0a" | Color of the overlay with the hole |
| duration | number | 1.5 | Expansion animation duration in seconds |
| delay | number | 0 | Delay before expansion starts |
| origin | { x: string; y: string } | { x: "50%", y: "50%" } | Hole expansion origin point |
| className | string | — | Container CSS classes |
| trigger | "mount" \| "scroll" \| "click" | "mount" | When to trigger the expansion |
| easing | string | "ease-out" | CSS easing function |
| onComplete | () => void | — | Callback when expansion finishes |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/hole-background"
```

## Usage Example
```jsx
import { HoleBackground } from "@/components/ui/hole-background";

export function RevealHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      {/* Content behind the hole */}
      <div className="absolute inset-0 bg-gradient-to-br from-[#ff642a]/20 to-[#ff0301]/20 bg-[#0a0a0a]" />
      <div className="relative z-10 text-center space-y-6">
        <h1 className="font-manrope font-800 text-7xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Welcome to Lyfework
        </h1>
        <p className="font-manrope font-400 text-gray-300 text-xl max-w-2xl mx-auto">
          The future of healthcare practice management
        </p>
      </div>

      {/* Hole overlay */}
      <HoleBackground
        color="#0a0a0a"
        duration={2}
        delay={0.5}
        trigger="mount"
        className="absolute inset-0 z-20 pointer-events-none"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Overlay color: `"#0a0a0a"` matching the dark background — hole reveals content beneath
- Use `delay={0.5}` to let the page load before the reveal starts
- Content behind the hole can include brand gradient tints `from-[#ff642a]/20`
- The hole overlay should be `z-20 pointer-events-none` to avoid blocking interactions after opening
- GHL compatible — CSS clip-path animation, no DOM manipulation conflicts
- Consider `trigger="scroll"` for mid-page section reveals on scroll

## Performance Notes
- Uses CSS clip-path circle() animation — GPU-accelerated, smooth
- Single element with no child nodes — minimal DOM impact
- Animation runs once — no continuous computation
- Pointer-events disabled after opening — no interaction blocking
- Clip-path transitions are well-optimized in modern browsers
