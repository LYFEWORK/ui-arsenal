---
name: glass-surface
source: ReactBits
source_url: https://reactbits.dev/components/glass-surface
category: components
tags: glass, surface, frosted, blur, panel, premium, backdrop
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# GlassSurface

> A frosted glass surface panel/card with configurable blur, opacity, and border styling. The foundational glassmorphism container component. Pure CSS implementation with no dependencies.

## When to Use

- Any card, panel, or container that needs a frosted glass aesthetic
- Hero section content overlays on top of gradient or image backgrounds
- Navigation bars with translucent glass backgrounds
- Sidebar panels in dashboard layouts
- Modal/dialog containers with premium glass styling

## When NOT to Use

- Light background layouts where frosted glass has no contrast
- Print stylesheets or email templates (backdrop-filter not supported)
- Very old browser targets (IE11, older Safari without prefix)
- Performance-critical mobile views with many stacked glass panels

## Pairs Well With

- `aurora` - Aurora gradient background visible through the glass surface
- `particles` - Particles floating behind glass panels for depth
- `gradient-text` - Gradient text inside glass containers
- `spotlight-card` - Combine spotlight hover with glass surface for premium cards

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content inside the glass surface |
| blur | number | 16 | Backdrop blur intensity in px |
| bgOpacity | number | 0.04 | Background white opacity (0-1) |
| borderOpacity | number | 0.06 | Border white opacity (0-1) |
| borderRadius | string | "12px" | Border radius |
| shadow | boolean | true | Apply subtle drop shadow |
| as | string | "div" | HTML element or component to render as |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GlassSurface-TS-TW
```

## Usage Example

```jsx
import GlassSurface from '@/components/ui/GlassSurface';

function CTASection() {
  return (
    <section className="relative py-32 px-8 bg-[#0a0a0a] overflow-hidden">
      {/* Background blobs */}
      <div className="absolute top-0 left-1/3 w-[500px] h-[500px] bg-[#ff642a]/15 rounded-full blur-[150px]" />
      <div className="absolute bottom-0 right-1/4 w-[400px] h-[400px] bg-[#ff0301]/10 rounded-full blur-[120px]" />

      <GlassSurface
        blur={20}
        bgOpacity={0.05}
        borderOpacity={0.08}
        borderRadius="16px"
        className="relative z-10 max-w-2xl mx-auto p-12 text-center"
      >
        <h2 className="text-4xl font-extrabold text-white font-[Manrope]">
          Ready to Scale Your Practice?
        </h2>
        <p className="mt-4 text-gray-300 text-lg">
          Book a free strategy call. We will map out your automation roadmap in 30 minutes.
        </p>
        <a
          href="/book"
          className="inline-block mt-8 px-8 py-4 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold rounded-lg text-base hover:opacity-90 transition"
        >
          Book Your Free Call
        </a>
      </GlassSurface>
    </section>
  );
}
```

## Lyfework Customization Notes

- This is the base component behind the `lyf-glass` utility class
- Standard Lyfework glass values: `blur: 20, bgOpacity: 0.04, borderOpacity: 0.06`
- Border radius: `12px` for cards, `16px` for hero panels, `8px` for buttons
- Background blobs: `#ff642a` at 15% and `#ff0301` at 10% with 120-150px blur
- Font: `Manrope` throughout; 800 for headings, 400 for body
- Fully GHL compatible -- pure CSS, no JS dependencies whatsoever

## Performance Notes

- Pure CSS using `backdrop-filter: blur()` and `background: rgba(255,255,255,var)`
- Zero JavaScript overhead; renders as a styled div
- `backdrop-filter` is GPU-accelerated on modern browsers
- Avoid stacking more than 3 glass surfaces in the same viewport (compounding blur cost)
- Provide `@supports` fallback for browsers without backdrop-filter support
