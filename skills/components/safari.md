---
name: safari
source: Magic UI
source_url: https://magicui.design/docs/components/safari
category: components
tags: device, mockup, browser, safari, frame
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Safari

> Safari browser device mockup frame for displaying web app screenshots in a realistic browser shell.

## When to Use
- Desktop web app showcase sections on landing pages
- SaaS dashboard previews in product marketing
- Portfolio project screenshots with browser context
- Documentation showing web interface examples
- Before/after website redesign comparisons

## When NOT to Use
- Mobile app showcases (use the Iphone mockup instead)
- When the browser frame distracts from the actual content
- Full-bleed hero images that should not be framed
- Contexts where the URL bar creates confusion with real navigation

## Pairs Well With
- `animated-content` - Slide the browser mockup into view on scroll
- `spotlight-card` - Spotlight glow effect behind the browser frame
- `tilted-card` - Perspective tilt on the Safari frame for 3D depth
- `aurora` - Aurora gradient behind the browser mockup

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| src | string | required | Image source URL for the browser content |
| url | string | "" | URL displayed in the Safari address bar |
| className | string | "" | Additional CSS classes |
| width | number | 1203 | Frame width |
| height | number | 753 | Frame height |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/safari"
```

## Usage Example
```jsx
import { Safari } from "@/components/magicui/safari";

export function DashboardPreview() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-4xl text-white mb-4">
        Your command{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          center
        </span>
      </h2>
      <p className="text-center font-manrope font-400 text-white/60 mb-16">
        Everything you need to run your clinic, in one dashboard.
      </p>
      <div className="mx-auto max-w-5xl px-6">
        <Safari
          src="/images/dashboard-screenshot.png"
          url="app.lyfework.com/dashboard"
          className="shadow-2xl rounded-[12px]"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Display `app.lyfework.com` in the URL bar for brand authenticity
- Screenshots should show Lyfework UI with Manrope font and brand colors
- Add `shadow-2xl` for depth on `#0a0a0a` backgrounds
- Apply `rounded-[12px]` to the outer frame for card consistency
- GHL compatible — pure HTML/CSS/SVG frame with no JavaScript dependencies

## Performance Notes
- Browser frame is CSS/SVG — extremely lightweight
- Screenshot image is the main payload — optimize with WebP format
- No JavaScript required — frame is entirely static
- Use `loading="lazy"` for screenshots below the fold
- Consider responsive srcSet for different viewport widths
