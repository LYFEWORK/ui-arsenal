---
name: sticky-banner
source: Aceternity UI
source_url: https://ui.aceternity.com/components/sticky-banner
category: components
tags: banner, sticky, notification, announcement, top-bar, dismissible
dependencies: none
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# StickyBanner

> Sticky top announcement or notification banner that stays visible as the user scrolls, with optional dismiss functionality.

## When to Use
- Announcing promotions, sales, or limited-time offers
- Displaying important site-wide notices or updates
- Promoting new features or product launches
- Showing compliance or cookie consent notices
- Highlighting upcoming events or webinars

## When NOT to Use
- When the announcement is not important enough for persistent visibility
- If multiple sticky elements already compete for top-of-viewport space
- For content that should appear inline in the page flow

## Pairs Well With
- `floating-navbar` - Stack banner above the floating navigation
- `gradient-text` - Gradient highlight on banner CTA text
- `animated-content` - Slide-in animation for the banner on page load
- `marquee` - Scrolling text inside the banner for long announcements

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Banner content |
| className | string | - | Additional classes for the banner |
| dismissible | boolean | true | Whether the banner can be closed |
| onDismiss | function | - | Callback when banner is dismissed |

## Installation
```bash
npx aceternity-ui@latest add sticky-banner
```

## Usage Example
```jsx
import { StickyBanner } from "@/components/ui/sticky-banner";

export function PromoBanner() {
  return (
    <StickyBanner className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white py-3 px-6">
      <div className="flex items-center justify-center gap-3 max-w-6xl mx-auto">
        <span className="font-[Manrope] font-700 text-sm">
          Limited Offer: Get 30% off your first Lyfework project
        </span>
        <a
          href="/contact"
          className="bg-white text-[#0a0a0a] font-[Manrope] font-700 text-sm px-4 py-1.5 rounded-[8px] hover:bg-white/90 transition-colors"
        >
          Claim Now
        </a>
      </div>
    </StickyBanner>
  );
}
```

## Lyfework Customization Notes
- Banner background uses `from-[#ff642a] to-[#ff0301]` gradient for high visibility
- Manrope 700 for banner text, 700 for CTA button text
- CTA button uses inverted colors: `bg-white text-[#0a0a0a]` with `rounded-[8px]`
- Dismiss button (X) should be white with hover opacity
- In GHL, ensure the banner z-index sits above all other page elements including nav

## Performance Notes
- Zero JavaScript dependencies; pure CSS `position: sticky` for scroll behavior
- Dismiss state can be stored in `localStorage` to prevent re-showing after page refresh
- No layout shift if banner height is accounted for in initial page render
- Minimal DOM: single container element with inline content
- CSS `position: sticky` is well-supported in all modern browsers including Safari
