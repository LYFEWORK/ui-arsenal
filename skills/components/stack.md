---
name: stack
source: ReactBits
source_url: https://reactbits.dev/components/stack
category: components
tags: stack, depth, layers, cards, container, 3d
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Stack

> A stacked element container with visual depth effect. Multiple cards or elements are layered behind each other with slight offsets and scale reductions, creating a "deck of cards" appearance. Interactive variants allow clicking to cycle through the stack.

## When to Use

- Testimonial or review displays where one card is featured with others peeking behind
- Image stacks showing multiple related photos in a layered composition
- Notification or card queue visualizations
- Feature comparisons where stacking implies progression or hierarchy
- Any single-item spotlight that hints at more content behind it

## When NOT to Use

- Content where all items need equal visibility (use a grid instead)
- Long lists of items (stack implies 3-5 items, not 20)
- Mobile layouts where the offset depth is too subtle on small screens
- Layouts where stacking creates confusion about what is clickable

## Pairs Well With

- `card-swap` - Click-to-swap animation for cycling through the stack
- `spotlight-card` - Spotlight hover on the top card in the stack
- `animated-content` - Scroll-reveal the entire stack composition
- `gradient-text` - Gradient text on the top/featured card

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode[] | required | Array of stacked elements |
| offset | number | 8 | Pixel offset between layers |
| scaleStep | number | 0.05 | Scale reduction per layer |
| rotateStep | number | 0 | Rotation per layer in degrees |
| interactive | boolean | false | Click top card to cycle stack |
| direction | "down" \| "up" \| "left" \| "right" | "down" | Stack offset direction |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Stack-TS-TW
```

## Usage Example

```jsx
import Stack from '@/components/ui/Stack';

function FeaturedTestimonial() {
  const reviews = [
    {
      quote: 'Revenue doubled in 60 days. The automation just works.',
      name: 'Dr. Patel',
      clinic: 'Summit Dental',
    },
    {
      quote: 'Best investment we have made for our practice.',
      name: 'Sarah Kim',
      clinic: 'Glow Aesthetics',
    },
    {
      quote: 'Our team saves 20 hours a week now.',
      name: 'Mike Torres',
      clinic: 'Peak PT',
    },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a] flex justify-center">
      <Stack
        offset={10}
        scaleStep={0.04}
        rotateStep={1.5}
        interactive
        direction="down"
        className="w-full max-w-md"
      >
        {reviews.map((r, i) => (
          <div key={i} className="lyf-glass rounded-xl p-8">
            <p className="text-white text-lg italic">"{r.quote}"</p>
            <div className="mt-6 flex items-center gap-3">
              <div className="w-10 h-10 rounded-full bg-gradient-to-br from-[#ff642a] to-[#ff0301]" />
              <div>
                <p className="text-white font-bold font-[Manrope]">{r.name}</p>
                <p className="text-gray-400 text-sm">{r.clinic}</p>
              </div>
            </div>
          </div>
        ))}
      </Stack>
    </section>
  );
}
```

## Lyfework Customization Notes

- Card backgrounds: `lyf-glass` with `rounded-xl` (12px) for Lyfework standard
- Avatar placeholder: `bg-gradient-to-br from-[#ff642a] to-[#ff0301]` brand gradient
- Rotation step: `1.5deg` adds subtle tilt to back cards for natural deck feel
- Font: `Manrope` 700 for names, 400 italic for quotes
- Interactive mode: top card animates to back on click, next card slides forward
- GHL compatible via React code embed; Framer Motion handles the shuffle animation

## Performance Notes

- Stack layers use CSS `transform: scale() translateY() rotate()` for GPU compositing
- Only the top 3 cards are rendered in the DOM; deeper items are hidden
- Framer Motion `AnimatePresence` handles the cycle animation when interactive
- `will-change: transform` on all stack cards for paint optimization
- Lightweight for 3-5 items; avoid stacking 10+ elements
