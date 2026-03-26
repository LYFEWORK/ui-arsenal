---
name: intro-disclosure
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/intro-disclosure
category: components
tags: disclosure, progressive, intro, tutorial, reveal, onboarding
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# IntroDisclosure

> Progressive disclosure intro/tutorial pattern that reveals content in digestible stages.

## When to Use
- Product introduction pages revealing features progressively
- Complex service explanations broken into digestible steps
- Interactive storytelling sections on landing pages
- Tutorial or how-it-works sections with staged reveals
- SaaS onboarding explanations with visual progression

## When NOT to Use
- Simple content that doesn't benefit from staged reveal
- SEO-critical content that needs to be immediately crawlable
- Pages where users need all information upfront for decisions
- Mobile pages where progressive disclosure adds friction

## Pairs Well With
- `animated-content` - Each disclosed section animates in smoothly
- `blur-text` - Text blur-reveal within each disclosure stage
- `shimmer-button` - "Continue" or "Next" shimmer button between stages
- `spotlight-card` - Spotlight effect highlighting newly revealed content

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| sections | { title: string; content: ReactNode }[] | [] | Disclosure sections |
| trigger | 'scroll' \| 'click' \| 'auto' | 'scroll' | How sections are revealed |
| delay | number | 500 | Delay between auto-reveals in ms |
| animation | 'fade' \| 'slide' \| 'scale' | 'fade' | Reveal animation type |
| stagger | number | 200 | Stagger delay between items in ms |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/intro-disclosure"
```

## Usage Example
```jsx
import { IntroDisclosure } from "@/components/ui/intro-disclosure";

export function HowItWorks() {
  const sections = [
    {
      title: "1. Book Online",
      content: (
        <p className="font-manrope font-400 text-white/70">
          Choose your service and pick a time that works for you.
        </p>
      ),
    },
    {
      title: "2. Get Confirmed",
      content: (
        <p className="font-manrope font-400 text-white/70">
          Receive instant confirmation with all visit details.
        </p>
      ),
    },
    {
      title: "3. Visit & Thrive",
      content: (
        <p className="font-manrope font-400 text-white/70">
          Experience personalized care from our expert team.
        </p>
      ),
    },
  ];

  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-16">
        How It Works
      </h2>
      <IntroDisclosure
        sections={sections}
        trigger="scroll"
        animation="slide"
        stagger={300}
        className="max-w-2xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Section titles: Manrope 700, brand gradient numbers via gradient-text
- Body text: Manrope 400, text-white/70 on #0a0a0a
- Use scroll trigger for landing pages, click trigger for tutorials
- lyf-glass containers for each disclosure section
- GHL compatible with scroll-based triggers

## Performance Notes
- Framer Motion AnimatePresence mounts sections lazily on reveal
- IntersectionObserver used for scroll triggers -- no scroll event listeners
- Hidden sections are not in the DOM until triggered (saves initial render)
- Stagger delays are CSS-only via transition-delay
- Fully SSR-safe with graceful degradation to all-visible state
