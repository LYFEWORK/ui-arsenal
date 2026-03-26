---
name: expandable-card
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/expandable-card
category: components
tags: card, expandable, accordion, reveal, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# ExpandableCard

> Card that expands inline to reveal more content with smooth height animation.

## When to Use
- Feature cards with detailed descriptions that expand on click
- FAQ sections with expandable answer cards
- Service listings with expandable detail panels
- Pricing cards with expandable feature lists
- Team member cards expanding to show full bios

## When NOT to Use
- When all card content should be immediately visible
- Very long expanded content that pushes other cards far down
- Layouts where card expansion causes jarring layout shifts

## Pairs Well With
- `spotlight-card` - Spotlight effect on expandable cards
- `animated-content` - Staggered entrance of expandable card grid
- `shimmer-button` - "Learn More" shimmer trigger for expansion
- `gradient-text` - Gradient card titles with expandable details

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | '' | Card title |
| description | string | '' | Card preview description |
| children | ReactNode | - | Expandable content |
| defaultExpanded | boolean | false | Initially expanded state |
| icon | ReactNode | undefined | Optional card icon |
| onToggle | (expanded: boolean) => void | - | Toggle callback |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/expandable-card"
```

## Usage Example
```jsx
import { ExpandableCard } from "@/components/ui/expandable-card";

export function ServiceCards() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-12">
        Our Services
      </h2>
      <div className="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-4xl mx-auto">
        <ExpandableCard
          title="Brand Strategy"
          description="Define your brand identity and market positioning."
          className="lyf-glass rounded-[12px] border border-white/10"
        >
          <div className="pt-4 border-t border-white/10">
            <ul className="space-y-2 font-manrope font-400 text-white/70">
              <li>Market research & competitive analysis</li>
              <li>Brand voice & messaging framework</li>
              <li>Visual identity guidelines</li>
              <li>Customer persona development</li>
            </ul>
          </div>
        </ExpandableCard>
        <ExpandableCard
          title="Web Development"
          description="Custom websites built for conversion and speed."
          className="lyf-glass rounded-[12px] border border-white/10"
        >
          <div className="pt-4 border-t border-white/10">
            <ul className="space-y-2 font-manrope font-400 text-white/70">
              <li>Next.js & React development</li>
              <li>GHL funnel integration</li>
              <li>Performance optimization</li>
              <li>Analytics & tracking setup</li>
            </ul>
          </div>
        </ExpandableCard>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Card container: lyf-glass, 12px radius, border-white/10 on #0a0a0a
- Title: Manrope 700, Description: Manrope 400 text-white/60
- Expanded content separated with border-t border-white/10 divider
- Expand indicator: brand orange #ff642a chevron icon
- GHL compatible for FAQ and service detail sections

## Performance Notes
- Framer Motion animate height uses GPU-accelerated transforms
- Only expanded content is measured; collapsed content is unmounted
- Height animation avoids layout thrashing with will-change: height
- Smooth spring animation at ~60fps on mid-range devices
- No impact on surrounding card layout until expansion completes
