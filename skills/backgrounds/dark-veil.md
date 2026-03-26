---
name: dark-veil
source: ReactBits
source_url: https://reactbits.dev/backgrounds/dark-veil
category: backgrounds
tags: background, dark, veil, overlay, translucent, dim, section
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# DarkVeil

> A dark translucent overlay/veil effect that dims and adds depth to any section. The workhorse utility background for improving text readability over images or other backgrounds.

## When to Use

- Over hero images or video backgrounds to improve text readability
- Section overlays where you need content to pop against a busy background
- Layered over other animated backgrounds (Aurora, Particles, etc.) for text clarity
- Dark mode section transitions to create visual depth between blocks
- Behind modal or dialog content to dim the page

## When NOT to Use

- On already-dark solid backgrounds (redundant, just darkens further)
- When you want the background content to remain fully visible
- As a standalone background without anything beneath it (pointless)

## Pairs Well With

- `aurora` - DarkVeil over Aurora gives you the glow without sacrificing readability
- `blur-text` - Text over a veiled background has perfect contrast for blur reveals
- `animated-content` - Content fading in over the veiled background feels clean
- `spotlight-card` - Cards over a veiled background section look polished and elevated

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| opacity | number | 0.5 | Veil darkness from 0 (transparent) to 1 (opaque) |
| color | string | "#000000" | Veil color (usually black or very dark) |
| blur | number | 0 | Optional backdrop blur in pixels |
| gradient | boolean | false | Fade from dark to transparent instead of flat overlay |
| gradientDirection | string | "bottom" | Direction of gradient fade: "top", "bottom", "left", "right" |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/DarkVeil-TS-TW
```

## Usage Example

```jsx
import DarkVeil from '@/components/ui/DarkVeil';

function ClinicHero({ backgroundImage }) {
  return (
    <section className="relative min-h-[70vh] flex items-center overflow-hidden">
      {/* Background image */}
      <img
        src={backgroundImage}
        alt=""
        className="absolute inset-0 w-full h-full object-cover"
      />

      {/* Dark veil for readability */}
      <DarkVeil
        opacity={0.6}
        gradient={true}
        gradientDirection="bottom"
      />

      {/* Content */}
      <div className="relative z-10 max-w-4xl mx-auto px-8 text-center">
        <h1 className="text-4xl md:text-6xl font-bold text-white font-[Manrope]">
          Your Smile, Reimagined
        </h1>
        <p className="mt-4 text-lg text-gray-200">
          Modern dental care with a personal touch.
        </p>
        <a
          href="#booking"
          className="mt-8 inline-block px-8 py-4 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold"
        >
          Book Your Appointment
        </a>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default Lyfework veil: `color="#0a0a0a"` with `opacity={0.5}` matches the brand dark background
- For clinic/client sites: use `gradient={true}` with `gradientDirection="bottom"` for a natural fade
- Combine with `lyf-glass` card styling for a layered glass-over-veil look
- For GHL: apply as a `::before` pseudo-element on the section container if the React component is unavailable
- The veil is the most reusable utility in the arsenal. Use it to rescue any background that hurts readability.
- `blur` of 4-8px creates a frosted glass effect when combined with opacity 0.3-0.4

## Performance Notes

- Extremely lightweight, just a CSS overlay element
- Zero JavaScript overhead, purely CSS-driven
- No performance concerns on any device or browser
- SSR-compatible with zero hydration cost
- Can be replaced with a simple Tailwind `bg-black/50` div if the component feels like overkill
