---
name: minimal-card
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/minimal-card
category: components
tags: card, minimal, clean, hover, subtle
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# MinimalCard

> Clean minimal card with subtle hover effects, ideal for content grids and feature sections.

## When to Use
- Feature grids with clean, consistent card styling
- Blog post previews with minimal visual overhead
- Service listings with understated elegance
- Dashboard widget containers
- Any card layout prioritizing content over decoration

## When NOT to Use
- When cards need heavy visual treatment or backgrounds
- Showcase sections requiring dramatic hover effects
- Layouts where cards must stand out individually from each other

## Pairs Well With
- `animated-content` - Staggered entrance of minimal card grids
- `marquee` - Minimal cards inside a scrolling marquee strip
- `gradient-text` - Subtle gradient title within minimal card
- `spotlight-card` - Upgrade to spotlight when more visual impact is needed

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| title | string | '' | Card title |
| description | string | '' | Card description |
| icon | ReactNode | undefined | Optional leading icon |
| href | string | undefined | Optional link wrapper |
| hoverEffect | 'lift' \| 'glow' \| 'border' \| 'none' | 'lift' | Hover interaction style |
| className | string | '' | Additional CSS classes |
| children | ReactNode | - | Card content |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/minimal-card"
```

## Usage Example
```jsx
import { MinimalCard } from "@/components/ui/minimal-card";
import { Zap, Shield, BarChart3 } from "lucide-react";

export function FeatureGrid() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6 max-w-5xl mx-auto">
        <MinimalCard
          title="Lightning Fast"
          description="Sub-second load times with edge-optimized delivery."
          icon={<Zap className="text-[#ff642a]" size={24} />}
          hoverEffect="lift"
          className="rounded-[12px]"
        />
        <MinimalCard
          title="Enterprise Security"
          description="SOC2 compliant with end-to-end encryption."
          icon={<Shield className="text-[#ff642a]" size={24} />}
          hoverEffect="lift"
          className="rounded-[12px]"
        />
        <MinimalCard
          title="Deep Analytics"
          description="Real-time dashboards with actionable insights."
          icon={<BarChart3 className="text-[#ff642a]" size={24} />}
          hoverEffect="lift"
          className="rounded-[12px]"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Default styling: bg-white/5 border border-white/10 on #0a0a0a
- Icons: brand orange #ff642a for visual accent
- Title: Manrope 700, Description: Manrope 400 text-white/60
- 12px card radius, lift hover with subtle translateY(-2px) + shadow
- GHL compatible -- zero JS, pure CSS hover effects

## Performance Notes
- Zero JavaScript dependencies -- pure CSS component
- Hover effects use CSS transform and box-shadow (GPU-accelerated)
- No repaints on hover -- only composite layer changes
- Minimal DOM footprint per card
- Works perfectly with SSR and static generation
