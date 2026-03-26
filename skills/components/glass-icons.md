---
name: glass-icons
source: ReactBits
source_url: https://reactbits.dev/components/glass-icons
category: components
tags: glass, icons, glassmorphism, blur, premium, container
dependencies: none
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# GlassIcons

> Glassmorphism-styled icon containers with frosted backgrounds, subtle borders, and optional hover glow. Wraps any icon in a translucent, premium-feeling glass pill or square. Pure CSS, no animation library needed.

## When to Use

- Feature grids where each feature has an icon that needs visual weight
- Social media icon rows in footers or headers
- Dashboard sidebar icon navigation with glass-style buttons
- Service listing cards where each service icon needs a container
- Any icon set on a dark background that needs to feel elevated and polished

## When NOT to Use

- Light backgrounds where glass effect washes out
- Dense icon toolbars where glass containers add too much padding
- Inline text icons that need to flow with typography
- Minimal designs where icon containers add unnecessary visual complexity

## Pairs Well With

- `spotlight-card` - Glass icons inside a spotlight card for feature sections
- `gradient-text` - Gradient label text next to glass icon containers
- `animated-content` - Scroll-reveal glass icon grids
- `count-up` - Glass icon container next to animated stat numbers

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| icon | ReactNode | required | Icon component or element |
| size | "sm" \| "md" \| "lg" | "md" | Container size (32/48/64px) |
| shape | "circle" \| "square" \| "pill" | "circle" | Container shape |
| glowColor | string | "rgba(255,100,42,0.15)" | Hover glow color |
| blur | number | 12 | Backdrop blur intensity in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GlassIcons-TS-TW
```

## Usage Example

```jsx
import GlassIcons from '@/components/ui/GlassIcons';
import { Zap, Bot, BarChart3, Globe } from 'lucide-react';

function FeaturesSection() {
  const features = [
    { icon: <Zap size={24} />, title: 'Fast Setup', desc: 'Live in 30 days, not 6 months.' },
    { icon: <Bot size={24} />, title: 'AI-Native', desc: 'Automation from day one.' },
    { icon: <BarChart3 size={24} />, title: 'Full Analytics', desc: 'Every metric, one dashboard.' },
    { icon: <Globe size={24} />, title: 'Scalable Infra', desc: 'Grows with your practice.' },
  ];

  return (
    <section className="py-24 px-8 bg-[#0a0a0a]">
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8 max-w-6xl mx-auto">
        {features.map((f, i) => (
          <div key={i} className="lyf-glass rounded-xl p-8 text-center">
            <GlassIcons
              icon={f.icon}
              size="lg"
              shape="circle"
              glowColor="rgba(255,100,42,0.12)"
              className="mx-auto text-[#ff642a]"
            />
            <h3 className="mt-5 text-lg font-bold text-white font-[Manrope]">{f.title}</h3>
            <p className="mt-2 text-sm text-gray-400">{f.desc}</p>
          </div>
        ))}
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Icon color: `text-[#ff642a]` Lyfework orange for brand consistency
- Glow color: `rgba(255,100,42,0.12)` for subtle on-hover brand glow
- Container bg: `rgba(255,255,255,0.04)` with `border: 1px solid rgba(255,255,255,0.06)`
- Pair with Lucide icons (already in most Lyfework projects) for consistent icon style
- Font: `Manrope` 700 for feature titles next to the glass icons
- GHL compatible -- pure CSS glass effect with no JS dependencies

## Performance Notes

- Pure CSS `backdrop-filter: blur()` for the glass effect, no JS overhead
- Hover glow uses CSS `box-shadow` transition, hardware-accelerated
- No animation library needed; transitions are CSS-only
- Works on all modern browsers; falls back to solid semi-transparent bg on older ones
- Lightweight component; safe to render 20+ instances on a single page
