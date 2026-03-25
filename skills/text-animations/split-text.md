---
name: split-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/split-text
category: text-animations
tags: text, split, stagger, reveal, entrance, gsap, scroll-trigger
dependencies: gsap, @gsap/react
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# SplitText

> Splits text into individual characters or words and animates each one with staggered timing. Uses GSAP for buttery smooth scroll-triggered or on-load animations.

## When to Use

- Section headlines that animate as user scrolls into view
- Subheadings that need a more dramatic entrance than a simple fade
- Quote or testimonial text that builds character by character
- Any text block where you want the reader's eye to follow the animation left to right
- Scroll-triggered reveals throughout a long-scroll page

## When NOT to Use

- Multiple instances on the same viewport (competing animations)
- Very long paragraphs (animation takes too long to complete)
- Navigation text or UI labels
- Text that updates dynamically (animation replays become annoying)

## Pairs Well With

- `animated-content` - SplitText the heading, AnimatedContent the body paragraph below
- `spotlight-card` - Animate the card title with SplitText inside a SpotlightCard
- `fade-content` - Chain SplitText headline with fading body copy

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text content to split and animate |
| splitBy | "characters" \| "words" \| "lines" | "characters" | How to split the text |
| staggerDelay | number | 0.05 | Delay between each element in seconds |
| duration | number | 0.6 | Animation duration per element |
| ease | string | "power2.out" | GSAP easing function |
| trigger | "scroll" \| "load" | "scroll" | When to trigger animation |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/SplitText-TS-TW
```

## Usage Example

```jsx
import SplitText from '@/components/ui/SplitText';

function FeatureSection() {
  return (
    <section className="py-24 px-8">
      <SplitText
        text="Built Different. By Design."
        splitBy="characters"
        staggerDelay={0.03}
        duration={0.5}
        ease="power3.out"
        trigger="scroll"
        className="text-4xl md:text-6xl font-extrabold text-white tracking-tight"
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- For Lyfework hero text: use `splitBy="words"` with `staggerDelay={0.08}`
- For accent/detail text: use `splitBy="characters"` with `staggerDelay={0.02}`
- GSAP ScrollTrigger should start at `top 80%` for natural reveal timing
- Always pair with Manrope 800 for headlines, 700 for subheads
- Keep total animation time under 1.5 seconds for the full text block
- For GHL: ensure GSAP is loaded via CDN in the page header, not per-section

## Performance Notes

- GSAP is performant but adds ~25kb gzipped
- ScrollTrigger adds another ~10kb
- For pages with many scroll animations, load GSAP once globally
- Uses `will-change: transform, opacity` internally for GPU acceleration
- Works well on mobile, but reduce stagger count on very long text for battery
