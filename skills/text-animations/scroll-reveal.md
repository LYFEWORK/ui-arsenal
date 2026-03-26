---
name: scroll-reveal
source: ReactBits
source_url: https://reactbits.dev/text-animations/scroll-reveal
category: text-animations
tags: text, scroll, reveal, progressive, reading, entrance, highlight
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# ScrollReveal

> Text revealed progressively as the user scrolls, with each word or line lighting up from muted to full opacity, guiding the reader through content at their own pace.

## When to Use

- Long-form storytelling sections where you want to pace the reading
- Mission statements or brand stories that unfold as the user scrolls
- Feature explanation blocks where each line appears naturally
- Testimonial or quote sections that build dramatic emphasis with scroll
- Any text-heavy section that benefits from guided reading flow

## When NOT to Use

- Short headlines that should be visible immediately
- Navigation, form labels, or any interactive text
- Pages where content needs to be scannable at a glance
- Very short sections where the scroll distance is insufficient for the effect

## Pairs Well With

- `split-text` - SplitText for the section header, ScrollReveal for the body below
- `blur-text` - BlurText entrance for the title, then ScrollReveal for supporting copy
- `animated-content` - AnimatedContent wrapper with ScrollReveal text inside
- `gradient-text` - Highlighted words in gradient as they scroll into full reveal

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text content to progressively reveal |
| revealBy | "words" \| "lines" | "words" | Unit of progressive reveal |
| baseOpacity | number | 0.15 | Starting opacity of unrevealed text |
| scrollStart | string | "top 90%" | ScrollTrigger start position |
| scrollEnd | string | "top 30%" | ScrollTrigger end position |
| highlightColor | string | undefined | Optional color for the currently revealing word |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ScrollReveal-TS-TW
```

## Usage Example

```jsx
import ScrollReveal from '@/components/ui/ScrollReveal';

function BrandStorySection() {
  return (
    <section className="py-32 px-8 bg-[#0a0a0a]">
      <div className="max-w-3xl mx-auto">
        <h2 className="text-4xl font-extrabold text-white mb-12" style={{ fontFamily: 'Manrope, sans-serif' }}>
          Our Story
        </h2>
        <ScrollReveal
          text="We started Lyfework because we saw clinics drowning in admin work. Talented doctors spending more time on spreadsheets than patients. We believed technology should handle the busywork so providers can do what they do best: care for people."
          revealBy="words"
          baseOpacity={0.12}
          scrollStart="top 85%"
          scrollEnd="top 25%"
          className="text-2xl md:text-3xl text-white/90 font-bold leading-relaxed"
          style={{ fontFamily: 'Manrope, sans-serif' }}
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use Manrope 700 at `text-2xl` or `text-3xl` for scroll-revealed body text
- Set `baseOpacity={0.10-0.15}` on #0a0a0a backgrounds so muted text is barely visible
- Use `highlightColor` set to `#ff642a` to make the currently-revealing word pop in brand orange
- `scrollStart="top 85%"` and `scrollEnd="top 25%"` gives a comfortable reveal pace
- For clinic brand story sections, pair with a subtle `lyf-glass` container for depth
- For GHL: framer-motion requires React; use IntersectionObserver-based fallback for pure HTML funnels

## Performance Notes

- Framer-motion's `useScroll` and `useTransform` are highly optimized for scroll-linked animation
- Each word is a separate `<span>`, keep text under 100 words to avoid excessive DOM nodes
- Uses `opacity` transitions only, fully GPU-composited with no layout recalculations
- No memory leaks, scroll listeners are cleaned up on unmount automatically
- Mobile-friendly, scroll-linked animations feel native on touch devices
