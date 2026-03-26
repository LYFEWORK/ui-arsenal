---
name: logo-carousel
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/logo-carousel
category: components
tags: logo, carousel, clients, partners, social-proof, brands
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# LogoCarousel

> Animated logo carousel for client, partner, or integration showcase sections.

## When to Use
- Client logo strips on agency or SaaS landing pages
- Partner integration showcases for platform products
- Trust-building social proof sections below the fold
- Technology stack displays on developer portfolios
- Certification or compliance badge carousels

## When NOT to Use
- When fewer than 4 logos exist (use a static grid instead)
- Pages where motion conflicts with accessibility preferences
- Print-oriented layouts where animation is irrelevant

## Pairs Well With
- `marquee` - Continuous scroll for larger logo sets
- `animated-content` - Fade-in entrance before carousel starts
- `spotlight-card` - Individual logo cards with hover spotlight
- `number-ticker` - "Trusted by 500+ brands" stat above logo carousel

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| logos | { src: string; alt: string; href?: string }[] | [] | Array of logo objects |
| speed | number | 30 | Scroll speed in pixels per second |
| pauseOnHover | boolean | true | Pause carousel on hover |
| direction | 'left' \| 'right' | 'left' | Scroll direction |
| columns | number | 5 | Visible logos at once |
| grayscale | boolean | true | Display logos in grayscale |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/logo-carousel"
```

## Usage Example
```jsx
import { LogoCarousel } from "@/components/ui/logo-carousel";

const clientLogos = [
  { src: "/logos/client-a.svg", alt: "Client A" },
  { src: "/logos/client-b.svg", alt: "Client B" },
  { src: "/logos/client-c.svg", alt: "Client C" },
  { src: "/logos/client-d.svg", alt: "Client D" },
  { src: "/logos/client-e.svg", alt: "Client E" },
  { src: "/logos/client-f.svg", alt: "Client F" },
];

export function TrustSection() {
  return (
    <section className="bg-[#0a0a0a] py-16 border-y border-white/10">
      <p className="font-manrope font-400 text-white/40 text-center text-sm uppercase tracking-widest mb-8">
        Trusted by leading practices
      </p>
      <LogoCarousel
        logos={clientLogos}
        speed={25}
        grayscale={true}
        pauseOnHover={true}
        columns={5}
      />
    </section>
  );
}
```

## Lyfework Customization Notes
- Use grayscale={true} on #0a0a0a background; logos colorize on hover
- Manrope 400 uppercase tracking label above carousel for context
- Set border-white/10 top/bottom for subtle section separation
- GHL compatible -- works in iframe embeds without issue
- Use SVG logos for crisp rendering at any scale

## Performance Notes
- CSS transform-based animation is GPU-accelerated
- Logos are duplicated in DOM for seamless loop -- keep set under 20
- SVG logos have near-zero rendering cost vs raster images
- pauseOnHover uses CSS animation-play-state (no JS per frame)
- Framer Motion only used for entrance animation; scroll is pure CSS
