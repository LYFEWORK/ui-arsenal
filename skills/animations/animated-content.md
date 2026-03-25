---
name: animated-content
source: ReactBits
source_url: https://reactbits.dev/animations/animated-content
category: animations
tags: scroll, reveal, fade, entrance, wrapper, framer-motion
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# AnimatedContent

> A wrapper component that animates its children into view on scroll. The bread-and-butter reveal animation for any premium website build.

## When to Use

- Every section on a long-scroll landing page (this is the default entrance animation)
- Card grids, feature blocks, testimonials, pricing sections
- Any content block that enters the viewport and should feel alive
- Staggered reveals for lists of items (wrap each item separately with increasing delay)
- The go-to "make this section feel premium" solution

## When NOT to Use

- Above-the-fold hero content (should use BlurText or SplitText instead for more impact)
- Content that's already visible on page load
- Elements inside a component that already has its own animation (double animation)

## Pairs Well With

- `blur-text` - BlurText for the headline, AnimatedContent for everything else in the section
- `split-text` - Same pattern, different headline treatment
- `tilted-card` - Wrap TiltedCards in AnimatedContent for scroll-triggered card reveals
- `spotlight-card` - Reveal spotlight cards on scroll

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to animate |
| direction | "up" \| "down" \| "left" \| "right" | "up" | Direction content enters from |
| distance | number | 20 | Distance in pixels of the entrance slide |
| duration | number | 0.6 | Animation duration in seconds |
| delay | number | 0 | Delay before animation starts |
| threshold | number | 0.1 | Viewport intersection threshold (0-1) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/AnimatedContent-TS-TW
```

## Usage Example

```jsx
import AnimatedContent from '@/components/ui/AnimatedContent';

function FeaturesGrid() {
  const features = [
    { title: 'Automated Intake', desc: 'Patients book themselves.' },
    { title: 'Smart Routing', desc: 'Right provider, every time.' },
    { title: 'Follow-Up Engine', desc: 'No patient falls through.' },
  ];

  return (
    <section className="py-24 px-8">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
        {features.map((feature, i) => (
          <AnimatedContent
            key={i}
            direction="up"
            distance={30}
            duration={0.5}
            delay={i * 0.15}
          >
            <div className="lyf-glass p-8 rounded-2xl">
              <h3 className="text-xl font-bold text-white">{feature.title}</h3>
              <p className="mt-3 text-gray-400">{feature.desc}</p>
            </div>
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Default entrance: `direction="up"` with `distance={20}` for most sections
- Stagger cards by `delay={index * 0.12}` for a 3-column grid
- Stagger cards by `delay={index * 0.1}` for a 4-column grid
- Duration of 0.5-0.7 seconds is the sweet spot. Faster feels cheap, slower feels sluggish.
- For GHL pages: this component uses IntersectionObserver. Test that the GHL iframe doesn't interfere with scroll detection.
- Pair with `lyf-fade-in` class as a CSS-only fallback for non-React builds

## Performance Notes

- Uses IntersectionObserver (native browser API, very efficient)
- framer-motion handles GPU-accelerated transforms
- Each instance is independent, even with 20+ on a page performance stays solid
- Animations only trigger once by default (no re-animation on scroll back up)
- SSR safe with Next.js
