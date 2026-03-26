---
name: loading-carousel
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/loading-carousel
category: components
tags: loading, carousel, skeleton, transition, waiting, animated
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# LoadingCarousel

> Animated loading state with rotating carousel content to keep users engaged during waits.

## When to Use
- Long-running API calls or data processing waits
- SaaS dashboard initial load with rotating tip slides
- File upload progress with informational carousel
- AI processing states with feature highlights
- Payment processing wait screens

## When NOT to Use
- Quick loads under 2 seconds (use a simple spinner)
- Background processes that don't block the user
- When loading state is uncertain in duration (use progress bar)

## Pairs Well With
- `shimmer-button` - Shimmer effect on "Processing..." button state
- `number-ticker` - Animated progress percentage display
- `blur-text` - Blur-reveal text for each carousel tip
- `animated-content` - Smooth transitions between carousel items

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | { title: string; description: string; icon?: ReactNode }[] | [] | Carousel content items |
| interval | number | 3000 | Rotation interval in ms |
| showProgress | boolean | true | Show loading progress bar |
| progress | number | undefined | Controlled progress (0-100) |
| animation | 'slide' \| 'fade' \| 'flip' | 'fade' | Transition animation |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/loading-carousel"
```

## Usage Example
```jsx
import { LoadingCarousel } from "@/components/ui/loading-carousel";

const loadingTips = [
  { title: "Setting Up Your Dashboard", description: "Configuring personalized analytics views..." },
  { title: "Syncing Patient Records", description: "Importing data from your existing systems..." },
  { title: "Optimizing Workflows", description: "Applying AI-powered scheduling optimization..." },
];

export function SetupLoading() {
  return (
    <div className="min-h-screen bg-[#0a0a0a] flex items-center justify-center">
      <div className="lyf-glass rounded-[12px] p-12 max-w-md w-full text-center">
        <LoadingCarousel
          items={loadingTips}
          interval={4000}
          showProgress={true}
          animation="fade"
        />
      </div>
    </div>
  );
}
```

## Lyfework Customization Notes
- Progress bar: brand gradient from-[#ff642a] to-[#ff0301]
- Container: lyf-glass with 12px radius on #0a0a0a background
- Titles: Manrope 700, descriptions: Manrope 400 text-white/60
- Use clinic/SaaS-relevant tip content during loading states
- GHL compatible for form submission processing screens

## Performance Notes
- Lightweight Framer Motion transitions between items
- Only current item is rendered; others are unmounted
- Progress bar uses CSS width transition (no JS per frame)
- Auto-rotation uses setInterval with cleanup on unmount
- Total component weight is under 3KB gzipped
