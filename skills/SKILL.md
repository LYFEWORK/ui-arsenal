---
name: ui-arsenal
description: >
  Lyfework UI Arsenal - Curated library of 70 premium animated React components.
  Use this skill whenever building websites, landing pages, or web applications
  for Lyfework or Lyfework clients. Contains text animations, scroll reveals,
  interactive cards, animated backgrounds, cursor effects, and navigation patterns.
  Each component is documented with usage context, implementation code, and
  Lyfework-specific customization notes. Always reference this skill before
  building UI to check if a pre-built premium component exists for the need.
---

# Lyfework UI Arsenal

A curated collection of 70 premium animated React components for building $30k+ websites.

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
- Adding scroll-triggered content reveals (AnimatedContent, FadeContent)
- Creating card grids (TiltedCard, SpotlightCard, GlowCard, FlipCard)
- Adding stats/metrics sections (CountUp, Counter)
- Building navigation (Dock, BubbleMenu, Stepper)
- Adding cursor effects (BlobCursor, SplashCursor, FollowCursor)
- Any section that needs animated polish

**Build Custom When:**
- The design calls for something truly unique to this specific client
- The component would need so many modifications it's faster to build fresh
- Performance constraints require a lighter implementation
- The element is simple enough that animation adds no value

## Component Index

### Text Animations (16)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| AsciiText | `text-animations/ascii-text.md` | none | Retro/terminal style text art on canvas |
| BlurText | `text-animations/blur-text.md` | framer-motion | Hero headlines, section titles. Blurs in word by word |
| CircularText | `text-animations/circular-text.md` | none | Rotating badge/orbit decorative text elements |
| CountUp | `text-animations/count-up.md` | framer-motion | Stats, metrics, KPIs. Numbers count up on scroll |
| FallingText | `text-animations/falling-text.md` | none | Dramatic gravity/physics text animations |
| GradientText | `text-animations/gradient-text.md` | none | Brand names, accent words. Animated color gradient sweep |
| RotatingText | `text-animations/rotating-text.md` | framer-motion | Cycling/swapping headline words (typewriter variant) |
| ScrollFloat | `text-animations/scroll-float.md` | gsap | Parallax depth text that floats on scroll |
| ScrollVelocity | `text-animations/scroll-velocity.md` | framer-motion | Kinetic scroll-speed text marquee |
| ShinyText | `text-animations/shiny-text.md` | none | Premium shimmer/gloss sweep on badges and labels |
| SplitText | `text-animations/split-text.md` | gsap, @gsap/react | Scroll-triggered headlines. GSAP-powered character splits |
| TextPressure | `text-animations/text-pressure.md` | none | Interactive cursor-responsive text distortion |
| TextScramble | `text-animations/text-scramble.md` | none | Matrix/cipher decode reveal effect |
| TrueFocus | `text-animations/true-focus.md` | framer-motion | Word-by-word focus highlight with border attention |
| TypingAnimation | `text-animations/typing-animation.md` | none | Typewriter cursor effect for terminal/code style |
| VariableProximity | `text-animations/variable-proximity.md` | none | Cursor-responsive variable font weight changes |

### Animations & Effects (17)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| AnimatedBorder | `animations/animated-border.md` | none | Rotating gradient border on cards and wrappers |
| AnimatedContent | `animations/animated-content.md` | framer-motion | Default scroll-reveal wrapper for any section |
| BlobCursor | `animations/blob-cursor.md` | none | Organic morphing blob that follows cursor |
| ClickSpark | `animations/click-spark.md` | none | CTA buttons. Spark burst on click for delight |
| Crosshair | `animations/crosshair.md` | none | Precision crosshair cursor for targeting UIs |
| FadeContent | `animations/fade-content.md` | framer-motion | Simple fade + scroll reveal entrance wrapper |
| FollowCursor | `animations/follow-cursor.md` | none | Eye-tracking / element follows cursor playfully |
| GradualBlur | `animations/gradual-blur.md` | framer-motion | Progressive blur on scroll for depth/focus |
| ImageTrail | `animations/image-trail.md` | none | Cursor leaves trail of images on hover |
| Magnet | `animations/magnet.md` | framer-motion | Hero CTAs. Element pulls toward cursor on hover |
| Marquee | `animations/marquee.md` | none | Infinite scrolling ticker for logos, brands, testimonials |
| MorphingBlob | `animations/morphing-blob.md` | none | Ambient organic SVG shape morphing |
| Noise | `animations/noise.md` | none | Film grain/noise texture overlay |
| PixelTransition | `animations/pixel-transition.md` | none | Dramatic pixel-dissolve page/section transitions |
| SmoothScroll | `animations/smooth-scroll.md` | none | Locomotive-style smooth scroll with inertia |
| SplashCursor | `animations/splash-cursor.md` | none | Premium WebGL fluid splash on cursor movement |
| StarBorder | `animations/star-border.md` | none | Animated glowing rotating border for buttons/cards |

### Interactive Components (16)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| Accordion | `components/accordion.md` | framer-motion | FAQ sections, expandable content panels |
| AnimatedList | `components/animated-list.md` | framer-motion | Feature lists, activity feeds. Staggered item reveal |
| Carousel | `components/carousel.md` | framer-motion | Image galleries, testimonial sliders, swipeable content |
| ComparisonSlider | `components/comparison-slider.md` | none | Before/after image comparison with drag handle |
| Counter | `components/counter.md` | framer-motion | Interactive increment/decrement number input |
| DecayCard | `components/decay-card.md` | none | Edgy hover distortion/glitch effect cards |
| ElasticSlider | `components/elastic-slider.md` | framer-motion | Physics-based elastic range slider input |
| FlipCard | `components/flip-card.md` | none | Two-sided 3D flip reveal cards on hover |
| GlowCard | `components/glow-card.md` | none | Neon glow border cards with ambient hover effect |
| Lanyard | `components/lanyard.md` | three.js, react-three-fiber | 3D physics-based badge/card with spring dynamics |
| PixelCard | `components/pixel-card.md` | none | Retro pixel/glitch hover effect cards on canvas |
| SpotlightCard | `components/spotlight-card.md` | none | Feature grids. Cursor-following spotlight glow |
| StackedCards | `components/stacked-cards.md` | framer-motion | Swipeable card deck with stacked depth effect |
| Tabs | `components/tabs.md` | framer-motion | Animated tab navigation with content switching |
| TiltedCard | `components/tilted-card.md` | framer-motion | Service cards, portfolio items. 3D tilt on hover |
| Tooltip | `components/tooltip.md` | framer-motion | Contextual hover popup with animated entrance |

### Navigation (4)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| BubbleMenu | `navigation/bubble-menu.md` | framer-motion | Floating radial/circular interactive menu |
| Dock | `navigation/dock.md` | framer-motion | Bottom nav bars. macOS-style icon magnification |
| InfiniteMenu | `navigation/infinite-menu.md` | framer-motion | Fullscreen creative nav. Showcase/portfolio sites only |
| Stepper | `navigation/stepper.md` | framer-motion | Multi-step wizard/progress navigation |

### Backgrounds (17)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| Aurora | `backgrounds/aurora.md` | none | Hero backgrounds. Flowing organic gradient animation |
| Ballpit | `backgrounds/ballpit.md` | three.js, cannon-es | Playful 3D physics ball pit interactive background |
| Beams | `backgrounds/beams.md` | none | Dramatic sections. Sweeping light beam animation |
| Galaxy | `backgrounds/galaxy.md` | ogl | Interactive WebGL star field/space background |
| GridDistortion | `backgrounds/grid-distortion.md` | three.js | Mouse-reactive WebGL grid warp distortion |
| GridMotion | `backgrounds/grid-motion.md` | gsap | Animated mosaic grid of images/text tiles |
| Hyperspeed | `backgrounds/hyperspeed.md` | three.js | Star warp/hyperspace WebGL dramatic background |
| Iridescence | `backgrounds/iridescence.md` | none | Holographic rainbow premium WebGL background |
| LetterGlitch | `backgrounds/letter-glitch.md` | none | Matrix/digital rain glitching letter background |
| Lightning | `backgrounds/lightning.md` | none | Electric energy lightning bolt canvas animation |
| Particles | `backgrounds/particles.md` | none | Tech/SaaS heroes. Connected dot particle field |
| Ribbons | `backgrounds/ribbons.md` | none | Flowing 3D ribbon lines for elegant/luxury sections |
| Ripple | `backgrounds/ripple.md` | none | Click-triggered water ripple ring animation |
| ShapeBlur | `backgrounds/shape-blur.md` | none | Soft organic blurred gradient shapes |
| Squares | `backgrounds/squares.md` | none | Subtle geometric grid pattern background |
| Threads | `backgrounds/threads.md` | none | Woven fabric-like thread lines on canvas |
| Waves | `backgrounds/waves.md` | none | Flowing SVG ocean wave organic background |

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

### Recipe: Immersive Hero
```
Galaxy (background) + ScrollFloat (headline) + GradualBlur (content reveal) + SplashCursor (cursor effect)
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

### Recipe: Premium Card Grid
```
FadeContent (reveal) + GlowCard or FlipCard (per card) + ShinyText (labels) + StarBorder (featured card)
```

### Recipe: Interactive Portfolio
```
Hyperspeed (background) + Marquee (client logos) + StackedCards (project showcase) + ImageTrail (hover detail)
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
| framer-motion | BlurText, AnimatedContent, AnimatedList, TiltedCard, Dock, Magnet, CountUp, RotatingText, ScrollVelocity, TrueFocus, FadeContent, GradualBlur, Accordion, Carousel, Counter, ElasticSlider, StackedCards, Tabs, Tooltip, BubbleMenu, InfiniteMenu, Stepper | ~30kb |
| gsap + ScrollTrigger | SplitText, ScrollFloat, GridMotion | ~35kb |
| three.js | Ballpit, GridDistortion, Hyperspeed, Lanyard | ~140kb |
| react-three-fiber | Lanyard | ~40kb |
| cannon-es | Ballpit | ~60kb |
| ogl | Galaxy | ~30kb |
| lucide-react | Dock (icons) | ~5kb per icon |
| (none) | GradientText, SpotlightCard, ClickSpark, Particles, Aurora, Beams, AsciiText, CircularText, FallingText, ShinyText, TextPressure, TextScramble, TypingAnimation, VariableProximity, AnimatedBorder, BlobCursor, Crosshair, FollowCursor, ImageTrail, Marquee, MorphingBlob, Noise, PixelTransition, SmoothScroll, SplashCursor, StarBorder, ComparisonSlider, DecayCard, FlipCard, GlowCard, PixelCard, Iridescence, LetterGlitch, Lightning, Ribbons, Ripple, ShapeBlur, Squares, Threads, Waves | 0kb |

For most builds, framer-motion is the only required dependency. Load GSAP only when SplitText or ScrollFloat is used. Load three.js only for Ballpit, GridDistortion, Hyperspeed, or Lanyard.
