---
name: number-ticker
source: Magic UI
source_url: https://magicui.design/docs/components/number-ticker
category: text-animations
tags: number, counter, ticker, stats, animation
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# NumberTicker

> Rolling digit counter animation that ticks up to a target number, perfect for stats and metrics.

## When to Use
- Stats sections showing key metrics (users, revenue, uptime)
- Social proof numbers ("10,000+ clinics served")
- Dashboard metric displays with animated values
- Achievement or milestone showcases
- Pricing page feature quantity displays

## When NOT to Use
- Real-time updating numbers (use a live counter instead)
- Small inline numbers within paragraphs
- When the target number is 0 or 1 (no visual effect)
- Contexts where animation delays critical information

## Pairs Well With
- `count-up` - Alternative counter from the arsenal — choose one per project
- `animated-content` - Trigger ticker when section scrolls into view
- `gradient-text` - Gradient text on the stat label
- `spotlight-card` - Stats inside spotlight-hover cards

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| value | number | required | Target number to count to |
| direction | "up" \| "down" | "up" | Count direction |
| delay | number | 0 | Delay before animation starts (seconds) |
| decimalPlaces | number | 0 | Number of decimal places to display |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/number-ticker"
```

## Usage Example
```jsx
import { NumberTicker } from "@/components/magicui/number-ticker";

const stats = [
  { value: 1200, label: "Clinics powered" },
  { value: 98.7, label: "Uptime %", decimals: 1 },
  { value: 40, label: "Less no-shows", suffix: "%" },
  { value: 2, label: "Million appointments", suffix: "M+" },
];

export function StatsSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <div className="mx-auto max-w-5xl grid grid-cols-2 md:grid-cols-4 gap-8 px-6">
        {stats.map((s, i) => (
          <div key={s.label} className="text-center">
            <div className="font-manrope font-800 text-4xl text-white">
              <NumberTicker value={s.value} delay={i * 0.2} decimalPlaces={s.decimals || 0} />
              {s.suffix && <span>{s.suffix}</span>}
            </div>
            <p className="font-manrope font-400 text-white/50 mt-2">{s.label}</p>
          </div>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Use Manrope font-800 for the animated numbers, font-400 for labels
- Add brand gradient text on specific stat values for emphasis
- Stagger delays across multiple tickers for a cascading reveal effect
- Stat labels should reflect Lyfework metrics (clinics, appointments, uptime)
- GHL compatible — standard DOM text animation via Framer Motion

## Performance Notes
- Framer Motion spring animation — single animation per ticker
- Each digit rolls independently — efficient per-character animation
- Animation triggers once (on mount or intersection) — no continuous loop
- Stagger delays prevent simultaneous heavy animation
- Decimal place formatting is computed, not animated digit-by-digit
