---
name: liquid-chrome
source: ReactBits
source_url: https://reactbits.dev/backgrounds/liquid-chrome
category: backgrounds
tags: background, liquid, chrome, metallic, flow, premium, WebGL
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# LiquidChrome

> A liquid metallic chrome flowing effect that creates a premium, hyper-realistic mercury/metal surface. The most visually striking background in the arsenal for high-impact hero sections.

## When to Use

- High-end product launch pages where premium aesthetics are essential
- Agency or studio portfolio hero sections for maximum visual impact
- Brand identity pages for luxury or tech-forward companies
- Award or showcase sections where the metallic effect reinforces prestige
- One-off campaign landing pages where performance tradeoffs are acceptable

## When NOT to Use

- Any page that needs fast load times (WebGL is heavy)
- Mobile-first experiences (GPU-intensive rendering)
- Professional service sites where the effect feels too flashy (medical, legal)
- Content-heavy pages where the chrome distracts from reading
- Low-budget client builds where the performance cost is not justified

## Pairs Well With

- `blur-text` - Text revealing over liquid chrome is the ultimate premium hero combo
- `gradient-text` - Silver/metallic gradient text ties into the chrome aesthetic
- `animated-content` - Content appearing over the flowing chrome feels like a luxury reveal
- `split-text` - Text splitting in over the reflective surface has a cinematic quality

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| speed | number | 0.5 | Flow speed of the liquid chrome |
| distortion | number | 1.0 | How much the surface distorts (0-2) |
| reflectivity | number | 0.8 | How reflective/shiny the surface is (0-1) |
| color | string | "#c0c0c0" | Base tint color of the chrome |
| mouseInteraction | boolean | true | Whether the chrome reacts to cursor movement |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LiquidChrome-TS-TW
```

## Usage Example

```jsx
import LiquidChrome from '@/components/ui/LiquidChrome';
import BlurText from '@/components/ui/BlurText';

function PremiumHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <LiquidChrome
          speed={0.3}
          distortion={0.8}
          reflectivity={0.7}
          color="#ff642a"
          mouseInteraction={true}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="Forged in Code."
          delay={200}
          animateBy="words"
          className="text-5xl md:text-8xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-xl text-gray-200 max-w-xl mx-auto font-[Manrope]">
          Precision-engineered digital infrastructure.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework chrome tint: `color="#ff642a"` gives the chrome surface a warm brand tint
- For neutral luxury: use `color="#888888"` or `color="#c0c0c0"` for pure silver chrome
- `speed` of 0.2-0.4 feels like slow-flowing mercury. Above 0.6 feels like rushing water.
- `mouseInteraction` is the killer feature. Keep it enabled on desktop, disable on mobile.
- GHL: not recommended. WebGL rendering requires a proper React environment.
- Only deploy on Lyfework's own brand pages or premium client builds that justify the weight
- Add a dark overlay between chrome and text for readability

## Performance Notes

- WebGL-based rendering, the heaviest background in the arsenal
- Requires a decent GPU. Will cause frame drops on low-end devices.
- Always provide a static gradient fallback for mobile and low-powered devices
- Lazy-load the WebGL context so it only initializes when the section is in view
- Disable `mouseInteraction` on mobile to save resources
- Not SSR-compatible in the WebGL variant. Server renders a fallback gradient.
