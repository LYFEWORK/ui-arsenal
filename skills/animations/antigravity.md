---
name: antigravity
source: ReactBits
source_url: https://reactbits.dev/animations/antigravity
category: animations
tags: float, gravity, hover, physics, levitate, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Antigravity

> Elements float upward defying gravity on hover or scroll trigger, creating a weightless levitation effect perfect for hero sections and feature highlights.

## When to Use

- Hero sections where cards or icons need to feel weightless and premium
- Feature grids where items lift on hover to signal interactivity
- Pricing cards that elevate on selection to draw attention
- Portfolio galleries where thumbnails float up as the user scrolls
- Decorative elements that need ambient floating motion in the background

## When NOT to Use

- Dense data tables or forms where motion distracts from input
- Content-heavy blog layouts where reading flow matters more than flair
- Mobile-first designs where hover states don't exist natively
- Sections with many interactive buttons close together (competing motion)

## Pairs Well With

- `animated-content` - AnimatedContent triggers the scroll entry, then Antigravity adds the float on hover
- `spotlight-card` - Cards that glow on hover and also lift create a double-premium feel
- `tilted-card` - Combine tilt with lift for a fully interactive card experience
- `particles` - Floating elements over a particle background sell the zero-gravity theme

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Elements to apply the antigravity effect to |
| floatDistance | number | 20 | How far up (in px) the element floats |
| duration | number | 0.4 | Animation duration in seconds |
| trigger | "hover" \| "scroll" \| "always" | "hover" | What triggers the float effect |
| easing | string | "easeOut" | Framer-motion easing curve |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Antigravity-TS-TW
```

## Usage Example

```jsx
import Antigravity from '@/components/ui/Antigravity';

function ClinicFeatures() {
  const services = [
    { icon: '🦷', title: 'Whitening', desc: 'Premium LED whitening sessions.' },
    { icon: '🩺', title: 'Check-ups', desc: 'Comprehensive oral exams.' },
    { icon: '💉', title: 'Implants', desc: 'Titanium implant placement.' },
  ];

  return (
    <section className="bg-[#0a0a0a] py-24 px-8 font-[Manrope]">
      <h2 className="text-3xl font-bold text-white text-center mb-16">
        Our Services
      </h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {services.map((s, i) => (
          <Antigravity key={i} floatDistance={16} duration={0.35}>
            <div className="lyf-glass p-8 rounded-[12px] text-center">
              <span className="text-4xl">{s.icon}</span>
              <h3 className="mt-4 text-xl font-bold text-white">{s.title}</h3>
              <p className="mt-2 text-gray-400">{s.desc}</p>
            </div>
          </Antigravity>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Keep `floatDistance` between 12-20px. Anything higher feels cartoonish on clinic sites.
- Use `font-[Manrope]` on the parent section so all floated children inherit the brand typeface.
- Apply `lyf-glass` to the inner card for the frosted-glass look on dark `#0a0a0a` backgrounds.
- Rounded corners should be `rounded-[12px]` for cards, `rounded-[8px]` for smaller chips.
- On GHL-embedded pages, test that hover events propagate through the iframe correctly.
- Combine with the brand gradient `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` on a CTA button inside the floated card.

## Performance Notes

- Uses framer-motion `animate` with GPU-accelerated `translateY` transforms only
- No layout shifts since the float is purely transform-based
- On mobile, switch `trigger` to `"scroll"` since hover is unavailable
- Lightweight: adds ~2KB on top of framer-motion
- SSR safe with Next.js; animation only runs client-side
