---
name: ui-arsenal
description: >
  Lyfework UI Arsenal - Curated library of 142 premium animated React components.
  Use this skill whenever building websites, landing pages, or web applications
  for Lyfework or Lyfework clients. Contains text animations, scroll reveals,
  interactive cards, animated backgrounds, cursor effects, and navigation patterns.
  Each component is documented with usage context, implementation code, and
  Lyfework-specific customization notes. Always reference this skill before
  building UI to check if a pre-built premium component exists for the need.
---

# Lyfework UI Arsenal

A curated collection of 142 premium animated React components for building $30k+ websites.

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
- Adding scroll-triggered content reveals (AnimatedContent, FadeContent, ScrollReveal)
- Creating card grids (TiltedCard, SpotlightCard, GlowCard, FlipCard, MagicBento)
- Adding stats/metrics sections (CountUp, Counter)
- Building navigation (Dock, BubbleMenu, Stepper, PillNav, FlowingMenu, GooeyNav)
- Adding cursor effects (BlobCursor, SplashCursor, FollowCursor, GhostCursor, TargetCursor)
- Glass/premium surfaces (FluidGlass, GlassSurface, GlassIcons)
- Image galleries (CircularGallery, DomeGallery, Masonry, Carousel)
- Any section that needs animated polish

**Build Custom When:**
- The design calls for something truly unique to this specific client
- The component would need so many modifications it's faster to build fresh
- Performance constraints require a lighter implementation
- The element is simple enough that animation adds no value

## Component Index

### Text Animations (23)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| AsciiText | `text-animations/ascii-text.md` | none | Renders text as ASCII art characters. Large block-letter text built from smaller c... |
| BlurText | `text-animations/blur-text.md` | framer-motion | Text that reveals itself by animating from blurred to sharp, word by word or chara... |
| CircularText | `text-animations/circular-text.md` | none | Text arranged in a circle that rotates continuously. Characters are placed along a... |
| CountUp | `text-animations/count-up.md` | framer-motion | Animates a number from 0 to a target value with easing. Triggers on scroll into vi... |
| CurvedLoop | `text-animations/curved-loop.md` | none | Text that curves along a circular or custom SVG path and loops continuously, creat... |
| DecryptedText | `text-animations/decrypted-text.md` | none | Text decryption reveal effect where characters scramble through random glyphs befo... |
| FallingText | `text-animations/falling-text.md` | none | Text characters that fall from their positions with gravity physics, then reassemb... |
| FuzzyText | `text-animations/fuzzy-text.md` | none | Text rendered with fuzzy, blurred edges that sharpens into focus on hover or scrol... |
| GlitchText | `text-animations/glitch-text.md` | none | Digital glitch and distortion effect on text using layered pseudo-elements with co... |
| GradientText | `text-animations/gradient-text.md` | none | Applies an animated gradient color sweep across text. The gradient shifts continuo... |
| RotatingText | `text-animations/rotating-text.md` | framer-motion | A text element that cycles through multiple strings with animated transitions. Wor... |
| ScrollFloat | `text-animations/scroll-float.md` | gsap | Text characters that float up from below with individual parallax timing as you sc... |
| ScrollReveal | `text-animations/scroll-reveal.md` | framer-motion | Text revealed progressively as the user scrolls, with each word or line lighting u... |
| ScrollVelocity | `text-animations/scroll-velocity.md` | framer-motion | Text that scrolls horizontally at a speed proportional to the user's scroll veloci... |
| ShinyText | `text-animations/shiny-text.md` | none | A glossy shimmer sweep that passes across text on a loop. Like a light reflection ... |
| Shuffle | `text-animations/shuffle.md` | none | Text characters or words shuffle through random positions before settling into the... |
| SplitText | `text-animations/split-text.md` | gsap, @gsap/react | Splits text into individual characters or words and animates each one with stagger... |
| TextCursor | `text-animations/text-cursor.md` | none | Custom animated text cursor/caret that blinks alongside typed or static text, evok... |
| TextPressure | `text-animations/text-pressure.md` | none | Text that deforms and squeezes under cursor pressure. Characters compress, stretch... |
| TextScramble | `text-animations/text-scramble.md` | none | Text that decodes from random characters into the final message. Characters shuffl... |
| TrueFocus | `text-animations/true-focus.md` | framer-motion | A text component where a focus border moves from word to word, highlighting each o... |
| TypingAnimation | `text-animations/typing-animation.md` | none | Classic typewriter effect. Text appears character by character with a blinking cur... |
| VariableProximity | `text-animations/variable-proximity.md` | none | Text that changes font weight, size, or style based on cursor proximity. Character... |

### Animations & Effects (32)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| AnimatedBorder | `animations/animated-border.md` | none | A gradient border that rotates around an element continuously. Different from Star... |
| AnimatedContent | `animations/animated-content.md` | framer-motion | A wrapper component that animates its children into view on scroll. The bread-and-... |
| Antigravity | `animations/antigravity.md` | framer-motion | Elements float upward defying gravity on hover or scroll trigger, creating a weigh... |
| BlobCursor | `animations/blob-cursor.md` | none | Replaces the cursor with a morphing organic blob that follows mouse movement. The ... |
| ClickSpark | `animations/click-spark.md` | none | Emits a burst of sparks from the click point on any element. A subtle micro-intera... |
| Crosshair | `animations/crosshair.md` | none | Adds a crosshair overlay that follows the cursor. Horizontal and vertical lines ex... |
| Cubes | `animations/cubes.md` | none | A 3D rotating cube animation built with pure CSS transforms, ideal for loading sta... |
| ElectricBorder | `animations/electric-border.md` | none | An animated crackling electric border effect that wraps any element, perfect for h... |
| FadeContent | `animations/fade-content.md` | framer-motion | Simple opacity fade-in on scroll. No slide, no transform, just clean opacity trans... |
| FollowCursor | `animations/follow-cursor.md` | none | An element (typically eyes, an icon, or a pointer) that tracks and follows the cur... |
| GhostCursor | `animations/ghost-cursor.md` | none | A ghostly cursor trail that follows the user's mouse with fading opacity echoes, a... |
| GlareHover | `animations/glare-hover.md` | none | A cursor-tracking glare/shine effect that sweeps across an element on hover, simul... |
| GradualBlur | `animations/gradual-blur.md` | framer-motion | Content progressively blurs or unblurs as the user scrolls. Creates a depth-of-fie... |
| ImageTrail | `animations/image-trail.md` | none | Images spawn and trail behind the cursor as it moves across a container. Creates a... |
| LaserFlow | `animations/laser-flow.md` | none | An animated laser beam that flows along paths or borders of elements, creating a h... |
| LogoLoop | `animations/logo-loop.md` | framer-motion | A continuous logo animation that cycles through client or partner logos in a smoot... |
| MagicRings | `animations/magic-rings.md` | none | Concentric animated rings that expand and pulse outward from a center point, creat... |
| MagnetLines | `animations/magnet-lines.md` | none | Lines that dynamically attract toward or repel from the cursor like a magnetic fie... |
| Magnet | `animations/magnet.md` | framer-motion | Makes an element magnetically attracted to the cursor on hover. The element subtly... |
| Marquee | `animations/marquee.md` | none | Infinite horizontal scrolling content strip. Logos, testimonials, badges, or any c... |
| MetaBalls | `animations/meta-balls.md` | none | Organic metaball blobs that merge and separate with smooth gooey transitions, crea... |
| MetallicPaint | `animations/metallic-paint.md` | none | A metallic chrome paint shader effect that coats elements in a reflective liquid m... |
| MorphingBlob | `animations/morphing-blob.md` | none | An SVG blob shape that continuously morphs between organic forms. Smooth, ambient ... |
| Noise | `animations/noise.md` | none | A film grain / noise texture overlay that adds analog warmth and depth to any sect... |
| OrbitImages | `animations/orbit-images.md` | framer-motion | Images orbiting around a central point in a 3D circular path, creating a dynamic r... |
| PixelTrail | `animations/pixel-trail.md` | none | A pixelated trail effect that follows cursor movement, rendering blocky pixel squa... |
| PixelTransition | `animations/pixel-transition.md` | none | A full-screen pixel dissolve transition between two states. Content breaks apart i... |
| SmoothScroll | `animations/smooth-scroll.md` | none | Wraps the page in a smooth, momentum-based scroll container. Replaces native brows... |
| SplashCursor | `animations/splash-cursor.md` | none | Replaces the default cursor with a fluid splash effect that trails behind mouse mo... |
| StarBorder | `animations/star-border.md` | none | An animated border with a glowing dot that travels around the element's perimeter.... |
| StickerPeel | `animations/sticker-peel.md` | framer-motion | A sticker peel-off reveal animation that lifts a cover element like peeling a stic... |
| TargetCursor | `animations/target-cursor.md` | none | A target/crosshair scope overlay that follows the mouse cursor, replacing or augme... |

### Interactive Components (39)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| Accordion | `components/accordion.md` | framer-motion | Animated expandable/collapsible content sections. Smooth spring-based height anima... |
| AnimatedList | `components/animated-list.md` | framer-motion | A list component where items animate in sequentially with staggered entrance. New ... |
| BorderGlow | `components/border-glow.md` | none | An animated glowing border effect for cards and containers. A luminous gradient tr... |
| BounceCards | `components/bounce-cards.md` | framer-motion | Cards that bounce into view with spring physics animation. Each card enters with a... |
| CardNav | `components/card-nav.md` | framer-motion | Card-based navigation with animated transitions between items. Each nav item is a ... |
| CardSwap | `components/card-swap.md` | framer-motion | Cards that swap and shuffle positions with smooth animation. Users can click or dr... |
| Carousel | `components/carousel.md` | framer-motion | A smooth, gesture-enabled carousel with momentum scrolling. Supports swipe on mobi... |
| ChromaGrid | `components/chroma-grid.md` | none | A chromatic, colorful animated grid layout where cells shift colors, reveal conten... |
| CircularGallery | `components/circular-gallery.md` | framer-motion | A 3D circular carousel gallery where images are arranged in a ring and rotate arou... |
| ComparisonSlider | `components/comparison-slider.md` | none | A drag-to-reveal before/after image comparison. Two images overlaid with a draggab... |
| Counter | `components/counter.md` | framer-motion | An animated increment/decrement counter with spring physics. Number changes animat... |
| DecayCard | `components/decay-card.md` | none | A card that distorts, warps, or "decays" on hover. The card image or content gets ... |
| DomeGallery | `components/dome-gallery.md` | three.js, @react-three/fiber, @react-three/drei | A dome-shaped 3D gallery layout rendered with WebGL. Images or cards are arranged ... |
| ElasticSlider | `components/elastic-slider.md` | framer-motion | A slider/range input with elastic spring physics. The thumb stretches and snaps ba... |
| FlipCard | `components/flip-card.md` | none | A card that flips to reveal back content on hover or click. Full 3D CSS transform ... |
| FlowingMenu | `components/flowing-menu.md` | framer-motion | A navigation menu with flowing, liquid-style hover transitions. When the user hove... |
| FluidGlass | `components/fluid-glass.md` | none | A fluid glassmorphism card/panel effect with dynamic blur that responds to mouse m... |
| FlyingPosters | `components/flying-posters.md` | framer-motion | Posters and cards that fly in from different directions with 3D rotation, convergi... |
| Folder | `components/folder.md` | framer-motion | An animated folder UI component that opens and closes with a realistic paper-foldi... |
| GlassIcons | `components/glass-icons.md` | none | Glassmorphism-styled icon containers with frosted backgrounds, subtle borders, and... |
| GlassSurface | `components/glass-surface.md` | none | A frosted glass surface panel/card with configurable blur, opacity, and border sty... |
| GlowCard | `components/glow-card.md` | none | A card with a glowing animated border that pulses or shifts color. The glow follow... |
| GooeyNav | `components/gooey-nav.md` | none | A gooey, sticky liquid navigation where menu items blend and merge with an SVG fil... |
| Lanyard | `components/lanyard.md` | three.js, react-three-fiber | A 3D badge/card hanging from a lanyard string with physics-based swinging. Respond... |
| MagicBento | `components/magic-bento.md` | framer-motion | An animated bento grid layout with interactive hover effects. Each cell in the gri... |
| Masonry | `components/masonry.md` | framer-motion | An animated masonry/Pinterest-style grid layout that arranges items in columns wit... |
| ModelViewer | `components/model-viewer.md` | three.js, @react-three/fiber, @react-three/drei | A 3D model viewer component for displaying and interacting with GLTF/GLB models. S... |
| PillNav | `components/pill-nav.md` | framer-motion | A pill-shaped sliding indicator navigation where a rounded highlight slides betwee... |
| PixelCard | `components/pixel-card.md` | none | A card that pixelates or dissolves into pixel fragments on hover. Creates a digita... |
| ProfileCard | `components/profile-card.md` | framer-motion | An animated profile/team member card with hover effects that reveal additional inf... |
| ReflectiveCard | `components/reflective-card.md` | none | A card with a reflective, mirror-like surface effect that responds to mouse moveme... |
| ScrollStack | `components/scroll-stack.md` | framer-motion | Cards or sections that stack on top of each other as the user scrolls. Each card s... |
| SpotlightCard | `components/spotlight-card.md` | none | A card with a radial light effect that follows the mouse cursor. Creates a spotlig... |
| Stack | `components/stack.md` | framer-motion | A stacked element container with visual depth effect. Multiple cards or elements a... |
| StackedCards | `components/stacked-cards.md` | framer-motion | Cards stacked on top of each other that can be swiped or clicked through like a de... |
| StaggeredMenu | `components/staggered-menu.md` | framer-motion | A menu where items enter with staggered animation, each appearing slightly after t... |
| Tabs | `components/tabs.md` | framer-motion | Animated tab navigation with a sliding active indicator and smooth content transit... |
| TiltedCard | `components/tilted-card.md` | framer-motion | A card that responds to mouse movement with a 3D tilt effect. Creates depth and in... |
| Tooltip | `components/tooltip.md` | framer-motion | Animated tooltip that appears on hover with spring physics. Supports multiple posi... |

### Navigation (4)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| BubbleMenu | `navigation/bubble-menu.md` | framer-motion | A floating circular menu that expands from a single button into radial options. It... |
| Dock | `navigation/dock.md` | framer-motion | A macOS-style dock navigation bar with icon magnification on hover. Items scale up... |
| InfiniteMenu | `navigation/infinite-menu.md` | framer-motion | A fullscreen menu with items arranged in a continuous scrolling loop. Items rotate... |
| Stepper | `navigation/stepper.md` | framer-motion | An animated step indicator showing progress through a multi-step process. Steps li... |

### Backgrounds (44)

| Component | File | Dependencies | Best For |
|-----------|------|-------------|----------|
| Aurora | `backgrounds/aurora.md` | none | An animated aurora borealis background effect with flowing, organic gradient color... |
| Balatro | `backgrounds/balatro.md` | none | A psychedelic warped stripe background inspired by the card game Balatro, creating... |
| Ballpit | `backgrounds/ballpit.md` | three.js, cannon-es | 3D physics-based ball pit with realistic collision. Balls bounce, stack, and respo... |
| Beams | `backgrounds/beams.md` | none | Animated light beams that sweep across a dark background. Creates a dramatic, cine... |
| ColorBends | `backgrounds/color-bends.md` | none | Bent and curved color gradient bands that create smooth, flowing color transitions... |
| DarkVeil | `backgrounds/dark-veil.md` | none | A dark translucent overlay/veil effect that dims and adds depth to any section. Th... |
| Dither | `backgrounds/dither.md` | none | A dithered gradient/pattern background that creates a retro pixel-art texture effe... |
| DotGrid | `backgrounds/dot-grid.md` | none | An animated dot grid pattern background that creates a clean, minimal geometric te... |
| EvilEye | `backgrounds/evil-eye.md` | none | An animated eye/iris that follows the user's cursor, creating an unsettling "being... |
| FaultyTerminal | `backgrounds/faulty-terminal.md` | none | A glitchy CRT terminal screen effect with scan lines, flicker, and text corruption... |
| FloatingLines | `backgrounds/floating-lines.md` | none | Thin animated lines that drift lazily across the background, creating an elegant, ... |
| Galaxy | `backgrounds/galaxy.md` | ogl | An interactive star field with twinkling stars, glow effects, and mouse-responsive... |
| GradientBlinds | `backgrounds/gradient-blinds.md` | none | Venetian blind strips with gradient animation that open and close to reveal conten... |
| Grainient | `backgrounds/grainient.md` | none | A gradient background with a film grain/noise texture overlay, combining smooth co... |
| GridDistortion | `backgrounds/grid-distortion.md` | three.js | A flat grid that warps and distorts where the mouse hovers. Creates a fabric-stret... |
| GridMotion | `backgrounds/grid-motion.md` | gsap | An animated grid of tiles that shift, scale, and rearrange with smooth motion. Til... |
| GridScan | `backgrounds/grid-scan.md` | none | A grid pattern background with a scanning line that sweeps across it, creating a f... |
| Hyperspeed | `backgrounds/hyperspeed.md` | three.js | A star-field warp speed effect. Particles streak toward the camera creating a hype... |
| Iridescence | `backgrounds/iridescence.md` | none | A holographic, iridescent surface effect that shifts colors based on mouse positio... |
| LetterGlitch | `backgrounds/letter-glitch.md` | none | A background filled with randomly glitching characters that shift and change. Crea... |
| LightPillar | `backgrounds/light-pillar.md` | none | A vertical light pillar/beam that rises from the bottom of the section, creating a... |
| LightRays | `backgrounds/light-rays.md` | none | Radiating light rays emanating from a focal point, creating a sunburst or divine l... |
| Lightning | `backgrounds/lightning.md` | none | Animated lightning bolts that arc across a dark background. Electric, high-energy ... |
| LineWaves | `backgrounds/line-waves.md` | none | Animated wavy lines flowing across the background in organic, undulating patterns.... |
| LiquidChrome | `backgrounds/liquid-chrome.md` | none | A liquid metallic chrome flowing effect that creates a premium, hyper-realistic me... |
| LiquidEther | `backgrounds/liquid-ether.md` | none | An ethereal liquid flowing ambient background with soft, dreamy color transitions.... |
| Orb | `backgrounds/orb.md` | none | A glowing, blurred orb/sphere that serves as an ambient background element. The si... |
| Particles | `backgrounds/particles.md` | none | An animated particle field with floating dots that connect with lines when near ea... |
| PixelBlast | `backgrounds/pixel-blast.md` | none | An exploding pixel burst background effect where pixels scatter outward from a foc... |
| PixelSnow | `backgrounds/pixel-snow.md` | none | Falling pixel-art snow particles that drift down the screen, creating a calm, ambi... |
| Plasma | `backgrounds/plasma.md` | none | An animated plasma/lava-lamp fluid effect with vibrant, shifting color blobs. Crea... |
| Prism | `backgrounds/prism.md` | none | A prismatic light refraction effect that splits light into a subtle rainbow spectr... |
| PrismaticBurst | `backgrounds/prismatic-burst.md` | none | An intense burst of prismatic light rays radiating outward with spectral color sep... |
| Radar | `backgrounds/radar.md` | none | A rotating radar sweep scan animation with concentric rings and a sweeping beam. C... |
| Ribbons | `backgrounds/ribbons.md` | none | Flowing 3D ribbon strands that weave across the screen with smooth, organic motion... |
| RippleGrid | `backgrounds/ripple-grid.md` | none | A grid pattern with ripple distortion waves that spread from cursor position or cl... |
| Ripple | `backgrounds/ripple.md` | none | Concentric ripple rings that emanate from click or cursor position. Creates a wate... |
| ShapeBlur | `backgrounds/shape-blur.md` | none | Large blurred gradient shapes (circles, blobs) floating and slowly drifting in the... |
| ShapeGrid | `backgrounds/shape-grid.md` | none | A grid of animated geometric shapes (circles, squares, triangles) that rotate, sca... |
| Silk | `backgrounds/silk.md` | none | A smooth, silky fabric flowing background that creates an elegant, luxurious sense... |
| SoftAurora | `backgrounds/soft-aurora.md` | none | A softer, subtler version of the aurora background with gentler color transitions ... |
| Squares | `backgrounds/squares.md` | none | A subtle animated grid of squares that pulse, fade, or shift in opacity. The light... |
| Threads | `backgrounds/threads.md` | none | Thin animated lines that weave and flow across the background like fabric threads ... |
| Waves | `backgrounds/waves.md` | none | Animated SVG wave layers that flow across the bottom or top of a section. Multiple... |

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

### Recipe: Luxury/Premium Hero
```
Silk (background) + BlurText (headline) + FluidGlass (content panel) + Magnet (CTA)
```

### Recipe: Feature Grid Section
```
AnimatedContent (section wrapper) + SpotlightCard (per card) + GradientText (card titles)
```

### Recipe: Premium Bento Layout
```
MagicBento (grid) + GlassSurface (panels) + CountUp (stats) + GradientText (labels)
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
Hyperspeed (background) + Marquee (client logos) + CircularGallery (project showcase) + ImageTrail (hover detail)
```

### Recipe: Glass Dashboard
```
SoftAurora (background) + FluidGlass (panels) + GlassIcons (nav) + PillNav (tabs) + CountUp (metrics)
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
| @gsap/react | SplitText | (included with gsap) |
| @react-three/drei | DomeGallery, ModelViewer | ~10kb |
| @react-three/fiber | DomeGallery, ModelViewer | ~10kb |
| cannon-es | Ballpit | ~60kb |
| framer-motion | Accordion, AnimatedContent, AnimatedList, Antigravity, BlurText, BounceCards, BubbleMenu, CardNav, CardSwap, Carousel, CircularGallery, CountUp, Counter, Dock, ElasticSlider, FadeContent, FlowingMenu, FlyingPosters, Folder, GradualBlur, InfiniteMenu, LogoLoop, MagicBento, Magnet, Masonry, OrbitImages, PillNav, ProfileCard, RotatingText, ScrollReveal, ScrollStack, ScrollVelocity, Stack, StackedCards, StaggeredMenu, Stepper, StickerPeel, Tabs, TiltedCard, Tooltip, TrueFocus | ~30kb |
| gsap | GridMotion, ScrollFloat, SplitText | ~35kb |
| ogl | Galaxy | ~30kb |
| react-three-fiber | Lanyard | ~40kb |
| three.js | Ballpit, DomeGallery, GridDistortion, Hyperspeed, Lanyard, ModelViewer | ~140kb |
| (none) | AnimatedBorder, AsciiText, Aurora, Balatro, Beams, BlobCursor, BorderGlow, ChromaGrid, CircularText, ClickSpark, ColorBends, ComparisonSlider, Crosshair, Cubes, CurvedLoop, DarkVeil, DecayCard, DecryptedText, Dither, DotGrid, ElectricBorder, EvilEye, FallingText, FaultyTerminal, FlipCard, FloatingLines, FluidGlass, FollowCursor, FuzzyText, GhostCursor, GlareHover, GlassIcons, GlassSurface, GlitchText, GlowCard, GooeyNav, GradientBlinds, GradientText, Grainient, GridScan, ImageTrail, Iridescence, LaserFlow, LetterGlitch, LightPillar, LightRays, Lightning, LineWaves, LiquidChrome, LiquidEther, MagicRings, MagnetLines, Marquee, MetaBalls, MetallicPaint, MorphingBlob, Noise, Orb, Particles, PixelBlast, PixelCard, PixelSnow, PixelTrail, PixelTransition, Plasma, Prism, PrismaticBurst, Radar, ReflectiveCard, Ribbons, Ripple, RippleGrid, ShapeBlur, ShapeGrid, ShinyText, Shuffle, Silk, SmoothScroll, SoftAurora, SplashCursor, SpotlightCard, Squares, StarBorder, TargetCursor, TextCursor, TextPressure, TextScramble, Threads, TypingAnimation, VariableProximity, Waves | 0kb |

For most builds, framer-motion is the only required dependency. Load GSAP only when SplitText or ScrollFloat is used. Load three.js only for DomeGallery, ModelViewer, Ballpit, GridDistortion, Hyperspeed, or Lanyard.

## Skipped Components (Known Broken)

The following ReactBits categories are excluded due to incomplete/placeholder implementations:
- **Buttons** (8 components) - All return placeholder code
- **Forms** (3 components) - Incomplete implementations
- **Loaders** (9 components) - Incomplete implementations
