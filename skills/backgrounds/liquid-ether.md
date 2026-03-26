---
name: liquid-ether
source: ReactBits
source_url: https://reactbits.dev/backgrounds/liquid-ether
category: backgrounds
tags: background, liquid, ether, flow, ambient, organic, dreamy
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# LiquidEther

> An ethereal liquid flowing ambient background with soft, dreamy color transitions. Creates a calming, organic atmosphere that feels like underwater light or cosmic gas.

## When to Use

- Hero sections for wellness, spa, or health-related client sites
- Ambient backgrounds for meditation, yoga, or mindfulness products
- SaaS pages targeting creative or design-focused audiences
- Behind testimonials or quotes where a calming atmosphere enhances the message
- Portfolio hero sections for a dreamy, artistic entrance

## When NOT to Use

- High-energy, conversion-heavy landing pages (too calm and dreamy)
- Corporate or enterprise SaaS pages (feels too soft for B2B)
- Pages with hard, geometric design elements (aesthetic conflict)
- When fast page load is critical (canvas rendering has weight)

## Pairs Well With

- `blur-text` - Text blurring in over ethereal liquid feels magical and dreamlike
- `animated-content` - Content gently appearing over the flowing ether
- `gradient-text` - Soft gradient text matches the ether's fluid color transitions
- `split-text` - Slow text reveal over the liquid background for scroll-based sections

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| colors | string[] | ["#4a00e0","#8e2de2","#00d2ff"] | Color palette for the ether |
| speed | number | 0.3 | Flow speed of the ether animation |
| complexity | number | 3 | Number of overlapping fluid layers |
| opacity | number | 0.6 | Overall opacity of the effect |
| blur | number | 40 | Blur amount applied to the fluid shapes |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LiquidEther-TS-TW
```

## Usage Example

```jsx
import LiquidEther from '@/components/ui/LiquidEther';
import BlurText from '@/components/ui/BlurText';

function WellnessHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0">
        <LiquidEther
          colors={['#1a0a2e', '#ff642a40', '#ff030120']}
          speed={0.2}
          complexity={3}
          opacity={0.5}
          blur={50}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Heal. Restore. Thrive."
          delay={200}
          animateBy="words"
          className="text-4xl md:text-6xl font-bold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-300 max-w-xl mx-auto font-[Manrope]">
          Holistic wellness designed around your body's natural rhythms.
        </p>
        <a
          href="#booking"
          className="mt-8 inline-block px-8 py-4 rounded-xl bg-white/10 backdrop-blur-md border border-white/20 text-white font-bold font-[Manrope]"
        >
          Begin Your Journey
        </a>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework ether: `['#1a0a2e', '#ff642a40', '#ff030120']` for muted brand tones in an organic flow
- For wellness clients: use soft purples, teals, and blues at 30-50% opacity
- `speed` of 0.15-0.3 feels meditative. Above 0.5 starts feeling chaotic.
- `blur` of 40-60 keeps the fluid shapes soft and ambient. Below 20 shows hard edges.
- The `lyf-glass` button style (backdrop-blur + semi-transparent) pairs perfectly with this background
- GHL: can be approximated with multiple blurred, animated gradient circles using CSS
- `complexity` of 2-4 is optimal. Above 5 adds rendering cost without visual benefit.

## Performance Notes

- Uses CSS filter blur on animated gradient elements
- More performant than WebGL alternatives but still has GPU cost from blur
- Reduce `complexity` and increase `blur` on mobile for better performance
- Consider using `will-change: transform` on the fluid elements
- SSR-compatible, renders a static gradient and animates on client
