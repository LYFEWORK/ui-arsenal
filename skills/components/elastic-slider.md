---
name: elastic-slider
source: ReactBits
source_url: https://reactbits.dev/components/elastic-slider
category: components
tags: slider, elastic, range, input, interactive, physics
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ElasticSlider

> A slider/range input with elastic spring physics. The thumb stretches and snaps back when dragged, creating a playful, tactile interaction.

## When to Use

- Pricing calculators or cost estimators
- Configuration panels where users adjust values (speed, intensity, quantity)
- Interactive demos or product showcases
- Settings pages in web applications
- Any slider where standard HTML range inputs feel too sterile

## When NOT to Use

- Forms that need precise numeric input (use a number field)
- Accessibility-critical contexts (test screen reader support first)
- Sliders with many discrete steps (elastic feels wrong for 20+ stops)

## Pairs Well With

- `spotlight-card` - Slider inside a spotlight card for a config panel
- `count-up` - Display the slider value with count-up animation
- `animated-content` - Reveal the slider section on scroll

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| min | number | 0 | Minimum value |
| max | number | 100 | Maximum value |
| value | number | 50 | Current value |
| onChange | function | required | Value change handler |
| elasticity | number | 0.5 | Spring elasticity (0-1) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ElasticSlider-TS-TW
```

## Usage Example

```jsx
import { useState } from 'react';
import ElasticSlider from '@/components/ui/ElasticSlider';

function PricingCalculator() {
  const [patients, setPatients] = useState(100);
  return (
    <div className="lyf-glass p-10 rounded-2xl max-w-md">
      <h3 className="text-xl font-bold text-white">Monthly Patients</h3>
      <ElasticSlider min={50} max={500} value={patients} onChange={setPatients} />
      <p className="mt-4 text-3xl font-extrabold text-white">{patients}</p>
    </div>
  );
}
```

## Lyfework Customization Notes

- Track color: `rgba(255,100,42,0.3)`. Thumb: Lyfework gradient.
- `elasticity` of 0.4-0.6 feels premium. Above 0.8 feels like a toy.
- Great for ClinicOS pricing pages with patient volume calculators
- Works in GHL with React embed blocks

## Performance Notes

- framer-motion spring physics, lightweight
- Touch-friendly, works on mobile
