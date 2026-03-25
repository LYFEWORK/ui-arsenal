---
name: blur-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/blur-text
category: text-animations
tags: text, reveal, blur, hero, headline, entrance, framer-motion
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# BlurText

> Text that reveals itself by animating from blurred to sharp, word by word or character by character.

## When to Use

- Hero section headlines on landing pages
- Section titles that enter viewport on scroll
- Any headline that needs a premium entrance effect
- First-impression text that needs to feel polished and intentional
- Client websites where the hero needs to feel alive, not static

## When NOT to Use

- Body copy or paragraphs (too distracting for reading)
- Repeated elements in a list (animation becomes noise)
- Text that needs to be immediately readable (form labels, nav items)
- Pages with many animated elements already (visual overload)

## Pairs Well With

- `aurora` - Blurred text over animated aurora background for hero sections
- `fade-content` - Stagger the BlurText first, then fade in supporting content below
- `gradient-text` - Apply gradient color to the text after blur reveal completes
- `particles` - Subtle particle background behind blur-revealing headline

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | The text content to animate |
| delay | number | 200 | Delay in ms between each word/character animation |
| animateBy | "words" \| "characters" | "words" | Animate per word or per character |
| direction | "top" \| "bottom" | "top" | Direction the text enters from |
| className | string | "" | Additional CSS classes for styling |
| onAnimationComplete | function | undefined | Callback when animation finishes |

## Installation

```bash
npx shadcn@latest add @react-bits/BlurText-TS-TW
```

## Usage Example

```jsx
import BlurText from '@/components/ui/BlurText';

function HeroSection() {
  return (
    <section className="relative min-h-screen flex items-center justify-center">
      <div className="text-center">
        <BlurText
          text="Your Clinic Runs Itself."
          delay={150}
          animateBy="words"
          direction="top"
          className="text-5xl md:text-7xl font-extrabold text-white"
        />
        <BlurText
          text="We build the system. You run the business."
          delay={100}
          animateBy="words"
          direction="bottom"
          className="mt-6 text-xl text-gray-400"
        />
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use with Manrope 800 weight for hero headlines
- Set `animateBy="words"` for headlines (smoother), `animateBy="characters"` only for short punchy lines
- Delay of 120-180ms feels premium. Below 100ms feels rushed. Above 250ms feels slow.
- On dark Lyfework backgrounds (#0a0a0a), use white text with this animation
- For GHL funnel pages: wrap in a div with `opacity: 1` to prevent FOUC
- Chain with `onAnimationComplete` to trigger next element animations

## Performance Notes

- Requires framer-motion (adds ~30kb gzipped)
- Performant on mobile, uses CSS transforms and opacity
- No layout shift, elements are positioned before animation starts
- SSR compatible with Next.js (animates on hydration)
