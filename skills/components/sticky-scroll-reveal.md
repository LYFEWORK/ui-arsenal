---
name: sticky-scroll-reveal
source: Aceternity UI
source_url: https://ui.aceternity.com/components/sticky-scroll-reveal
category: components
tags: sticky, scroll, reveal, side-panel, content, features, storytelling
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# StickyScrollReveal

> Pinned content panel with a scrolling side panel that reveals different sections as the user scrolls through.

## When to Use
- Feature walkthrough sections with sticky headline and scrolling details
- Process or workflow explanations with step-by-step reveals
- Product benefit showcases with corresponding visuals
- Case study narratives with sticky stats and scrolling story
- Service descriptions with pinned imagery and scrolling text

## When NOT to Use
- On mobile layouts where side-by-side pinning breaks
- For short content that does not benefit from scroll-driven reveals
- When content sections are independent and do not follow a narrative

## Pairs Well With
- `gradient-text` - Gradient headings in the pinned content area
- `count-up` - Animated statistics in the sticky panel
- `blur-text` - Text entrance animations in the scrolling panel
- `animated-content` - Stagger content appearance in each reveal section

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| content | array | - | Array of { title, description, content } sections |
| contentClassName | string | - | Classes for the scrolling content panel |

## Installation
```bash
npx aceternity-ui@latest add sticky-scroll-reveal
```

## Usage Example
```jsx
import { StickyScroll } from "@/components/ui/sticky-scroll-reveal";

const processSteps = [
  {
    title: "Discovery & Strategy",
    description: "We analyze your clinic's needs, competitors, and patient journey to build a data-driven strategy.",
    content: (
      <div className="lyf-glass rounded-[12px] p-8 h-full flex items-center justify-center">
        <img src="/process/discovery.webp" alt="Discovery" className="rounded-[8px]" />
      </div>
    ),
  },
  {
    title: "Design & Prototype",
    description: "High-fidelity designs in Figma with Manrope typography and your brand palette. Full client review.",
    content: (
      <div className="lyf-glass rounded-[12px] p-8 h-full flex items-center justify-center">
        <img src="/process/design.webp" alt="Design" className="rounded-[8px]" />
      </div>
    ),
  },
  {
    title: "Build & Integrate",
    description: "Next.js development with GHL CRM integration, AI chatbots, and HIPAA-compliant forms.",
    content: (
      <div className="lyf-glass rounded-[12px] p-8 h-full flex items-center justify-center">
        <img src="/process/build.webp" alt="Build" className="rounded-[8px]" />
      </div>
    ),
  },
  {
    title: "Launch & Optimize",
    description: "Performance monitoring, A/B testing, and continuous optimization for maximum conversions.",
    content: (
      <div className="lyf-glass rounded-[12px] p-8 h-full flex items-center justify-center">
        <img src="/process/launch.webp" alt="Launch" className="rounded-[8px]" />
      </div>
    ),
  },
];

export function ProcessSection() {
  return (
    <section className="bg-[#0a0a0a]">
      <StickyScroll content={processSteps} />
    </section>
  );
}
```

## Lyfework Customization Notes
- Sticky content panel uses `lyf-glass` with `rounded-[12px]` for glass card effect
- Section titles use Manrope 700 in white, descriptions use Manrope 400 in neutral-400
- Process images wrapped in `rounded-[8px]` containers
- Background #0a0a0a with the gradient accent appearing in active section indicators
- GHL iframe scrolling may conflict with sticky positioning; test scroll container context

## Performance Notes
- Uses `position: sticky` for the pinned panel, CSS-driven with zero JavaScript overhead
- Scroll detection for section switching uses `IntersectionObserver`, highly efficient
- Content panels render all sections in DOM but only the active one is visually emphasized
- Images in inactive sections should use `loading="lazy"` for deferred loading
- Smooth transitions between sections use opacity/transform, GPU-composited
