---
name: hero-heatmap
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/hero-heatmap
category: backgrounds
tags: hero, heatmap, interactive, data-viz, background
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# HeroHeatmap

> Interactive heatmap-style hero background that responds to mouse movement or data input.

## When to Use
- Analytics or data-focused SaaS product hero sections
- Dashboard landing pages where data visualization sets the tone
- Tech company sites emphasizing data intelligence
- Interactive portfolio pieces showcasing technical capability
- Conference or event pages with dynamic visual appeal

## When NOT to Use
- Mobile-first pages where hover interactions are unavailable
- Simple marketing pages where interactivity is unnecessary
- Accessibility-critical contexts without proper keyboard fallbacks
- Content-heavy pages where background competes for attention

## Pairs Well With
- `number-ticker` - Animated stats overlaid on heatmap background
- `spotlight-card` - Feature cards with spotlight on heatmap canvas
- `blur-text` - Text blur-in reveals over heatmap create drama
- `shimmer-button` - Shimmering CTA buttons stand out on heat-colored background

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ['#0a0a0a', '#ff642a', '#ff0301'] | Heatmap color gradient stops |
| interactive | boolean | true | Enable mouse-tracking heat effect |
| cellSize | number | 20 | Size of each heatmap cell in pixels |
| intensity | number | 0.6 | Heat intensity multiplier |
| decay | number | 0.95 | Rate at which heat decays per frame |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/hero-heatmap"
```

## Usage Example
```jsx
import { HeroHeatmap } from "@/components/ui/hero-heatmap";

export function AnalyticsHero() {
  return (
    <section className="relative min-h-screen bg-[#0a0a0a]">
      <HeroHeatmap
        colors={["#0a0a0a", "#ff642a", "#ff0301"]}
        interactive={true}
        cellSize={16}
        intensity={0.5}
        decay={0.97}
        className="absolute inset-0 opacity-60"
      />
      <div className="relative z-10 flex flex-col items-center justify-center min-h-screen px-6">
        <h1 className="font-manrope font-800 text-6xl text-white text-center">
          See the Data. Feel the Insight.
        </h1>
        <p className="font-manrope font-400 text-white/60 mt-4 max-w-lg text-center">
          Real-time analytics for modern healthcare practices.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Map brand gradient #ff642a to #ff0301 onto heatmap color scale
- Reduce opacity to 40-60% so Manrope headings remain readable
- Use with #0a0a0a base to keep dark theme consistent
- Add `lyf-glass` content containers over heatmap for card sections
- Disable interactive mode in GHL embeds where pointer events may conflict

## Performance Notes
- Canvas-based rendering keeps DOM node count minimal
- requestAnimationFrame loop runs only when tab is visible
- Decay mechanism naturally reduces computation over time
- cellSize directly impacts draw calls -- increase on mobile (24-32px)
- Pause animation when element leaves viewport via IntersectionObserver
