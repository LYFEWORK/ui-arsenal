---
name: smooth-scroll
source: ReactBits
source_url: https://reactbits.dev/animations/smooth-scroll
category: animations
tags: scroll, smooth, locomotive, inertia, momentum, wrapper
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# SmoothScroll

> Wraps the page in a smooth, momentum-based scroll container. Replaces native browser scrolling with buttery inertia-based scrolling like Locomotive Scroll.

## When to Use

- Full-page creative builds where native scroll feels too abrupt
- Portfolio or agency sites with scroll-triggered animations throughout
- Single-page designs with multiple animated sections
- Builds pairing with GradualBlur, SplitText, or other scroll-linked animations

## When NOT to Use

- Content-heavy sites where users need to scroll quickly
- E-commerce or utility sites (smooth scroll slows navigation)
- Pages with anchor links (smooth scroll can interfere with jump-to-section)
- Accessibility-focused builds (overriding native scroll has a11y implications)
- GHL builds (conflicts with platform scroll behavior)

## Pairs Well With

- `split-text` - GSAP ScrollTrigger text reveals feel better with smooth scrolling
- `gradual-blur` - Scroll-linked blur transitions are smoother
- `animated-content` - All scroll reveals benefit from momentum scrolling
- `parallax` - Smooth scroll + parallax layers = premium depth

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Page content to wrap |
| damping | number | 0.1 | Scroll damping (0-1, lower = smoother) |
| speed | number | 1 | Scroll speed multiplier |
| touchMultiplier | number | 2 | Touch scroll sensitivity |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/SmoothScroll-TS-TW
```

## Lyfework Customization Notes

- `damping` of 0.08-0.12 feels premium. Above 0.2 feels barely different from native.
- Wrap the ENTIRE page content, not individual sections
- Test all scroll-linked animations after enabling (timing may shift)
- NOT for GHL builds. React-only.
- Add `will-change: transform` to the scroll container

## Performance Notes

- Transforms the scroll container via CSS translate3d
- Can impact performance on very long pages with many DOM elements
- requestAnimationFrame based, GPU accelerated
- Test on mobile (touch scroll with smooth scrolling can feel laggy)
