---
name: link-preview
source: Aceternity UI
source_url: https://ui.aceternity.com/components/link-preview
category: components
tags: link, preview, tooltip, hover, thumbnail, popup
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 2
added: 2026-03-25
---

# LinkPreview

> Hover preview tooltip that shows a thumbnail or preview card of the linked page before the user clicks.

## When to Use
- Blog or documentation pages with cross-references
- Resource pages linking to case studies or portfolio items
- Navigation elements where previewing the destination adds value
- Content-rich pages with many internal links
- Partner or integration pages with preview of external sites

## When NOT to Use
- For simple navigation links where preview adds no value
- On mobile-first experiences where hover is unavailable
- When linked pages have no meaningful visual preview

## Pairs Well With
- `gradient-text` - Gradient-styled link text with preview
- `animated-content` - Fade in link sections on scroll
- `blur-text` - Animate link text appearance
- `dock` - Navigation dock with link previews on hover

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| url | string | - | URL to preview |
| children | ReactNode | - | Link text or element |
| className | string | - | Classes for the link wrapper |
| width | number | 200 | Preview popup width in pixels |
| height | number | 125 | Preview popup height in pixels |
| isStatic | boolean | false | Use a static image instead of iframe |
| imageSrc | string | - | Static image URL for the preview |

## Installation
```bash
npx aceternity-ui@latest add link-preview
```

## Usage Example
```jsx
import { LinkPreview } from "@/components/ui/link-preview";

export function ResourceLinks() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6 max-w-3xl mx-auto">
      <h2 className="font-[Manrope] font-800 text-3xl text-white mb-8">Resources</h2>
      <p className="font-[Manrope] font-400 text-neutral-400 text-lg leading-relaxed">
        Check out our{" "}
        <LinkPreview url="/case-studies/wellness-clinic" imageSrc="/previews/wellness.webp" isStatic>
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent font-700">
            Wellness Clinic case study
          </span>
        </LinkPreview>{" "}
        to see how we increased bookings by 300%, or explore our{" "}
        <LinkPreview url="/services/ghl-integration" imageSrc="/previews/ghl.webp" isStatic>
          <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent font-700">
            GHL integration service
          </span>
        </LinkPreview>{" "}
        for automated patient workflows.
      </p>
    </section>
  );
}
```

## Lyfework Customization Notes
- Link text uses gradient `from-[#ff642a] to-[#ff0301]` with Manrope 700
- Preview popup should have `rounded-[12px]` and `border border-white/10`
- Use `isStatic` with pre-captured screenshots for faster load and GHL compatibility
- Body text uses Manrope 400 on #0a0a0a background
- Static previews avoid cross-origin iframe issues common in GHL embedded contexts

## Performance Notes
- Static image previews have near-zero overhead; iframe previews can be resource-heavy
- Popup renders on hover only, no DOM cost when not interacting
- Use small preview images (400x250px WebP) for fast tooltip appearance
- Framer Motion spring animation for popup entrance/exit is lightweight
- Limit iframe previews to same-origin URLs to avoid security and performance issues
