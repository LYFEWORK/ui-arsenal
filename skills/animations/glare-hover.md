---
name: glare-hover
source: ReactBits
source_url: https://reactbits.dev/animations/glare-hover
category: animations
tags: glare, hover, shine, reflection, card, premium
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# GlareHover

> A cursor-tracking glare/shine effect that sweeps across an element on hover, simulating a reflective surface for a premium, tactile feel.

## When to Use

- Every card component that needs to feel premium without being over-the-top
- Pricing cards, feature cards, testimonial cards -- the universal "polish" layer
- CTA buttons that need subtle interactivity beyond color change
- Image thumbnails in a gallery to simulate a glossy print feel
- Hero section glass panels to reinforce the premium aesthetic

## When NOT to Use

- Text-only content blocks where the glare competes with readability
- Elements that already have complex hover animations (tilt, spotlight, etc.)
- Light-background designs where the glare is barely visible
- Extremely small elements like icon buttons or tags

## Pairs Well With

- `tilted-card` - Tilt handles the perspective, glare adds the reflective sheen on top
- `animated-content` - Scroll-reveal the card, then glare activates on hover
- `blur-text` - Glare card below a blur-text headline creates a cohesive premium section
- `spotlight-card` - Use one or the other, not both (they serve similar hover-enhance purposes)

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to apply glare effect to |
| glareColor | string | "rgba(255,255,255,0.15)" | Color and opacity of the glare |
| glareSize | number | 200 | Diameter of the glare spot in pixels |
| glareOpacity | number | 0.15 | Maximum opacity of the glare (0-1) |
| borderRadius | number | 12 | Border radius matching the card |
| disabled | boolean | false | Disable the effect (useful for mobile) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GlareHover-TS-TW
```

## Usage Example

```jsx
import GlareHover from '@/components/ui/GlareHover';

function TestimonialCards() {
  const testimonials = [
    { name: 'Dr. Sarah Chen', role: 'Clinic Owner', text: 'Lyfework transformed our online presence.' },
    { name: 'Marcus Webb', role: 'Founder, Fitlyf', text: 'The best investment we made this year.' },
    { name: 'Aisha Patel', role: 'Marketing Dir.', text: 'Our conversion rate doubled in 60 days.' },
  ];

  return (
    <section className="bg-[#0a0a0a] py-24 px-8 font-[Manrope]">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        {testimonials.map((t, i) => (
          <GlareHover key={i} glareOpacity={0.12} borderRadius={12}>
            <div className="lyf-glass p-8 rounded-[12px]">
              <p className="text-gray-300 italic">"{t.text}"</p>
              <div className="mt-6">
                <p className="text-white font-bold">{t.name}</p>
                <p className="text-sm text-gray-500">{t.role}</p>
              </div>
            </div>
          </GlareHover>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default `glareColor` at `rgba(255,255,255,0.15)` works perfectly on `lyf-glass` cards over `#0a0a0a`.
- For brand-tinted glare, try `rgba(255,100,42,0.08)` for a warm orange sheen.
- Match `borderRadius` to the card: `12` for standard cards, `16` for feature cards, `8` for compact cards.
- This is the Tier 1 go-to hover effect. Use it on every card unless the card already has tilt or spotlight.
- GHL embeds: works reliably since it only uses `mousemove` on the card element itself, not the document.
- Pair with Manrope bold headings inside the card to keep typography consistent with the brand system.

## Performance Notes

- Pure CSS radial-gradient overlay positioned via JS mouse tracking
- No canvas, no SVG, no external dependencies -- the lightest hover effect in the arsenal
- Uses `pointer-events: none` on the glare layer so clicks pass through cleanly
- Automatically disables on touch devices via media query `(hover: hover)`
- Zero bundle size impact beyond the component itself (~1.5KB)
