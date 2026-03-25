---
name: fade-content
source: ReactBits
source_url: https://reactbits.dev/animations/fade-content
category: animations
tags: fade, reveal, scroll, entrance, opacity, wrapper
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# FadeContent

> Simple opacity fade-in on scroll. No slide, no transform, just clean opacity transition. The most minimal entrance animation in the arsenal.

## When to Use

- Supporting content that should appear subtly (body text, captions, disclaimers)
- Secondary elements after a more dramatic primary animation has played
- Clean/minimal designs where AnimatedContent's slide feels like too much
- Staggered reveal of fine details (icons, labels, badges)
- Anywhere opacity-only entrance is more appropriate than slide + fade

## When NOT to Use

- Hero content (needs more impact, use BlurText or AnimatedContent)
- Section headlines (too subtle, won't register as intentional animation)

## Pairs Well With

- `blur-text` - BlurText headline, FadeContent for supporting body text
- `split-text` - SplitText headline, FadeContent body paragraph
- `animated-content` - AnimatedContent for primary elements, FadeContent for secondary

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Content to fade in |
| duration | number | 0.8 | Fade duration in seconds |
| delay | number | 0 | Delay before fade starts |
| threshold | number | 0.1 | Viewport intersection threshold |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FadeContent-TS-TW
```

## Usage Example

```jsx
import BlurText from '@/components/ui/BlurText';
import FadeContent from '@/components/ui/FadeContent';

function HeroSection() {
  return (
    <section className="py-32 text-center">
      <BlurText text="Your Clinic Runs Itself." delay={150} className="text-6xl font-extrabold text-white" />
      <FadeContent delay={1.2} duration={0.8}>
        <p className="mt-6 text-xl text-gray-400 max-w-xl mx-auto">
          We build the system. You run the business. That's it.
        </p>
      </FadeContent>
      <FadeContent delay={1.8} duration={0.6}>
        <button className="mt-10 px-8 py-4 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
          Book Your Install
        </button>
      </FadeContent>
    </section>
  );
}
```

## Lyfework Customization Notes

- Duration of 0.6-1.0s for body content. Slightly slower than AnimatedContent.
- Use `delay` to chain after headline animations (typically 1.0-2.0s after page load)
- The go-to for "everything else" after the headline has its dramatic entrance
- Works in GHL, uses IntersectionObserver + opacity transition

## Performance Notes

- Extremely lightweight (opacity animation only)
- GPU accelerated, no layout shifts
- SSR safe
