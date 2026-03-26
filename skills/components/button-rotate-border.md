---
name: button-rotate-border
source: Luxe
source_url: https://www.luxeui.com/ui/button-rotate-border
category: components
tags: button, rotating border, animated border, cta, gradient border
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ButtonRotateBorder

> Button with a continuously rotating animated gradient border, creating a mesmerizing energy ring effect.

## When to Use
- Standout CTAs that need to command attention on feature-rich pages
- SaaS dashboard upgrade prompts or trial expiration warnings
- Portfolio hero sections for primary "Hire Me" or "Contact" buttons
- Event or launch countdown pages where urgency is key
- Dark-mode landing pages where the rotating border glows dramatically

## When NOT to Use
- Pages with multiple competing animated elements — causes visual overload
- Form submission buttons where animation implies processing state
- Professional/corporate contexts preferring understated design
- Mobile-heavy audiences where the rotation is less impactful at small sizes

## Pairs Well With
- `aurora` - rotating border button over aurora background creates an energy-field aesthetic
- `particles` - button with rotating border amid floating particles for cosmic hero sections
- `gradient-text` - gradient text heading + rotating border CTA shares the color language
- `spotlight-card` - rotating border button as the focal action inside a spotlight card

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | — | Button content |
| className | string | — | Additional CSS classes |
| borderColor | string | "gradient" | Border color or gradient value |
| borderWidth | number | 2 | Border width in pixels |
| duration | number | 3 | Full rotation duration in seconds |
| radius | string | "8px" | Border radius |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/button-rotate-border"
```

## Usage Example
```jsx
import { ButtonRotateBorder } from "@/components/ui/button-rotate-border";

export function LaunchHero() {
  return (
    <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a]">
      <div className="text-center space-y-8">
        <h1 className="font-manrope font-800 text-6xl text-white">
          Something Big is Coming
        </h1>
        <ButtonRotateBorder
          className="px-10 py-4 font-manrope font-700 text-white text-lg"
          borderColor="linear-gradient(90deg, #ff642a, #ff0301, #ff642a)"
          duration={2.5}
          radius="8px"
        >
          Join the Waitlist
        </ButtonRotateBorder>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Set `borderColor` to `"linear-gradient(90deg, #ff642a, #ff0301, #ff642a)"` for brand gradient
- Use `radius="8px"` to match Lyfework button radius standard
- Apply `font-manrope font-700` for brand typography on button text
- On `#0a0a0a` backgrounds the rotating gradient border creates a neon glow effect
- GHL compatible — uses CSS conic-gradient animation, no external runtime
- Consider slowing `duration` to 4s for a more subtle, premium rotation feel

## Performance Notes
- Pure CSS animation using conic-gradient and rotation — no JS animation loop
- Uses `@property` for gradient angle animation (modern browsers)
- Continuous animation uses GPU compositing — minimal CPU impact
- No layout shift — border is rendered via pseudo-element overlay
- Gracefully degrades to static gradient border in older browsers
