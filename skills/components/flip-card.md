---
name: flip-card
source: ReactBits
source_url: https://reactbits.dev/components/flip-card
category: components
tags: card, flip, 3d, hover, two-sided, reveal
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# FlipCard

> A card that flips to reveal back content on hover or click. Full 3D CSS transform with perspective. Front and back are independently styled.

## When to Use

- Team member cards (photo on front, bio on back)
- Service cards (icon/title on front, details on back)
- FAQ-style content (question on front, answer on back)
- Before/after comparisons
- Any card where you want to pack more info without expanding the layout

## When NOT to Use

- Critical content that shouldn't be hidden behind an interaction
- Mobile-first designs where hover flip doesn't exist (use click trigger)
- Cards in dense grids where accidental hovers cause visual chaos
- Content that users need to scan quickly

## Pairs Well With

- `animated-content` - Scroll reveal the grid, then cards flip on hover
- `gradient-text` - Gradient title on the front face
- `glow-card` - Glow border on the front, content on the back

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| front | ReactNode | required | Front face content |
| back | ReactNode | required | Back face content |
| direction | "horizontal" \| "vertical" | "horizontal" | Flip axis |
| trigger | "hover" \| "click" | "hover" | What triggers the flip |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FlipCard-TS-TW
```

## Usage Example

```jsx
import FlipCard from '@/components/ui/FlipCard';

function TeamGrid() {
  return (
    <FlipCard
      direction="horizontal"
      trigger="hover"
      front={
        <div className="h-80 bg-cover bg-center rounded-2xl" style={{ backgroundImage: 'url(/team/sarah.jpg)' }}>
          <div className="absolute bottom-0 p-6 bg-gradient-to-t from-black/80">
            <h3 className="text-xl font-bold text-white">Sarah Chen</h3>
            <p className="text-sm text-gray-300">Operations Lead</p>
          </div>
        </div>
      }
      back={
        <div className="h-80 lyf-glass rounded-2xl p-8 flex flex-col justify-center">
          <p className="text-white">10+ years scaling clinic operations across 3 states.</p>
          <a href="#" className="mt-4 text-orange-400 font-bold">Connect</a>
        </div>
      }
    />
  );
}
```

## Lyfework Customization Notes

- Always use `trigger="click"` on mobile (add media query detection)
- Front face: bold visuals. Back face: `lyf-glass` with text content.
- `direction="horizontal"` for team cards, `"vertical"` for service/feature cards
- Add `rounded-2xl` to match Lyfework border radius standard
- Works in GHL with CSS 3D transforms

## Performance Notes

- Pure CSS transforms, zero JavaScript for the flip animation
- `backface-visibility: hidden` prevents content bleed
- No performance concerns even with 12+ cards
