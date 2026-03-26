---
name: neumorph-eyebrow
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/neumorph-eyebrow
category: components
tags: eyebrow, badge, label, neumorphism, tag
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# NeumorphEyebrow

> Neumorphic eyebrow badge/label with soft inset shadow for section headings and categories.

## When to Use
- Section eyebrow labels above headings ("New Feature", "Coming Soon")
- Category tags on cards or blog posts
- Status badges in dashboards with soft-UI aesthetic
- Product labels (Beta, Pro, Enterprise) with depth
- Any inline label needing visual depth on dark backgrounds

## When NOT to Use
- Standard flat badge/pill designs where depth is unnecessary
- Light-themed pages where neumorphic shadows work differently
- Very small labels where shadow detail is lost
- High-contrast accessibility modes

## Pairs Well With
- `neumorph-button` - Matching neumorphic visual language
- `gradient-text` - Gradient heading below neumorphic eyebrow
- `animated-content` - Eyebrow badge animating in before heading
- `spotlight-card` - Neumorphic category labels on spotlight cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| label | string | '' | Badge text content |
| variant | 'raised' \| 'inset' \| 'flat' | 'inset' | Shadow depth style |
| size | 'sm' \| 'md' | 'sm' | Badge size |
| color | string | '#1a1a1a' | Base surface color |
| accentColor | string | undefined | Optional accent text color |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/neumorph-eyebrow"
```

## Usage Example
```jsx
import { NeumorphEyebrow } from "@/components/ui/neumorph-eyebrow";

export function SectionHeader() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6 text-center">
      <NeumorphEyebrow
        label="New Feature"
        variant="inset"
        color="#151515"
        accentColor="#ff642a"
        className="font-manrope font-700 uppercase tracking-wider text-xs mx-auto mb-4"
      />
      <h2 className="font-manrope font-800 text-4xl text-white">
        Intelligent Scheduling
      </h2>
      <p className="font-manrope font-400 text-white/60 mt-4 max-w-lg mx-auto">
        AI-powered booking that learns from your practice patterns.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use accentColor="#ff642a" for brand-colored label text
- Surface color #151515 calculates shadows properly against #0a0a0a
- Manrope 700 uppercase with tracking-wider for eyebrow labels
- Size "sm" for card eyebrows, "md" for section eyebrows
- GHL compatible -- pure CSS shadows with no JavaScript

## Performance Notes
- Pure CSS box-shadow implementation -- zero runtime cost
- No JavaScript, no animations, no repaints
- Single DOM element per badge
- Sub-0.5KB component weight
- SSR and static generation safe
