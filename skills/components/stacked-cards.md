---
name: stacked-cards
source: ReactBits
source_url: https://reactbits.dev/components/stacked-cards
category: components
tags: card, stacked, carousel, swipe, deck, interactive
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# StackedCards

> Cards stacked on top of each other that can be swiped or clicked through like a deck. Each card fans out with depth perspective. Great for testimonials or portfolio showcases.

## When to Use

- Testimonial sections (stack client quotes, swipe through)
- Portfolio or case study showcases
- Team member cards on about pages
- Feature highlights where you want progressive disclosure
- Any content where a traditional carousel feels boring

## When NOT to Use

- Content that users need to compare side-by-side (stacking hides context)
- More than 8-10 cards (stack gets unwieldy)
- Critical information that shouldn't be hidden behind interaction
- Mobile layouts where swipe conflicts with page scroll

## Pairs Well With

- `animated-content` - Scroll reveal the stack into view
- `blur-text` - Section headline animates, then stack appears
- `beams` - Dramatic beam background behind a testimonial stack

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | CardItem[] | [] | Array of card content |
| offset | number | 10 | Vertical offset between cards in px |
| scaleFactor | number | 0.06 | Scale decrease per card in stack |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/StackedCards-TS-TW
```

## Usage Example

```jsx
import StackedCards from '@/components/ui/StackedCards';

function Testimonials() {
  const reviews = [
    { text: "Our no-show rate dropped 40% in the first month.", name: "Dr. Sarah Chen" },
    { text: "The system paid for itself in two weeks.", name: "Mark Rivera, DDS" },
    { text: "I finally stopped micromanaging my front desk.", name: "Dr. James Park" },
  ];

  return (
    <section className="py-24 flex justify-center">
      <StackedCards
        items={reviews.map(r => (
          <div className="lyf-glass p-10 rounded-2xl w-[400px]">
            <p className="text-lg text-white italic">"{r.text}"</p>
            <p className="mt-4 text-sm text-gray-400 font-bold">{r.name}</p>
          </div>
        ))}
        offset={12}
        scaleFactor={0.05}
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Card width of 380-420px works best for testimonials
- Use `lyf-glass` styling on each card
- `offset` of 10-15px and `scaleFactor` of 0.04-0.06 for premium depth
- Add swipe instruction text on mobile: "Swipe to read more"
- For GHL: test touch events inside the iframe

## Performance Notes

- framer-motion handles spring animations for card transitions
- Only renders visible cards + 2 behind
- Gesture handlers are throttled
