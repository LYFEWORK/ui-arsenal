---
name: luxe-badge
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-badge
category: components
tags: badge, tag, label, status, animated, pulse
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# LuxeBadge

> Animated badge component with smooth entrance animation and optional pulse effect for status indicators.

## When to Use
- Status indicators (Online, Active, New) on dashboard or profile elements
- Feature labels ("Beta", "New", "Pro") on navigation items or cards
- Category tags on blog posts, portfolio projects, or service listings
- Notification count badges on navigation icons
- Highlight labels on pricing cards ("Most Popular", "Best Value")

## When NOT to Use
- Long text content that should be a chip or pill component instead
- Interactive elements that need click/toggle behavior — use a button
- Dense lists where animated badges on every item cause visual noise
- Static content where animation adds no functional value

## Pairs Well With
- `luxe-card` - badge overlay on card corner for "New" or "Featured" labels
- `dock` - notification count badges on dock items
- `marquee` - animated badges scrolling in a testimonial or partner marquee
- `gradient-text` - gradient badge text matching the section heading style

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Badge content |
| className | string | — | Additional CSS classes |
| variant | "default" \| "outline" \| "gradient" | "default" | Visual style variant |
| pulse | boolean | false | Enable pulsing animation |
| animate | boolean | true | Enable entrance animation |
| size | "sm" \| "md" \| "lg" | "md" | Badge size preset |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-badge"
```

## Usage Example
```jsx
import { LuxeBadge } from "@/components/ui/luxe-badge";

export function PricingCardHeader() {
  return (
    <div className="relative lyf-glass rounded-[12px] p-8 bg-[#0a0a0a]/80">
      <LuxeBadge
        variant="gradient"
        className="absolute -top-3 right-4 bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white text-xs px-3 py-1 rounded-full"
        pulse
      >
        Most Popular
      </LuxeBadge>
      <h3 className="font-manrope font-800 text-2xl text-white mt-2">Growth Plan</h3>
      <p className="font-manrope font-400 text-gray-400 mt-2">Perfect for scaling practices</p>
    </div>
  );
}
```

## Lyfework Customization Notes
- Gradient variant: `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` for brand badges
- Use `font-manrope font-700` for badge text in all variants
- On `#0a0a0a` backgrounds, outline variant should use `border-[#ff642a]/50`
- Pulse animation color should match badge background for cohesive glow
- GHL compatible — pure CSS animation, embeds without issue
- Use `rounded-full` for pill-shaped badges, `rounded-[8px]` for rectangular

## Performance Notes
- Pure CSS keyframe animations — no JavaScript runtime needed
- Pulse uses box-shadow animation — GPU-composited
- Entrance animation is one-shot — no continuous CPU usage after mount
- Negligible DOM footprint — single span element with pseudo-elements
- Safe to render 50+ badges on a page without performance degradation
