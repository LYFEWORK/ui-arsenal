---
name: card-swap
source: ReactBits
source_url: https://reactbits.dev/components/card-swap
category: components
tags: card, swap, shuffle, animated, transition, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# CardSwap

> Cards that swap and shuffle positions with smooth animation. Users can click or drag to cycle through cards, with each card sliding, rotating, or flipping to its new position. Creates a tactile, deck-of-cards interaction.

## When to Use

- Testimonial sections where reviews shuffle through a card stack
- Team introductions with a "meet the next person" interaction
- Before/after showcases where cards swap to reveal comparisons
- Product feature highlights that cycle through key selling points
- Interactive portfolio pieces where projects shuffle on demand

## When NOT to Use

- Content that needs to be scannable all at once (cards hide content behind each other)
- Data-heavy layouts where users need to compare items side by side
- Accessibility-critical contexts (swapping motion can be disorienting)
- More than 8-10 items (shuffle becomes tedious)

## Pairs Well With

- `animated-content` - Scroll-reveal the card swap section
- `gradient-text` - Gradient heading on the top/active card
- `click-spark` - Spark effect on each swap interaction
- `tilted-card` - Combine tilt hover with swap for layered card depth

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| cards | ReactNode[] | required | Array of card elements to shuffle |
| autoSwap | boolean | false | Auto-cycle through cards on interval |
| interval | number | 3000 | Auto-swap interval in ms |
| swapDirection | "horizontal" \| "vertical" | "horizontal" | Direction of the swap animation |
| draggable | boolean | true | Allow drag-to-swap interaction |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CardSwap-TS-TW
```

## Usage Example

```jsx
import CardSwap from '@/components/ui/CardSwap';

function TestimonialsSection() {
  const testimonials = [
    { name: 'Dr. Patel', clinic: 'Summit Dental', quote: 'Our patient bookings increased 340% in the first 90 days.' },
    { name: 'Sarah Kim', clinic: 'Glow Aesthetics', quote: 'The AI chatbot handles 80% of inquiries before my team even wakes up.' },
    { name: 'Mike Torres', clinic: 'Peak Performance PT', quote: 'Best ROI of any marketing investment we have ever made. Period.' },
  ];

  const cards = testimonials.map((t, i) => (
    <div key={i} className="lyf-glass rounded-xl p-8 w-full max-w-md">
      <p className="text-white text-lg italic leading-relaxed">"{t.quote}"</p>
      <div className="mt-6 flex items-center gap-3">
        <div className="w-10 h-10 rounded-full bg-gradient-to-br from-[#ff642a] to-[#ff0301]" />
        <div>
          <p className="text-white font-bold font-[Manrope]">{t.name}</p>
          <p className="text-gray-400 text-sm">{t.clinic}</p>
        </div>
      </div>
    </div>
  ));

  return (
    <section className="py-24 px-8 bg-[#0a0a0a] flex flex-col items-center">
      <h2 className="text-4xl font-extrabold text-white font-[Manrope] mb-12">
        What Clients Say
      </h2>
      <CardSwap cards={cards} autoSwap interval={4000} swapDirection="horizontal" />
    </section>
  );
}
```

## Lyfework Customization Notes

- Card backgrounds: `lyf-glass` with `rounded-xl` (12px) for Lyfework standard
- Avatar placeholder: `bg-gradient-to-br from-[#ff642a] to-[#ff0301]` Lyfework gradient
- Font: `Manrope` 700 for names, 400 for body text
- Auto-swap interval: 4000ms feels natural; faster feels rushed on clinic sites
- GHL compatible via React code embed; ensure Framer Motion is bundled
- For client builds, add their headshot images and brand colors to the cards

## Performance Notes

- Framer Motion `AnimatePresence` handles mount/unmount of swapping cards efficiently
- Only 2-3 cards are rendered in the DOM at any time (active + adjacent)
- Drag gestures use pointer events with GPU-accelerated transforms
- Auto-swap pauses when the component is not in viewport (Intersection Observer)
- `will-change: transform` applied to animating cards for compositor optimization
