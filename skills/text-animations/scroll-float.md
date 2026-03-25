---
name: scroll-float
source: ReactBits
source_url: https://reactbits.dev/text-animations/scroll-float
category: text-animations
tags: text, scroll, float, parallax, depth, 3d, entrance
dependencies: gsap
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# ScrollFloat

> Text characters that float up from below with individual parallax timing as you scroll. Each character has slightly different speed, creating a wave-like entrance with depth.

## When to Use

- Section headlines that need more depth than SplitText
- Quote or manifesto-style text blocks
- Single powerful statement sections
- Scroll-driven storytelling moments
- Builds where GSAP is already loaded for other animations

## When NOT to Use

- Short text (effect needs 4+ words to look good)
- Multiple instances per page (diminishing impact)
- Fast-scroll pages where the animation gets missed
- Body text or secondary content

## Pairs Well With

- `smooth-scroll` - ScrollFloat + smooth scrolling = premium combo
- `gradual-blur` - Background un-blurs as text floats into position
- `noise` - Noise texture behind floating text
- `aurora` - Atmospheric background for the floating text moment

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to animate |
| depth | number | 100 | Float distance in px |
| stagger | number | 0.03 | Stagger between characters |
| scrollStart | string | "top 80%" | ScrollTrigger start position |
| scrollEnd | string | "top 20%" | ScrollTrigger end position |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/ScrollFloat-TS-TW
```

## Lyfework Customization Notes

- `depth` of 80-120px for noticeable float. Below 50 looks like regular fade-in.
- `stagger` of 0.02-0.04 between characters. Creates the wave effect.
- Use Manrope 800 at large sizes (text-5xl+) for maximum impact
- Requires GSAP ScrollTrigger (bundle with SplitText if both are used)
- Not for GHL (GSAP + React required)

## Performance Notes

- GSAP ScrollTrigger powered
- Each character is a positioned span element
- Long text blocks = many DOM elements (keep under 50 characters)
- GPU accelerated transforms
