---
name: share-button
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/share-button
category: components
tags: share, social, button, fan-out, animated, social media
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ShareButton

> Share button with animated social icon fan-out that reveals sharing options in a radial or linear expansion.

## When to Use
- Blog post or article share actions
- Portfolio project pages with social sharing
- Landing page sections where content sharing drives organic growth
- Event or webinar pages encouraging attendees to share
- Case study or testimonial pages worth amplifying

## When NOT to Use
- Dashboard or admin interfaces where sharing is not a primary action
- Private or gated content that should not be shared publicly
- Mobile contexts where native share sheet is more appropriate
- Pages with multiple share buttons close together — fan-out overlaps

## Pairs Well With
- `luxe-card` - share button in the footer of content cards
- `copy-button` - copy link option alongside social share icons
- `spotlight-card` - share action on spotlight-featured content
- `luxe-tooltip` - tooltips on each social icon in the fan-out

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| url | string | — | URL to share |
| title | string | — | Share title/text |
| platforms | string[] | ["twitter", "linkedin", "facebook"] | Social platforms to show |
| className | string | — | Button CSS classes |
| direction | "up" \| "down" \| "left" \| "right" | "up" | Fan-out direction |
| iconSize | number | 20 | Social icon size in pixels |
| spacing | number | 48 | Distance between fanned icons |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/share-button"
```

## Usage Example
```jsx
import { ShareButton } from "@/components/ui/share-button";

export function CaseStudyShare() {
  return (
    <div className="flex items-center justify-between lyf-glass rounded-[12px] p-6 bg-[#0a0a0a]/80">
      <div>
        <p className="font-manrope font-700 text-white">Found this helpful?</p>
        <p className="font-manrope font-400 text-gray-400 text-sm">Share with your network</p>
      </div>
      <ShareButton
        url="https://lyfework.com/case-study/dental-practice-3x-growth"
        title="How we helped a dental practice grow 3x in 6 months"
        platforms={["twitter", "linkedin", "facebook", "email"]}
        direction="up"
        className="text-[#ff642a] hover:text-[#ff0301] rounded-[8px]"
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Trigger icon: `text-[#ff642a]` matching brand accent
- Social icons: white on dark backgrounds, with hover state `opacity-80`
- Container: `lyf-glass rounded-[12px]` for brand card styling
- Text: `font-manrope font-700` for prompt, `font-400` for description
- GHL compatible — share links are standard URLs, open in new tabs
- Include "email" platform for healthcare audiences who prefer email sharing

## Performance Notes
- Social icons are lazily rendered — not in DOM until fan-out is triggered
- Fan-out animation uses staggered spring transitions — sequential reveal
- Click outside detection for closing the fan-out — single event listener
- Icon SVGs are inlined — no external requests for social platform logos
- Auto-closes on share action — clean state management
