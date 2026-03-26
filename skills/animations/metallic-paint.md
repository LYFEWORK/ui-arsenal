---
name: metallic-paint
source: ReactBits
source_url: https://reactbits.dev/animations/metallic-paint
category: animations
tags: metallic, chrome, paint, shader, premium, reflective
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# MetallicPaint

> A metallic chrome paint shader effect that coats elements in a reflective liquid metal surface, reacting to cursor movement for a premium, high-end visual treatment.

## When to Use

- Hero section feature images or product shots that need a luxury feel
- Logo treatments where the brand mark gets a chrome or liquid metal finish
- Award or milestone sections where the metallic sheen communicates prestige
- One-time use on a key visual element to make it the page centerpiece
- Premium service tier cards where the metallic effect justifies the price visually

## When NOT to Use

- Body text or readable content (metallic distortion kills readability)
- Multiple elements on the same page (one chrome element is statement, five is gaudy)
- Fast-loading pages where the shader adds significant render time
- Mobile-first designs where the shader effect may not render consistently

## Pairs Well With

- `glare-hover` - Metallic paint on the element, glare sweep on hover for double reflection
- `gradient-text` - Brand gradient text next to a chrome element creates high-low contrast
- `animated-content` - Scroll-reveal the metallic element for dramatic entrance
- `magic-rings` - Pulsing rings behind a chrome-coated logo for a prestige hero

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Element to apply the metallic effect to |
| color | string | "#c0c0c0" | Base metallic color |
| roughness | number | 0.3 | Surface roughness (0 = mirror, 1 = matte) |
| intensity | number | 0.8 | Reflection intensity (0-1) |
| interactive | boolean | true | React to cursor position for light simulation |
| lightAngle | number | 45 | Default light source angle in degrees |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/MetallicPaint-TS-TW
```

## Usage Example

```jsx
import MetallicPaint from '@/components/ui/MetallicPaint';

function LuxuryServiceHero() {
  return (
    <section className="bg-[#0a0a0a] py-32 px-8 font-[Manrope]">
      <div className="max-w-4xl mx-auto text-center">
        <MetallicPaint
          color="#d4a574"
          roughness={0.2}
          intensity={0.9}
          interactive
        >
          <h1 className="text-8xl font-bold tracking-tight">
            PREMIUM
          </h1>
        </MetallicPaint>
        <p className="mt-8 text-xl text-gray-400 max-w-xl mx-auto">
          Bespoke web experiences for brands that demand the extraordinary.
        </p>
        <button className="mt-10 px-10 py-4 rounded-[12px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold text-lg">
          Inquire Now
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- For gold metallic: `color="#d4a574"` with `roughness={0.2}`. For silver chrome: `color="#c0c0c0"` with `roughness={0.15}`.
- Use sparingly -- one metallic element per page is the rule. It should be the hero moment.
- On `#0a0a0a` backgrounds the chrome reflections contrast beautifully; avoid on light backgrounds.
- The brand gradient CTA button (`from-[#ff642a] to-[#ff0301]`) placed below metallic text creates a luxury-to-action flow.
- GHL embeds: the canvas-based shader may need explicit dimensions; test that it scales within GHL containers.
- Pair with Manrope at heavy weights (`font-bold` or `font-extrabold`) for text that carries the metallic treatment well.

## Performance Notes

- Uses a canvas-based shader for the metallic reflection simulation
- CPU-intensive on initial render; consider lazy-loading the component
- `interactive` mode uses `mousemove` for light angle updates at 60fps via `requestAnimationFrame`
- Bundle size: ~5KB (shader math + canvas rendering logic)
- On low-end mobile devices, set `interactive={false}` and use a static metallic gradient fallback
