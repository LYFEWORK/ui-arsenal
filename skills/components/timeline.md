---
name: timeline
source: Aceternity UI
source_url: https://ui.aceternity.com/components/timeline
category: components
tags: timeline, scroll, beam, history, process, sticky, narrative
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# Timeline

> Vertical timeline with sticky headers and an animated connecting beam that traces scroll progress through content sections.

## When to Use
- Company history or milestones sections
- Project process walkthroughs (discovery, design, build, launch)
- Product roadmap or changelog displays
- Career journey or resume timeline presentations
- Event schedules or upcoming feature releases

## When NOT to Use
- For fewer than 3 timeline entries (too sparse for scroll animation)
- When timeline content is very short and does not warrant scroll tracking
- On pages where vertical space is at a premium

## Pairs Well With
- `gradient-text` - Gradient year or milestone labels
- `count-up` - Animated stats within timeline entries
- `animated-content` - Content entrance as each timeline node activates
- `tracing-beam` - Reinforce the timeline beam with a tracing line

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| data | array | - | Array of { title, content } timeline entries |
| className | string | - | Classes for the timeline container |

## Installation
```bash
npx aceternity-ui@latest add timeline
```

## Usage Example
```jsx
import { Timeline } from "@/components/ui/timeline";

const milestones = [
  {
    title: "2024",
    content: (
      <div>
        <h3 className="font-[Manrope] font-700 text-xl text-white mb-3">Founded Lyfework</h3>
        <p className="font-[Manrope] font-400 text-neutral-400">
          Launched with a mission to bring AI-powered web design to healthcare and SaaS companies.
        </p>
      </div>
    ),
  },
  {
    title: "2025",
    content: (
      <div>
        <h3 className="font-[Manrope] font-700 text-xl text-white mb-3">100+ Projects Delivered</h3>
        <p className="font-[Manrope] font-400 text-neutral-400">
          Scaled operations with GHL integration expertise and AI chatbot deployments for clinics.
        </p>
      </div>
    ),
  },
  {
    title: "2026",
    content: (
      <div>
        <h3 className="font-[Manrope] font-700 text-xl text-white mb-3">AI-First Platform Launch</h3>
        <p className="font-[Manrope] font-400 text-neutral-400">
          Released our proprietary design system and component arsenal for rapid client deployments.
        </p>
      </div>
    ),
  },
];

export function CompanyTimeline() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <Timeline data={milestones} />
    </section>
  );
}
```

## Lyfework Customization Notes
- Timeline beam color can be set to gradient `from-[#ff642a] to-[#ff0301]`
- Year/title labels use Manrope 800, content headings use 700, descriptions use 400
- Section background #0a0a0a with white/neutral text for readability
- Timeline dot/node indicators can be colored `bg-[#ff642a]` for brand accent
- Sticky headers work well on desktop; on mobile, they stack normally for GHL compatibility

## Performance Notes
- Scroll progress beam uses `useScroll` with a single `useTransform` mapping
- Sticky headers use CSS `position: sticky`, zero JavaScript overhead
- Content sections lazy-render if using `IntersectionObserver` for below-fold entries
- Beam gradient animation is a `scaleY` transform, GPU-composited
- Works smoothly with 10+ timeline entries without performance degradation
