---
name: lamp-effect
source: Aceternity UI
source_url: https://ui.aceternity.com/components/lamp-effect
category: components
tags: lamp, glow, header, section, accent, linear, dramatic
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# LampEffect

> Linear-style glowing lamp accent for section headers, creating a dramatic top-down light beam that illuminates content.

## When to Use
- Section headers that need dramatic visual separation
- Feature announcement sections with spotlight emphasis
- Pricing page headers with premium glow treatment
- Portfolio section dividers with cinematic flair
- CTA sections that need to command attention

## When NOT to Use
- For multiple consecutive sections (overuse dilutes impact)
- On light-themed pages where the glow effect is invisible
- When the section content is lightweight or secondary

## Pairs Well With
- `gradient-text` - Gradient headline text under the lamp glow
- `blur-text` - Text entrance animation synchronized with lamp reveal
- `particles` - Subtle particles floating in the lamp light
- `animated-content` - Stagger content appearance after lamp opens

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Content rendered under the lamp effect |
| className | string | - | Classes for the lamp container |

## Installation
```bash
npx aceternity-ui@latest add lamp-effect
```

## Usage Example
```jsx
import { LampContainer } from "@/components/ui/lamp";

export function FeatureSection() {
  return (
    <LampContainer className="bg-[#0a0a0a]">
      <h2 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white text-center mt-8">
        AI-Powered{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          Growth Engine
        </span>
      </h2>
      <p className="font-[Manrope] font-400 text-neutral-400 text-xl text-center mt-6 max-w-2xl mx-auto">
        Automate patient acquisition, scheduling, and follow-ups with our intelligent platform.
      </p>
      <button className="mt-10 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px]">
        See How It Works
      </button>
    </LampContainer>
  );
}
```

## Lyfework Customization Notes
- Lamp glow color can be adjusted; use `#ff642a` or `#ff0301` for brand-colored light
- Background must be #0a0a0a or very dark for the lamp effect to be visible
- Manrope 800 at 5xl-7xl for section headlines, 400 for supporting text
- CTA buttons use `rounded-[8px]` with gradient background
- Lamp beam width can be controlled via CSS; wider beam for full-width sections

## Performance Notes
- Lamp animation uses framer-motion spring for the beam expansion, runs once on mount
- Glow effect is a CSS gradient with blur filter, GPU-composited
- Single animation cycle means no ongoing CPU cost after initial render
- Minimal DOM elements: gradient div + blur div + content container
- Safe to use once per page; using 2+ lamp sections may cause visual fatigue
