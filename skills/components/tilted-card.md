---
name: tilted-card
source: ReactBits
source_url: https://reactbits.dev/components/tilted-card
category: components
tags: card, tilt, hover, 3d, interactive, image, portfolio
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# TiltedCard

> A card that responds to mouse movement with a 3D tilt effect. Creates depth and interactivity on hover. Perfect for portfolios, team grids, and feature showcases.

## When to Use

- Service or feature card grids where each card needs presence
- Team member cards or client logo showcases
- Portfolio pieces or case study thumbnails
- Any image-forward card layout that needs to feel premium and interactive
- Pricing cards where you want to draw attention to each tier

## When NOT to Use

- Dense data layouts (tables, dashboards) where interaction would distract
- Cards with complex interactive content inside (forms, dropdowns)
- Mobile-first designs where hover isn't available (add tap fallback)
- More than 6-8 cards on screen at once (too much visual noise)

## Pairs Well With

- `animated-content` - Scroll-reveal TiltedCards into view, then they respond to hover
- `spotlight-card` - Alternative card style for variety in the same build
- `click-spark` - Add spark effect on card click for extra delight
- `gradient-text` - Gradient text inside the card for the title

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| imageSrc | string | "" | Image URL for the card |
| captionText | string | "" | Text overlay on the card |
| containerHeight | string | "300px" | Card height |
| containerWidth | string | "100%" | Card width |
| imageHeight | string | "300px" | Image height within card |
| imageWidth | string | "100%" | Image width within card |
| rotateAmplitude | number | 12 | Max tilt rotation in degrees |
| scaleOnHover | number | 1.05 | Scale multiplier on hover |
| showMobileWarning | boolean | false | Show hover warning on mobile |
| showTooltip | boolean | true | Show tooltip on hover |
| displayOverlayContent | boolean | false | Show custom overlay content |
| overlayContent | ReactNode | null | Custom overlay JSX |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/TiltedCard-TS-TW
```

## Usage Example

```jsx
import TiltedCard from '@/components/ui/TiltedCard';
import AnimatedContent from '@/components/ui/AnimatedContent';

function ServicesGrid() {
  const services = [
    { title: 'Website Build', image: '/img/service-web.jpg' },
    { title: 'Lyfework IO Setup', image: '/img/service-io.jpg' },
    { title: 'AI Integration', image: '/img/service-ai.jpg' },
  ];

  return (
    <section className="py-24 px-8">
      <div className="grid grid-cols-1 md:grid-cols-3 gap-10">
        {services.map((svc, i) => (
          <AnimatedContent key={i} direction="up" delay={i * 0.15}>
            <TiltedCard
              imageSrc={svc.image}
              captionText={svc.title}
              containerHeight="380px"
              rotateAmplitude={10}
              scaleOnHover={1.04}
              showMobileWarning={false}
              className="rounded-2xl overflow-hidden"
            />
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- `rotateAmplitude` of 8-12 feels premium. Above 15 feels gimmicky.
- `scaleOnHover` of 1.03-1.06 is the sweet spot. Subtle, not dramatic.
- Always pair with `rounded-2xl` for Lyfework's border radius standard
- On dark backgrounds, add a subtle `lyf-shadow` class to the card
- For GHL builds: wrap in a standard div container. The 3D transform uses `perspective` which works fine in GHL's iframe.
- Caption text should use Manrope 700, white, with a dark gradient overlay on the image bottom

## Performance Notes

- Uses CSS transforms (GPU accelerated)
- Mouse tracking is throttled internally by framer-motion
- No performance issues with 6-9 cards on screen
- For 12+ cards, consider virtualizing or lazy-loading off-screen cards
- Mobile degrades gracefully (no tilt, just the static card with scale on tap)
