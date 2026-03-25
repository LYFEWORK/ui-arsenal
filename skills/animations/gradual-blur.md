---
name: gradual-blur
source: ReactBits
source_url: https://reactbits.dev/animations/gradual-blur
category: animations
tags: blur, scroll, progressive, depth, focus, elegant
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GradualBlur

> Content progressively blurs or unblurs as the user scrolls. Creates a depth-of-field effect where content sharpens into focus at a specific scroll position.

## When to Use

- Hero sections where content sharpens as user scrolls down
- Section transitions that create a cinematic rack-focus feel
- Background images that blur as foreground content enters
- Storytelling layouts where progressive reveal matters
- Any scroll-based experience that needs a premium, filmic quality

## When NOT to Use

- Content that needs to be immediately readable
- Short pages with no scroll depth
- Mobile layouts where scroll behavior is quick and choppy
- Pages with many competing animations

## Pairs Well With

- `split-text` - Text splits into view as background un-blurs
- `animated-content` - Content fades in while GradualBlur sharpens the surroundings
- `aurora` - Aurora background that sharpens into focus on scroll
- `particles` - Particle field that comes into focus as user scrolls

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to blur/unblur |
| blurStart | number | 10 | Starting blur amount in px |
| blurEnd | number | 0 | Ending blur amount in px |
| scrollStart | number | 0 | Scroll position where blur starts changing |
| scrollEnd | number | 300 | Scroll position where blur finishes |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GradualBlur-TS-TW
```

## Usage Example

```jsx
import GradualBlur from '@/components/ui/GradualBlur';

function CinematicHero() {
  return (
    <section className="relative min-h-[150vh]">
      <GradualBlur blurStart={12} blurEnd={0} scrollStart={0} scrollEnd={400}>
        <div className="sticky top-0 h-screen flex items-center justify-center">
          <img src="/hero-bg.jpg" className="absolute inset-0 w-full h-full object-cover" />
          <h1 className="relative z-10 text-6xl font-extrabold text-white">Clarity Through Infrastructure.</h1>
        </div>
      </GradualBlur>
    </section>
  );
}
```

## Lyfework Customization Notes

- `blurStart` of 8-15px for noticeable blur. Above 20 is too opaque.
- The unblur should complete within 300-500px of scroll distance
- Best used on hero sections with a sticky background image
- Pair with `opacity` transition for a combined blur + fade effect
- Works in GHL if using CSS-only implementation (scroll-linked blur via IntersectionObserver)

## Performance Notes

- CSS `filter: blur()` is GPU accelerated
- Scroll listener should be throttled via requestAnimationFrame
- framer-motion useScroll hook handles this efficiently
- Test on mobile (blur filter can be heavy on older phones)
