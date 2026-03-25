---
name: gradient-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/gradient-text
category: text-animations
tags: text, gradient, color, animated, accent, headline
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# GradientText

> Applies an animated gradient color sweep across text. The gradient shifts continuously or on hover, creating a living, premium text effect.

## When to Use

- Brand name or product name in hero sections
- Accent words within a headline ("Your clinic runs on *autopilot*" where autopilot gets the gradient)
- Feature highlights or key differentiators
- Section headers that need visual weight without increasing font size
- Call-to-action text that needs to draw the eye

## When NOT to Use

- Full paragraphs (illegible and distracting)
- More than 2-3 gradient text instances per page (diminishing impact)
- On light backgrounds with light gradient colors (contrast issues)
- Body text or anything meant to be read quickly

## Pairs Well With

- `blur-text` - Blur reveal into gradient text for maximum hero impact
- `split-text` - Split animate into gradient for staggered color reveal
- `aurora` - Gradient text that echoes the aurora background colors

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display |
| colors | string[] | ["#ff642a", "#ff0301"] | Gradient color stops |
| animationSpeed | number | 8 | Speed of gradient animation in seconds |
| direction | "horizontal" \| "vertical" \| "diagonal" | "horizontal" | Gradient sweep direction |
| showBorder | boolean | false | Show gradient border around text |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GradientText-TS-TW
```

## Usage Example

```jsx
import GradientText from '@/components/ui/GradientText';

function HeroBrand() {
  return (
    <h1 className="text-5xl font-extrabold text-white">
      Powered by{' '}
      <GradientText
        text="Lyfework IO"
        colors={['#ff642a', '#ff0301', '#ff642a']}
        animationSpeed={6}
        direction="horizontal"
        className="inline"
      />
    </h1>
  );
}
```

## Lyfework Customization Notes

- Default Lyfework gradient colors: `['#ff642a', '#ff0301', '#ff642a']` (loops the brand gradient)
- Animation speed of 5-8 seconds feels premium. Faster feels cheap.
- Always use `direction="horizontal"` unless the layout specifically calls for vertical
- For the Lyfework brand name specifically, the gradient should match `--lyf-gradient` exactly
- Works on both dark and light backgrounds when colors are chosen correctly
- Pure CSS implementation, no JS animation library needed

## Performance Notes

- Zero JavaScript dependencies for the basic gradient animation
- Uses CSS `background-clip: text` and `background-size` animation
- Extremely lightweight, no performance concerns
- Works on all modern browsers, Safari needs `-webkit-background-clip`
- No SSR issues
