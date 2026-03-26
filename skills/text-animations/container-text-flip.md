---
name: container-text-flip
source: Aceternity UI
source_url: https://ui.aceternity.com/components/container-text-flip
category: text-animations
tags: text, flip, rotate, container, animation, transition, swap
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# ContainerTextFlip

> Text that flips or rotates within a fixed container, cycling through multiple words or phrases with smooth 3D transitions.

## When to Use
- Hero headlines with rotating value propositions
- Feature sections cycling through benefit keywords
- CTA areas with rotating action verbs or outcomes
- Landing page headers showing multiple service offerings
- Tagline sections that showcase versatility

## When NOT to Use
- When the changing word creates confusing sentence grammar
- For critical information that must be readable at all times
- On pages where motion reduction preferences should be honored

## Pairs Well With
- `gradient-text` - Apply gradient to the flipping text for emphasis
- `hero-highlight` - Place text flip inside a hero highlight section
- `animated-content` - Surrounding content fades in while text flips
- `blur-text` - Static text uses blur entrance alongside the flip

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| words | array | - | Array of strings to cycle through |
| duration | number | 3000 | Milliseconds between word flips |
| className | string | - | Classes for the text element |

## Installation
```bash
npx aceternity-ui@latest add container-text-flip
```

## Usage Example
```jsx
import { ContainerTextFlip } from "@/components/ui/container-text-flip";

export function HeroTagline() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-6 text-center">
      <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white">
        We Build Websites That{" "}
        <ContainerTextFlip
          words={["Convert", "Scale", "Impress", "Perform"]}
          className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent"
        />
      </h1>
      <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6">
        Lyfework: Where AI meets design for clinic and SaaS growth.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Flipping text styled with `from-[#ff642a] to-[#ff0301]` gradient for brand emphasis
- Container width should accommodate the longest word to prevent layout shifts
- Manrope 800 for headline text at 5xl-7xl scale on #0a0a0a background
- Flip duration of 3000ms gives comfortable reading time between transitions
- GHL compatible; flip animation uses standard CSS transforms

## Performance Notes
- Flip animation uses CSS `rotateX` transform, GPU-composited
- Only two text elements exist at any time (current and next), minimal DOM overhead
- Animation is a single transition per flip, no continuous frame loop
- `AnimatePresence` handles mount/unmount of text elements efficiently
- Consider pausing animation when component is out of viewport
