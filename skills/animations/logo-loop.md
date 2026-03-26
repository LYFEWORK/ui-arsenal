---
name: logo-loop
source: ReactBits
source_url: https://reactbits.dev/animations/logo-loop
category: animations
tags: logo, loop, animation, brand, continuous, identity
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# LogoLoop

> A continuous logo animation that cycles through client or partner logos in a smooth infinite scroll or morphing loop, perfect for social proof sections.

## When to Use

- "Trusted by" or "Our clients" social proof strips on landing pages
- Partner logo showcases below the hero section
- Tech stack or integration logo displays
- Award or certification badge scrolling strips
- Footer trust signals showing payment providers, security badges, etc.

## When NOT to Use

- When you have fewer than 4 logos (looks empty and repetitive)
- Case study pages where each logo needs its own dedicated section
- Situations where logos need to be clickable links to individual pages
- Print-style layouts where continuous motion is inappropriate

## Pairs Well With

- `animated-content` - Scroll-reveal the entire logo strip, then it starts looping
- `blur-text` - "Trusted by leading brands" headline with BlurText above the LogoLoop
- `split-text` - Same pattern as above with a different text entrance
- `glare-hover` - Wrap individual logos in glare for a premium hover interaction

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| logos | { src: string; alt: string }[] | required | Array of logo images |
| speed | number | 30 | Scroll speed in pixels per second |
| direction | "left" \| "right" | "left" | Scroll direction |
| pauseOnHover | boolean | true | Pause the scroll on hover |
| gap | number | 48 | Gap between logos in pixels |
| logoHeight | number | 40 | Height of each logo in pixels |
| grayscale | boolean | true | Display logos in grayscale until hovered |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LogoLoop-TS-TW
```

## Usage Example

```jsx
import LogoLoop from '@/components/ui/LogoLoop';

function TrustedBy() {
  const clientLogos = [
    { src: '/logos/clinic-a.svg', alt: 'Smile Dental' },
    { src: '/logos/saas-b.svg', alt: 'GrowthStack' },
    { src: '/logos/fitness-c.svg', alt: 'FitLyf Studios' },
    { src: '/logos/agency-d.svg', alt: 'Pixel Partners' },
    { src: '/logos/realty-e.svg', alt: 'HomeKey Realty' },
    { src: '/logos/med-f.svg', alt: 'VitalCare Health' },
  ];

  return (
    <section className="bg-[#0a0a0a] py-16 font-[Manrope]">
      <p className="text-center text-sm uppercase tracking-widest text-gray-500 mb-8">
        Trusted by forward-thinking brands
      </p>
      <LogoLoop
        logos={clientLogos}
        speed={35}
        direction="left"
        pauseOnHover
        grayscale
        logoHeight={36}
        gap={56}
      />
    </section>
  );
}
```

## Lyfework Customization Notes

- Always use `grayscale={true}` so logos don't clash with the Lyfework brand palette on `#0a0a0a`.
- On hover, logos transition from grayscale to full color -- this is the standard premium pattern.
- Set `logoHeight={36}` for a subtle strip, `logoHeight={48}` for a more prominent display.
- The label above should use Manrope uppercase with `tracking-widest` and `text-gray-500` for the standard style.
- For GHL landing pages, ensure the logo images are hosted on a CDN (not relative paths) since GHL may not resolve them.
- Add `opacity-60 hover:opacity-100` via className on the wrapper for an extra layer of grayscale-to-active transition.

## Performance Notes

- Uses CSS `translateX` animation for the infinite scroll -- GPU accelerated
- Logos are duplicated in the DOM to create the seamless loop illusion
- framer-motion handles the `pauseOnHover` with `useAnimation` controls
- Lazy-load logo images with `loading="lazy"` to avoid blocking LCP
- SSR safe: renders the first set of logos statically, animation starts on hydration
