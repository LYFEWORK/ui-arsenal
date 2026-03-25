---
name: ui-arsenal
description: >
  Lyfework UI Arsenal - Curated library of premium animated React components.
  Use this skill whenever building websites, landing pages, or web applications
  for Lyfework or Lyfework clients. Contains text animations, scroll reveals,
  interactive cards, animated backgrounds, and navigation patterns. Each component
  is documented with usage context, implementation code, and Lyfework-specific
  customization notes. Always reference this skill before building UI to check
  if a pre-built premium component exists for the need.
---

# Lyfework UI Arsenal

A curated collection of premium animated React components for building $30k+ websites.

## How to Use This Skill Library

Before building any UI section, check if a component in this arsenal matches the need.
These are production-tested, performance-optimized, and pre-adapted for Lyfework builds.

### Decision Flow

1. **Identify what you're building** (hero section, feature grid, navigation, etc.)
2. **Check this index** for matching components
3. **Read the component's skill file** for props, usage examples, and pairing recommendations
4. **Implement using the documented code** with Lyfework customization notes applied
5. **Combine components** using the "Pairs Well With" recommendations

### When to Use Arsenal Components vs. Custom Code

**Use Arsenal Components When:**
- Building hero sections (BlurText + Aurora or Particles)
- Adding scroll-triggered content reveals (AnimatedContent)
- Creating card grids (TiltedCard, SpotlightCard)
- Adding stats/metrics sections (CountUp)
- Building navigation (Dock, InfiniteMenu)
- Any section that needs animated polish

**Build Custom When:**
- The design calls for something truly unique to this specific client
- The component would need so many modifications it's faster to build fresh
- Performance constraints require a lighter implementation
- The element is simple enough that animation adds no value

## Component Index

### Text Animations

| Component | Tier | File | Best For |
|-----------|------|------|----------|
| BlurText | 1 | `text-animations/blur-text.md` | Hero headlines, section titles. Blurs in word by word. |
| SplitText | 1 | `text-animations/split-text.md` | Scroll-triggered headlines. GSAP-powered character splits. |
| GradientText | 1 | `text-animations/gradient-text.md` | Brand names, accent words. Animated color gradient sweep. |
| CountUp | 2 | `text-animations/count-up.md` | Stats, metrics, KPIs. Numbers count up on scroll. |

### Animations & Effects

| Component | Tier | File | Best For |
|-----------|------|------|----------|
| AnimatedContent | 1 | `animations/animated-content.md` | Everything. Default scroll-reveal wrapper for any section. |
| ClickSpark | 2 | `animations/click-spark.md` | CTA buttons. Spark burst on click for delight. |
| Magnet | 2 | `animations/magnet.md` | Hero CTAs. Element pulls toward cursor on hover. |

### Interactive Components

| Component | Tier | File | Best For |
|-----------|------|------|----------|
| TiltedCard | 1 | `components/tilted-card.md` | Service cards, portfolio items. 3D tilt on hover. |
| SpotlightCard | 1 | `components/spotlight-card.md` | Feature grids. Cursor-following spotlight glow. |
| AnimatedList | 1 | `components/animated-list.md` | Feature lists, activity feeds. Staggered item reveal. |

### Navigation

| Component | Tier | File | Best For |
|-----------|------|------|----------|
| Dock | 1 | `navigation/dock.md` | Bottom nav bars. macOS-style icon magnification. |
| InfiniteMenu | 2 | `navigation/infinite-menu.md` | Fullscreen creative nav. Showcase/portfolio sites only. |

### Backgrounds

| Component | Tier | File | Best For |
|-----------|------|------|----------|
| Aurora | 1 | `backgrounds/aurora.md` | Hero backgrounds. Flowing organic gradient animation. |
| Particles | 1 | `backgrounds/particles.md` | Tech/SaaS heroes. Connected dot particle field. |
| Beams | 2 | `backgrounds/beams.md` | Dramatic sections. Sweeping light beam animation. |

## Tier System

- **Tier 1 (Core):** Use on most builds. These are the bread-and-butter components.
- **Tier 2 (Situational):** Use when the design specifically calls for it.
- **Tier 3 (Showcase):** Reserved for hero builds where maximum visual impact is the goal.

## Standard Build Recipes

### Recipe: Premium Hero Section
```
Aurora (background) + BlurText (headline) + AnimatedContent (subtext + CTA) + Magnet (CTA button)
```

### Recipe: Tech-Forward Hero
```
Particles (background) + SplitText (headline) + CountUp (inline stat) + ClickSpark (CTA)
```

### Recipe: Feature Grid Section
```
AnimatedContent (section wrapper) + SpotlightCard (per card) + GradientText (card titles)
```

### Recipe: Stats / Social Proof
```
Beams (background) + AnimatedContent (wrapper) + CountUp (per stat) + SpotlightCard (stat container)
```

### Recipe: Service Showcase
```
AnimatedContent (scroll reveal) + TiltedCard (per service) + BlurText (section headline)
```

### Recipe: Full-Page Single-Scroll Site
```
Aurora (hero bg) + BlurText (hero text) + Dock (navigation) + AnimatedContent (all sections) + SpotlightCard (features) + TiltedCard (portfolio) + CountUp (stats) + ClickSpark (CTAs)
```

## Lyfework Build Standards (Apply to All Components)

1. **Typography:** Manrope 800 for headlines, 700 for subheads, 400 for body
2. **Colors:** Brand gradient `#ff642a` to `#ff0301` for accents. Dark bg `#0a0a0a`.
3. **Glass effect:** `lyf-glass` class on cards and panels
4. **Border radius:** 12px cards, 8px buttons, 16px glass panels
5. **Animation timing:** 0.5-0.7s duration, ease-out. Never bouncy. Never slow.
6. **Mobile:** All components must degrade gracefully. Test hover states on touch.
7. **GHL compatibility:** Test canvas elements and IntersectionObserver inside GHL iframe.

## Dependencies Summary

| Package | Used By | Size (gzipped) |
|---------|---------|-----------------|
| framer-motion | BlurText, AnimatedContent, AnimatedList, TiltedCard, Dock, Magnet | ~30kb |
| gsap + ScrollTrigger | SplitText | ~35kb |
| lucide-react | Dock (icons) | ~5kb per icon |
| (none) | GradientText, SpotlightCard, ClickSpark, Particles, Aurora, Beams | 0kb |

For most builds, framer-motion is the only required dependency. Load GSAP only when SplitText is used.
