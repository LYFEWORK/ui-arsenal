---
name: count-up
source: ReactBits
source_url: https://reactbits.dev/text-animations/count-up
category: text-animations
tags: number, counter, stats, metrics, scroll-trigger, animation
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# CountUp

> Animates a number from 0 to a target value with easing. Triggers on scroll into view. The standard way to make stats and metrics feel dynamic.

## When to Use

- Stats/metrics sections ("500+ Clients", "98% Retention", "$2.4M Revenue Managed")
- Dashboard KPIs on landing pages
- Social proof numbers (reviews, customers, years in business)
- Any numerical value that benefits from animated entrance

## When NOT to Use

- Numbers that change in real-time (use live data binding instead)
- Prices or costs (animation feels gimmicky on pricing)
- Sequential numbers (step 1, 2, 3) where the count-up adds no meaning
- More than 4-6 counters on screen at once

## Pairs Well With

- `spotlight-card` - Each stat inside a spotlight card
- `animated-content` - Wrap the stats section, CountUp triggers after scroll reveal
- `particles` - Stats section over a subtle particle background
- `gradient-text` - The number in gradient, the label in white

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| to | number | 0 | Target number to count to |
| from | number | 0 | Starting number |
| duration | number | 2 | Animation duration in seconds |
| separator | string | "," | Thousands separator |
| prefix | string | "" | Text before number ("$", "#") |
| suffix | string | "" | Text after number ("+", "%", "k") |
| decimals | number | 0 | Decimal places |
| trigger | "scroll" \| "load" | "scroll" | When to start counting |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/CountUp-TS-TW
```

## Usage Example

```jsx
import CountUp from '@/components/ui/CountUp';
import SpotlightCard from '@/components/ui/SpotlightCard';
import AnimatedContent from '@/components/ui/AnimatedContent';

function StatsSection() {
  const stats = [
    { value: 500, suffix: '+', label: 'Clients Served' },
    { value: 98, suffix: '%', label: 'Retention Rate' },
    { value: 30, suffix: ' days', label: 'Average Install' },
    { value: 2.4, suffix: 'M', prefix: '$', decimals: 1, label: 'Revenue Managed' },
  ];

  return (
    <section className="py-24 px-8">
      <div className="grid grid-cols-2 md:grid-cols-4 gap-6 max-w-5xl mx-auto">
        {stats.map((stat, i) => (
          <AnimatedContent key={i} direction="up" delay={i * 0.1}>
            <SpotlightCard className="p-8 text-center rounded-2xl">
              <CountUp
                to={stat.value}
                suffix={stat.suffix}
                prefix={stat.prefix || ''}
                decimals={stat.decimals || 0}
                duration={2.5}
                className="text-4xl font-extrabold text-white"
              />
              <p className="mt-2 text-sm text-gray-400">{stat.label}</p>
            </SpotlightCard>
          </AnimatedContent>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Duration of 2-3 seconds for stats sections. Feels satisfying without being slow.
- Always use scroll trigger for stats (nobody sees the animation if it fires on page load off-screen)
- For Lyfework brand numbers, use Manrope 800 at a large size (text-4xl or text-5xl)
- Pair each counter with a short, punchy label below it
- For GHL: ensure the scroll trigger intersection observer works inside the GHL iframe

## Performance Notes

- Lightweight, just a number interpolation on requestAnimationFrame
- IntersectionObserver for scroll trigger (native API)
- No DOM thrashing, just text content updates
- SSR safe (renders target number statically, animates on client)
