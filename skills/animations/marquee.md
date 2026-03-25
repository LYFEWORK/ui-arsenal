---
name: marquee
source: ReactBits
source_url: https://reactbits.dev/animations/marquee
category: animations
tags: marquee, scroll, ticker, infinite, logos, brands, testimonials
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Marquee

> Infinite horizontal scrolling content strip. Logos, testimonials, badges, or any content that scrolls continuously. Pauses on hover. CSS-only.

## When to Use

- Client logo bars ("Trusted by" sections)
- Social proof tickers (review snippets scrolling by)
- Technology/tool stack displays
- Award or certification badge strips
- Any content that benefits from continuous ambient movement

## When NOT to Use

- Content users need to read carefully (scrolling makes it hard)
- More than 2 marquee strips on one page
- Single items or very few items (looks broken with gaps)

## Pairs Well With

- `animated-content` - Reveal the marquee section on scroll
- `count-up` - Stats section above, logo marquee below
- `blur-text` - "Trusted By" headline blur-reveals, then marquee starts

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode[] | required | Items to scroll |
| speed | number | 30 | Scroll speed in seconds per loop |
| direction | "left" \| "right" | "left" | Scroll direction |
| pauseOnHover | boolean | true | Pause scrolling on hover |
| gap | number | 40 | Gap between items in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Marquee-TS-TW
```

## Usage Example

```jsx
import Marquee from '@/components/ui/Marquee';

function TrustedBy() {
  const logos = ['/logos/client1.svg', '/logos/client2.svg', '/logos/client3.svg', '/logos/client4.svg', '/logos/client5.svg'];
  return (
    <section className="py-16 border-y border-white/5">
      <p className="text-center text-sm text-gray-500 uppercase tracking-widest mb-8">Trusted By</p>
      <Marquee speed={40} pauseOnHover={true} gap={60}>
        {logos.map((src, i) => (
          <img key={i} src={src} alt="" className="h-8 opacity-40 hover:opacity-100 transition-opacity" />
        ))}
      </Marquee>
    </section>
  );
}
```

## Lyfework Customization Notes

- Logo opacity: 40% default, 100% on hover for the understated look
- `speed` of 30-50 for logos. Faster (15-25) for text testimonial tickers.
- Gap of 40-80px between logos depending on logo size
- For double-row effect: stack two Marquees with opposite directions
- Works perfectly in GHL (pure CSS animation with `@keyframes`)

## Performance Notes

- Pure CSS animation, zero JavaScript
- Duplicates children internally for seamless loop
- Will-change: transform for GPU acceleration
- No performance concerns whatsoever
