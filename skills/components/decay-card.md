---
name: decay-card
source: ReactBits
source_url: https://reactbits.dev/components/decay-card
category: components
tags: card, decay, distort, hover, glitch, distortion, edgy
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# DecayCard

> A card that distorts, warps, or "decays" on hover. The card image or content gets a digital distortion effect when the user hovers. Edgy, experimental aesthetic.

## When to Use

- Portfolio or case study cards for creative/design agencies
- Music, gaming, or streetwear brand product cards
- Artist or photographer showcase pages
- Any build where "perfectly polished" isn't the vibe and "raw digital" is
- Lyfework showcase builds that need to demonstrate range

## When NOT to Use

- Professional service businesses (medical, legal, financial)
- Clean/minimal design systems
- E-commerce product cards (distortion makes products look broken)
- More than 4-6 decay cards per page

## Pairs Well With

- `letter-glitch` - Glitch background with decaying cards on top
- `text-scramble` - Scramble text labels inside decay cards
- `pixel-transition` - Full glitch aesthetic suite
- `splash-cursor` - Cursor effects matching the decay feel

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Card content |
| decayIntensity | number | 0.5 | Distortion intensity on hover (0-1) |
| decayType | "glitch" \| "warp" \| "noise" | "glitch" | Style of decay effect |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/DecayCard-TS-TW
```

## Usage Example

```jsx
import DecayCard from '@/components/ui/DecayCard';

function CreativePortfolio() {
  return (
    <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
      <DecayCard decayIntensity={0.4} decayType="glitch">
        <div className="h-80 bg-cover bg-center rounded-2xl" style={{ backgroundImage: 'url(/work/project1.jpg)' }}>
          <div className="absolute bottom-0 p-6 bg-gradient-to-t from-black/80 w-full">
            <h3 className="text-xl font-bold text-white">Project Vortex</h3>
          </div>
        </div>
      </DecayCard>
    </div>
  );
}
```

## Lyfework Customization Notes

- Tier 3 showcase only. This is for proving Lyfework can build anything.
- `decayIntensity` of 0.3-0.5 for subtle. 0.7+ for aggressive.
- `decayType="glitch"` for digital. `"warp"` for organic distortion. `"noise"` for static.
- Not for standard client builds. Save for creative verticals or the Lyfework portfolio.
- Not for GHL (requires SVG filters or Canvas)

## Performance Notes

- SVG filter-based distortion (GPU accelerated)
- Only activates on hover (no idle cost)
- Can cause minor frame drops at high intensity on older GPUs
- Desktop only (hover-dependent)
