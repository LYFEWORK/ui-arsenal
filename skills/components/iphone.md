---
name: iphone
source: Magic UI
source_url: https://magicui.design/docs/components/iphone
category: components
tags: device, mockup, iphone, mobile, frame
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Iphone

> iPhone device mockup frame for displaying app screenshots, mobile previews, or video content in a realistic device shell.

## When to Use
- Mobile app showcase sections on landing pages
- Displaying responsive design in device context
- App store preview mockups in portfolio projects
- Before/after mobile UI comparisons
- Product demo sections showing mobile experience

## When NOT to Use
- When the content should fill the full viewport without framing
- Desktop-only product showcases (use Safari mockup instead)
- When the mockup frame draws too much attention from the content
- Print or static contexts where the device frame adds no value

## Pairs Well With
- `animated-content` - Slide the phone mockup in from the side
- `spotlight-card` - Spotlight glow behind the device frame
- `aurora` - Aurora gradient behind the phone for visual depth
- `tilted-card` - Tilt the phone mockup on hover for 3D effect

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| src | string | required | Image or video source URL |
| className | string | "" | Additional CSS classes |
| width | number | 433 | Device frame width |
| height | number | 882 | Device frame height |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/iphone"
```

## Usage Example
```jsx
import { Iphone } from "@/components/magicui/iphone";

export function MobileAppShowcase() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <div className="mx-auto max-w-6xl flex flex-col lg:flex-row items-center gap-16 px-6">
        <div className="flex-1">
          <h2 className="font-manrope font-800 text-4xl text-white mb-6">
            Book appointments{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              on the go
            </span>
          </h2>
          <p className="font-manrope font-400 text-white/60 text-lg mb-8">
            Patients can schedule, reschedule, and manage appointments from their phone in seconds.
          </p>
        </div>
        <div className="flex-1 flex justify-center">
          <Iphone src="/images/mobile-booking-screenshot.png" className="shadow-2xl" />
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Device frame renders with a realistic bezel — no additional border styling needed
- Screenshot content should use the Lyfework UI with Manrope font and brand colors
- Place on `#0a0a0a` backgrounds with subtle shadow for floating effect
- Pair with `animated-content` to slide the device in from the right on scroll
- GHL compatible — pure HTML/CSS device frame, no canvas or WebGL

## Performance Notes
- Device frame is CSS/SVG — extremely lightweight
- Screenshot image is the main payload — optimize with WebP
- No JavaScript animation by default — frame is static
- Combine with Framer Motion externally for entrance animations
- Use `loading="lazy"` for screenshots below the fold
