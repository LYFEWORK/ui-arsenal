---
name: layout-text-flip
source: Aceternity UI
source_url: https://ui.aceternity.com/components/layout-text-flip
category: text-animations
tags: text, flip, layout, transition, animation, swap, full-width
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# LayoutTextFlip

> Full layout text flip transition that animates the entire text block with a page-turning or card-flipping motion.

## When to Use
- Section headers that transition between different themes or topics
- Full-width text statements with dramatic flip reveals
- Storytelling sections where each flip reveals a new chapter
- Landing page above-fold with rotating full-sentence taglines
- Interactive about sections with flipping mission/vision statements

## When NOT to Use
- For single-word swaps (use container-text-flip instead)
- When continuous readability is more important than animation
- On low-powered devices where 3D transforms may stutter

## Pairs Well With
- `gradient-text` - Apply gradient to the active text state
- `lamp-effect` - Lamp glow behind the flipping text section
- `aurora` - Background aurora enhancing the flip transitions
- `animated-content` - Surrounding content animates with each flip

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| words | array | - | Array of text strings for the flip cycle |
| duration | number | 4000 | Milliseconds between flips |
| className | string | - | Classes for the container |

## Installation
```bash
npx aceternity-ui@latest add layout-text-flip
```

## Usage Example
```jsx
import { LayoutTextFlip } from "@/components/ui/layout-text-flip";

export function MissionStatement() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-6 flex items-center justify-center min-h-[50vh]">
      <LayoutTextFlip
        words={[
          "We design for healthcare.",
          "We build for performance.",
          "We optimize for growth.",
        ]}
        className="font-[Manrope] font-800 text-4xl md:text-6xl text-white text-center"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Text uses Manrope 800 at 4xl-6xl for impactful full-width statements
- Background #0a0a0a with white text for maximum contrast during flips
- Key words within each statement can be wrapped in gradient spans
- Flip timing of 4000ms allows comfortable reading of full sentences
- Works in GHL contexts; ensure section has sufficient height for flip animation

## Performance Notes
- Full layout flip uses CSS `perspective` and `rotateX/Y`, GPU-composited
- Only the current and next text are rendered in DOM at any time
- 3D transform creates a new stacking context, isolated from page layout
- Animation runs at 60fps on modern hardware; may drop frames on older mobile
- Uses `AnimatePresence` for clean mount/unmount during transitions
