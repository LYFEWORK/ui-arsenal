---
name: curved-loop
source: ReactBits
source_url: https://reactbits.dev/text-animations/curved-loop
category: text-animations
tags: text, curved, loop, path, circular, continuous, decorative
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# CurvedLoop

> Text that curves along a circular or custom SVG path and loops continuously, creating an eye-catching decorative element.

## When to Use

- Badge-style decorative text orbiting a logo or icon
- Circular taglines wrapping around a hero image or avatar
- Decorative section dividers where text follows a curved path
- Brand stamp or seal elements on portfolio and agency pages
- Playful accent text on creative landing pages

## When NOT to Use

- Primary headlines or any text the user must read quickly
- Dense informational content or paragraphs
- Mobile-first layouts where curved text becomes illegible at small sizes
- Pages focused on conversion where every word must scan instantly

## Pairs Well With

- `aurora` - Curved text orbiting over an aurora background for a cosmic hero
- `particles` - Looping text with particle effects behind for depth
- `spotlight-card` - Curved badge text wrapping the corner of a SpotlightCard
- `tilted-card` - Decorative curved text accent on a tilted product card

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text content to render along the path |
| radius | number | 100 | Radius of the circular path in pixels |
| speed | number | 10 | Rotation speed in seconds per full loop |
| direction | "clockwise" \| "counterclockwise" | "clockwise" | Direction of text rotation |
| fontSize | number | 14 | Font size in pixels |
| letterSpacing | number | 2 | Spacing between characters in pixels |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CurvedLoop-TS-TW
```

## Usage Example

```jsx
import CurvedLoop from '@/components/ui/CurvedLoop';

function ClinicBrandSeal() {
  return (
    <section className="relative min-h-screen flex items-center justify-center bg-[#0a0a0a]">
      <div className="relative">
        <img
          src="/clinic-logo.svg"
          alt="Clinic Logo"
          className="w-24 h-24 rounded-full"
        />
        <CurvedLoop
          text="LYFEWORK STUDIO  ·  BUILT DIFFERENT  ·  "
          radius={80}
          speed={15}
          direction="clockwise"
          fontSize={12}
          letterSpacing={3}
          className="text-white/60 font-bold uppercase tracking-widest"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use Manrope 700 uppercase with wide letter-spacing for the curved text
- On #0a0a0a backgrounds, use `text-white/50` or `text-white/60` so it reads as decorative, not primary
- Keep text short (under 30 characters repeated) to avoid crowding the path
- Speed of 12-18 seconds per loop feels elegant; under 8s feels frantic
- For GHL embed: use inline SVG path so the animation works without React hydration
- Pair with the Lyfework gradient (`#ff642a` to `#ff0301`) as a subtle text color for brand seals

## Performance Notes

- Pure CSS animation with SVG textPath, no JavaScript runtime cost
- Zero layout shift since the element is absolutely positioned
- Very lightweight, no external dependencies
- Runs on GPU via CSS `animation: rotate`, minimal battery impact
- Works on all modern browsers including mobile Safari
