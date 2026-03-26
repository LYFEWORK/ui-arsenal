---
name: feature-carousel
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/feature-carousel
category: components
tags: carousel, features, showcase, slider, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# FeatureCarousel

> Animated feature showcase carousel with auto-play, drag, and keyboard navigation.

## When to Use
- SaaS feature highlight sections with multiple product capabilities
- Portfolio project showcases with swipeable cards
- Service offering carousels for clinic or agency sites
- Product screenshot walkthroughs with descriptions
- Mobile-friendly feature browsing on narrow viewports

## When NOT to Use
- When fewer than 3 features exist (use a grid instead)
- Critical content that must all be visible without interaction
- Pages where carousel interaction may reduce conversion

## Pairs Well With
- `spotlight-card` - Feature cards with spotlight hover inside carousel
- `animated-content` - Staggered entrance of carousel items
- `shimmer-button` - "Learn More" shimmer buttons on each feature card
- `gradient-text` - Gradient feature titles within carousel slides

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | { title: string; description: string; icon?: ReactNode; image?: string }[] | [] | Feature items |
| autoPlay | boolean | true | Enable auto-advance |
| interval | number | 5000 | Auto-play interval in ms |
| showDots | boolean | true | Show pagination dots |
| showArrows | boolean | true | Show navigation arrows |
| draggable | boolean | true | Enable drag/swipe |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/feature-carousel"
```

## Usage Example
```jsx
import { FeatureCarousel } from "@/components/ui/feature-carousel";

const features = [
  {
    title: "Smart Scheduling",
    description: "AI-powered appointment booking that reduces no-shows by 60%.",
    image: "/features/scheduling.png",
  },
  {
    title: "Patient Portal",
    description: "Self-service portal for intake forms, records, and messaging.",
    image: "/features/portal.png",
  },
  {
    title: "Analytics Dashboard",
    description: "Real-time insights into practice performance and patient flow.",
    image: "/features/analytics.png",
  },
];

export function FeaturesSection() {
  return (
    <section className="bg-[#0a0a0a] py-24 px-6">
      <h2 className="font-manrope font-800 text-4xl text-white text-center mb-16">
        Everything You Need
      </h2>
      <FeatureCarousel
        items={features}
        autoPlay={true}
        interval={6000}
        draggable={true}
        className="max-w-5xl mx-auto"
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Feature cards: lyf-glass background, 12px radius, Manrope 700 titles
- Dot indicators: brand gradient active state from-[#ff642a] to-[#ff0301]
- Arrow buttons: white/20 with hover white/40 on #0a0a0a background
- Swipe gestures work naturally in GHL mobile views
- Image slides should be 16:9 or 4:3 for consistent carousel height

## Performance Notes
- Framer Motion drag uses GPU-accelerated transforms
- Only visible slide + adjacent slides are rendered (virtual sliding)
- Images use loading="lazy" except the first visible slide
- Auto-play pauses when tab is not visible (Page Visibility API)
- Touch events are passive for smooth mobile scrolling
