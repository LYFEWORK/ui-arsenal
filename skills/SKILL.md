---
name: ui-arsenal
description: >
  Lyfework UI Arsenal - Curated library of 225 premium animated React components
  from ReactBits, Magic UI, and Aceternity UI. Use this skill whenever building
  websites, landing pages, or web applications for Lyfework or Lyfework clients.
  Contains text animations, scroll reveals, interactive cards, animated backgrounds,
  cursor effects, navigation patterns, device mockups, and buttons. Each component
  is documented with usage context, implementation code, and Lyfework-specific
  customization notes. Always reference this skill before building UI to check
  if a pre-built premium component exists for the need.
---

# Lyfework UI Arsenal

A curated collection of 225 premium animated React components for building $30k+ websites.

## Sources

- **Aceternity UI**: 47 components
- **Magic UI**: 36 components
- **ReactBits**: 142 components

Source badges in tables: **RB** = ReactBits, **MU** = Magic UI, **AU** = Aceternity UI

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
- Building hero sections (BlurText + Aurora or Particles or LampEffect)
- Adding scroll-triggered reveals (AnimatedContent, FadeContent, ScrollReveal, TracingBeam)
- Creating card grids (TiltedCard, SpotlightCard, MagicCard, 3DCardEffect, WobbleCard)
- Adding stats/metrics (CountUp, Counter, NumberTicker)
- Building navigation (Dock, FloatingNavbar, Sidebar, BubbleMenu, PillNav)
- Adding cursor effects (BlobCursor, SplashCursor, FollowCursor, Pointer)
- Glass/premium surfaces (FluidGlass, GlassSurface, GlassIcons)
- Image galleries (CircularGallery, DomeGallery, Masonry, HeroParallax, FocusCards)
- Device mockups (Safari, iPhone, MacbookScroll, ContainerScrollAnimation)
- Buttons (ShimmerButton, PulsatingButton, RainbowButton, RippleButton, ShinyButton)
- Video showcases (HeroVideoDialog, VideoText)
- Maps and globes (Globe, DottedMap, WorldMap)
- Testimonials (AnimatedTestimonials, MarqueeTestimonials)
- Any section that needs animated polish

**Build Custom When:**
- The design calls for something truly unique to this specific client
- The component needs so many modifications it's faster to build fresh
- Performance constraints require a lighter implementation
- The element is simple enough that animation adds no value

## Component Index

### Text Animations (37)

| Component | Source | File | Dependencies | Best For |
|-----------|--------|------|-------------|----------|
| AsciiText | RB | `text-animations/ascii-text.md` | none | Renders text as ASCII art characters. Large block-letter text built from smal... |
| AuroraText | MU | `text-animations/aurora-text.md` | framer-motion | Text with an animated aurora/gradient color effect that smoothly shifts throu... |
| BlurText | RB | `text-animations/blur-text.md` | framer-motion | Text that reveals itself by animating from blurred to sharp, word by word or ... |
| CircularText | RB | `text-animations/circular-text.md` | none | Text arranged in a circle that rotates continuously. Characters are placed al... |
| ColourfulText | AU | `text-animations/colourful-text.md` | framer-motion | Text with per-character rainbow color animation that cycles through vibrant h... |
| ComicText | MU | `text-animations/comic-text.md` | none | Bold comic/pop-art style text with exaggerated shadows and vibrant treatment. |
| ContainerTextFlip | AU | `text-animations/container-text-flip.md` | framer-motion | Text that flips or rotates within a fixed container, cycling through multiple... |
| CountUp | RB | `text-animations/count-up.md` | framer-motion | Animates a number from 0 to a target value with easing. Triggers on scroll in... |
| CurvedLoop | RB | `text-animations/curved-loop.md` | none | Text that curves along a circular or custom SVG path and loops continuously, ... |
| DecryptedText | RB | `text-animations/decrypted-text.md` | none | Text decryption reveal effect where characters scramble through random glyphs... |
| FallingText | RB | `text-animations/falling-text.md` | none | Text characters that fall from their positions with gravity physics, then rea... |
| FuzzyText | RB | `text-animations/fuzzy-text.md` | none | Text rendered with fuzzy, blurred edges that sharpens into focus on hover or ... |
| GlitchText | RB | `text-animations/glitch-text.md` | none | Digital glitch and distortion effect on text using layered pseudo-elements wi... |
| GradientText | RB | `text-animations/gradient-text.md` | none | Applies an animated gradient color sweep across text. The gradient shifts con... |
| LayoutTextFlip | AU | `text-animations/layout-text-flip.md` | framer-motion | Full layout text flip transition that animates the entire text block with a p... |
| LineShadowText | MU | `text-animations/line-shadow-text.md` | none | Text with a cascading line shadow depth effect creating an elegant layered ap... |
| MorphingText | MU | `text-animations/morphing-text.md` | framer-motion | Text that smoothly morphs between different words or phrases with fluid lette... |
| NumberTicker | MU | `text-animations/number-ticker.md` | framer-motion | Rolling digit counter animation that ticks up to a target number, perfect for... |
| RotatingText | RB | `text-animations/rotating-text.md` | framer-motion | A text element that cycles through multiple strings with animated transitions... |
| ScrollFloat | RB | `text-animations/scroll-float.md` | gsap | Text characters that float up from below with individual parallax timing as y... |
| ScrollReveal | RB | `text-animations/scroll-reveal.md` | framer-motion | Text revealed progressively as the user scrolls, with each word or line light... |
| ScrollVelocity | RB | `text-animations/scroll-velocity.md` | framer-motion | Text that scrolls horizontally at a speed proportional to the user's scroll v... |
| ShinyText | RB | `text-animations/shiny-text.md` | none | A glossy shimmer sweep that passes across text on a loop. Like a light reflec... |
| Shuffle | RB | `text-animations/shuffle.md` | none | Text characters or words shuffle through random positions before settling int... |
| SparklesText | MU | `text-animations/sparkles-text.md` | none | Text with floating sparkle/glitter particles that twinkle around the characters. |
| SplitText | RB | `text-animations/split-text.md` | gsap, @gsap/react | Splits text into individual characters or words and animates each one with st... |
| TextAnimate | MU | `text-animations/text-animate.md` | framer-motion | Character-by-character or word-by-word entrance animation wrapper for text co... |
| TextCursor | RB | `text-animations/text-cursor.md` | none | Custom animated text cursor/caret that blinks alongside typed or static text,... |
| TextHighlighter | MU | `text-animations/text-highlighter.md` | none | Text with an animated highlight/marker underline effect that draws across the... |
| TextHoverEffect | AU | `text-animations/text-hover-effect.md` | none | SVG-based text with a mask/reveal effect on hover, creating a gradient or ima... |
| TextPressure | RB | `text-animations/text-pressure.md` | none | Text that deforms and squeezes under cursor pressure. Characters compress, st... |
| TextReveal | MU | `text-animations/text-reveal.md` | framer-motion | Text revealed progressively by scroll position, where each word highlights as... |
| TextScramble | RB | `text-animations/text-scramble.md` | none | Text that decodes from random characters into the final message. Characters s... |
| TrueFocus | RB | `text-animations/true-focus.md` | framer-motion | A text component where a focus border moves from word to word, highlighting e... |
| TypingAnimation | RB | `text-animations/typing-animation.md` | none | Classic typewriter effect. Text appears character by character with a blinkin... |
| VariableProximity | RB | `text-animations/variable-proximity.md` | none | Text that changes font weight, size, or style based on cursor proximity. Char... |
| VideoText | MU | `text-animations/video-text.md` | none | Text filled with video content using the text as a clipping mask, creating a ... |

### Animations & Effects (41)

| Component | Source | File | Dependencies | Best For |
|-----------|--------|------|-------------|----------|
| 3dMarquee | AU | `animations/3d-marquee.md` | framer-motion | 3D perspective scrolling marquee with depth effect, creating an infinite scro... |
| AnimatedBorder | RB | `animations/animated-border.md` | none | A gradient border that rotates around an element continuously. Different from... |
| AnimatedContent | RB | `animations/animated-content.md` | framer-motion | A wrapper component that animates its children into view on scroll. The bread... |
| Antigravity | RB | `animations/antigravity.md` | framer-motion | Elements float upward defying gravity on hover or scroll trigger, creating a ... |
| BlobCursor | RB | `animations/blob-cursor.md` | none | Replaces the cursor with a morphing organic blob that follows mouse movement.... |
| CanvasRevealEffect | AU | `animations/canvas-reveal-effect.md` | framer-motion | Canvas-based paint/brush reveal effect on hover, where dots or particles expa... |
| ClickSpark | RB | `animations/click-spark.md` | none | Emits a burst of sparks from the click point on any element. A subtle micro-i... |
| Confetti | MU | `animations/confetti.md` | canvas-confetti | Celebration confetti burst effect triggered by user actions like form submiss... |
| Crosshair | RB | `animations/crosshair.md` | none | Adds a crosshair overlay that follows the cursor. Horizontal and vertical lin... |
| Cubes | RB | `animations/cubes.md` | none | A 3D rotating cube animation built with pure CSS transforms, ideal for loadin... |
| ElectricBorder | RB | `animations/electric-border.md` | none | An animated crackling electric border effect that wraps any element, perfect ... |
| FadeContent | RB | `animations/fade-content.md` | framer-motion | Simple opacity fade-in on scroll. No slide, no transform, just clean opacity ... |
| FollowCursor | RB | `animations/follow-cursor.md` | none | An element (typically eyes, an icon, or a pointer) that tracks and follows th... |
| GhostCursor | RB | `animations/ghost-cursor.md` | none | A ghostly cursor trail that follows the user's mouse with fading opacity echo... |
| GlareHover | RB | `animations/glare-hover.md` | none | A cursor-tracking glare/shine effect that sweeps across an element on hover, ... |
| GoogleGeminiEffect | AU | `animations/google-gemini-effect.md` | framer-motion | Google Gemini-style animated SVG beam hero with flowing, undulating lines tha... |
| GradualBlur | RB | `animations/gradual-blur.md` | framer-motion | Content progressively blurs or unblurs as the user scrolls. Creates a depth-o... |
| ImageTrail | RB | `animations/image-trail.md` | none | Images spawn and trail behind the cursor as it moves across a container. Crea... |
| LaserFlow | RB | `animations/laser-flow.md` | none | An animated laser beam that flows along paths or borders of elements, creatin... |
| LogoLoop | RB | `animations/logo-loop.md` | framer-motion | A continuous logo animation that cycles through client or partner logos in a ... |
| MagicRings | RB | `animations/magic-rings.md` | none | Concentric animated rings that expand and pulse outward from a center point, ... |
| MagnetLines | RB | `animations/magnet-lines.md` | none | Lines that dynamically attract toward or repel from the cursor like a magneti... |
| Magnet | RB | `animations/magnet.md` | framer-motion | Makes an element magnetically attracted to the cursor on hover. The element s... |
| Marquee | RB | `animations/marquee.md` | none | Infinite horizontal scrolling content strip. Logos, testimonials, badges, or ... |
| MetaBalls | RB | `animations/meta-balls.md` | none | Organic metaball blobs that merge and separate with smooth gooey transitions,... |
| MetallicPaint | RB | `animations/metallic-paint.md` | none | A metallic chrome paint shader effect that coats elements in a reflective liq... |
| MorphingBlob | RB | `animations/morphing-blob.md` | none | An SVG blob shape that continuously morphs between organic forms. Smooth, amb... |
| Noise | RB | `animations/noise.md` | none | A film grain / noise texture overlay that adds analog warmth and depth to any... |
| OrbitImages | RB | `animations/orbit-images.md` | framer-motion | Images orbiting around a central point in a 3D circular path, creating a dyna... |
| OrbitingCircles | MU | `animations/orbiting-circles.md` | none | Icons or elements that orbit around a central point in smooth circular motion. |
| PixelTrail | RB | `animations/pixel-trail.md` | none | A pixelated trail effect that follows cursor movement, rendering blocky pixel... |
| PixelTransition | RB | `animations/pixel-transition.md` | none | A full-screen pixel dissolve transition between two states. Content breaks ap... |
| PointerHighlight | AU | `animations/pointer-highlight.md` | framer-motion | Cursor-following highlight or glow effect that tracks the mouse pointer acros... |
| ScrollProgress | MU | `animations/scroll-progress.md` | framer-motion | Reading progress bar that fills based on scroll position, typically fixed at ... |
| SmoothScroll | RB | `animations/smooth-scroll.md` | none | Wraps the page in a smooth, momentum-based scroll container. Replaces native ... |
| SplashCursor | RB | `animations/splash-cursor.md` | none | Replaces the default cursor with a fluid splash effect that trails behind mou... |
| StarBorder | RB | `animations/star-border.md` | none | An animated border with a glowing dot that travels around the element's perim... |
| StickerPeel | RB | `animations/sticker-peel.md` | framer-motion | A sticker peel-off reveal animation that lifts a cover element like peeling a... |
| SvgMaskEffect | AU | `animations/svg-mask-effect.md` | framer-motion | SVG mask that reveals content underneath as the cursor moves, creating a spot... |
| TargetCursor | RB | `animations/target-cursor.md` | none | A target/crosshair scope overlay that follows the mouse cursor, replacing or ... |
| TracingBeam | AU | `animations/tracing-beam.md` | framer-motion | SVG beam that traces scroll progress along the side of content, creating a vi... |

### Interactive Components (86)

| Component | Source | File | Dependencies | Best For |
|-----------|--------|------|-------------|----------|
| 3dAnimatedPin | AU | `components/3d-animated-pin.md` | framer-motion | 3D elevated pin popup that rises on hover, ideal for maps, location markers, ... |
| 3dCardEffect | AU | `components/3d-card-effect.md` | framer-motion | Perspective tilt card with elevated floating children that respond to mouse p... |
| Accordion | RB | `components/accordion.md` | framer-motion | Animated expandable/collapsible content sections. Smooth spring-based height ... |
| AnimatedBeam | MU | `components/animated-beam.md` | framer-motion | Animated SVG light beam that visually connects two elements, ideal for illust... |
| AnimatedList | RB | `components/animated-list.md` | framer-motion | A list component where items animate in sequentially with staggered entrance.... |
| AnimatedModal | AU | `components/animated-modal.md` | framer-motion | Spring-animated modal/dialog with smooth open/close transitions, backdrop blu... |
| AnimatedTestimonials | AU | `components/animated-testimonials.md` | framer-motion | Auto-rotating testimonial carousel with smooth cross-fade animations, avatar ... |
| AvatarCircles | MU | `components/avatar-circles.md` | none | Overlapping stacked avatar circles for displaying users, team members, or soc... |
| BorderGlow | RB | `components/border-glow.md` | none | An animated glowing border effect for cards and containers. A luminous gradie... |
| BounceCards | RB | `components/bounce-cards.md` | framer-motion | Cards that bounce into view with spring physics animation. Each card enters w... |
| CardHoverEffect | AU | `components/card-hover-effect.md` | framer-motion | Card grid with gradient glow hover animation that highlights the active card ... |
| CardNav | RB | `components/card-nav.md` | framer-motion | Card-based navigation with animated transitions between items. Each nav item ... |
| CardSwap | RB | `components/card-swap.md` | framer-motion | Cards that swap and shuffle positions with smooth animation. Users can click ... |
| Carousel | RB | `components/carousel.md` | framer-motion | A smooth, gesture-enabled carousel with momentum scrolling. Supports swipe on... |
| ChromaGrid | RB | `components/chroma-grid.md` | none | A chromatic, colorful animated grid layout where cells shift colors, reveal c... |
| CircularGallery | RB | `components/circular-gallery.md` | framer-motion | A 3D circular carousel gallery where images are arranged in a ring and rotate... |
| CodeComparison | MU | `components/code-comparison.md` | none | Side-by-side code diff comparison component for showcasing before/after code ... |
| CometCard | AU | `components/comet-card.md` | none | Card with animated comet streak/trail effect along the border, creating a dyn... |
| ComparisonSlider | RB | `components/comparison-slider.md` | none | A drag-to-reveal before/after image comparison. Two images overlaid with a dr... |
| ContainerScrollAnimation | AU | `components/container-scroll-animation.md` | framer-motion | MacBook-style scroll reveal animation for product showcases, with a device fr... |
| Counter | RB | `components/counter.md` | framer-motion | An animated increment/decrement counter with spring physics. Number changes a... |
| Cover | AU | `components/cover.md` | framer-motion | Text or element wrapper with an animated beam reveal effect on hover, creatin... |
| DecayCard | RB | `components/decay-card.md` | none | A card that distorts, warps, or "decays" on hover. The card image or content ... |
| DirectionAwareHover | AU | `components/direction-aware-hover.md` | framer-motion | Card with an overlay that enters from the direction the cursor approaches, cr... |
| DomeGallery | RB | `components/dome-gallery.md` | three.js, @react-three/fiber, @react-three/drei | A dome-shaped 3D gallery layout rendered with WebGL. Images or cards are arra... |
| DottedMap | MU | `components/dotted-map.md` | none | Animated world map composed of dots with highlighted location pins for showca... |
| DraggableCard | AU | `components/draggable-card.md` | framer-motion | Drag-to-move interactive card with spring physics, inertia, and boundary cons... |
| ElasticSlider | RB | `components/elastic-slider.md` | framer-motion | A slider/range input with elastic spring physics. The thumb stretches and sna... |
| EvervaultCard | AU | `components/evervault-card.md` | framer-motion | Card with encrypted matrix text effect that reveals readable content on hover... |
| FileTree | MU | `components/file-tree.md` | none | Animated file explorer directory tree component for displaying project struct... |
| FlipCard | RB | `components/flip-card.md` | none | A card that flips to reveal back content on hover or click. Full 3D CSS trans... |
| FlowingMenu | RB | `components/flowing-menu.md` | framer-motion | A navigation menu with flowing, liquid-style hover transitions. When the user... |
| FluidGlass | RB | `components/fluid-glass.md` | none | A fluid glassmorphism card/panel effect with dynamic blur that responds to mo... |
| FlyingPosters | RB | `components/flying-posters.md` | framer-motion | Posters and cards that fly in from different directions with 3D rotation, con... |
| FocusCards | AU | `components/focus-cards.md` | framer-motion | Cards that expand and come into focus when hovered, while dimming the rest of... |
| Folder | RB | `components/folder.md` | framer-motion | An animated folder UI component that opens and closes with a realistic paper-... |
| GlassIcons | RB | `components/glass-icons.md` | none | Glassmorphism-styled icon containers with frosted backgrounds, subtle borders... |
| GlassSurface | RB | `components/glass-surface.md` | none | A frosted glass surface panel/card with configurable blur, opacity, and borde... |
| Globe | MU | `components/globe.md` | cobe | Interactive 3D rotating globe rendered on canvas, perfect for showcasing glob... |
| GlowCard | RB | `components/glow-card.md` | none | A card with a glowing animated border that pulses or shifts color. The glow f... |
| GooeyNav | RB | `components/gooey-nav.md` | none | A gooey, sticky liquid navigation where menu items blend and merge with an SV... |
| HeroHighlight | AU | `components/hero-highlight.md` | framer-motion | Hero section with animated gradient highlight that follows the cursor, plus a... |
| HeroParallax | AU | `components/hero-parallax.md` | framer-motion | Full-page parallax image gallery hero with multi-row scrolling images that cr... |
| HeroVideoDialog | MU | `components/hero-video-dialog.md` | framer-motion | Video modal with an animated thumbnail trigger — click to expand into a full-... |
| IconCloud | MU | `components/icon-cloud.md` | none | Floating cloud of tech/brand icons with interactive 3D rotation and hover eff... |
| ImagesBadge | AU | `components/images-badge.md` | none | Floating avatar or image badges scattered as decorative elements around conte... |
| InteractiveHoverButton | MU | `components/interactive-hover-button.md` | none | Button with an animated fill effect on hover that slides in from the edge wit... |
| Iphone | MU | `components/iphone.md` | none | iPhone device mockup frame for displaying app screenshots, mobile previews, o... |
| LampEffect | AU | `components/lamp-effect.md` | framer-motion | Linear-style glowing lamp accent for section headers, creating a dramatic top... |
| Lanyard | RB | `components/lanyard.md` | three.js, react-three-fiber | A 3D badge/card hanging from a lanyard string with physics-based swinging. Re... |
| LayoutGrid | AU | `components/layout-grid.md` | framer-motion | Animated expanding grid layout where cards grow to reveal detailed content on... |
| Lens | MU | `components/lens.md` | framer-motion | Magnifying lens effect that follows the cursor on hover over images, revealin... |
| LinkPreview | AU | `components/link-preview.md` | framer-motion | Hover preview tooltip that shows a thumbnail or preview card of the linked pa... |
| MacbookScroll | AU | `components/macbook-scroll.md` | framer-motion | MacBook lid-opening scroll animation that reveals a product screenshot or vid... |
| MagicBento | RB | `components/magic-bento.md` | framer-motion | An animated bento grid layout with interactive hover effects. Each cell in th... |
| MagicCard | MU | `components/magic-card.md` | framer-motion | Card with a radial gradient that follows the cursor on hover, creating a spot... |
| Masonry | RB | `components/masonry.md` | framer-motion | An animated masonry/Pinterest-style grid layout that arranges items in column... |
| ModelViewer | RB | `components/model-viewer.md` | three.js, @react-three/fiber, @react-three/drei | A 3D model viewer component for displaying and interacting with GLTF/GLB mode... |
| NeonGradientCard | MU | `components/neon-gradient-card.md` | none | Card with an animated neon gradient border glow that shifts colors continuously. |
| PillNav | RB | `components/pill-nav.md` | framer-motion | A pill-shaped sliding indicator navigation where a rounded highlight slides b... |
| PixelCard | RB | `components/pixel-card.md` | none | A card that pixelates or dissolves into pixel fragments on hover. Creates a d... |
| ProfileCard | RB | `components/profile-card.md` | framer-motion | An animated profile/team member card with hover effects that reveal additiona... |
| PulsatingButton | MU | `components/pulsating-button.md` | none | Button with a continuous pulsing glow ring animation that draws attention to ... |
| RainbowButton | MU | `components/rainbow-button.md` | none | Button with an animated rainbow gradient border that continuously shifts thro... |
| ReflectiveCard | RB | `components/reflective-card.md` | none | A card with a reflective, mirror-like surface effect that responds to mouse m... |
| RippleButton | MU | `components/ripple-button.md` | none | Button with a material-design-style ripple effect that emanates from the clic... |
| Safari | MU | `components/safari.md` | none | Safari browser device mockup frame for displaying web app screenshots in a re... |
| ScrollStack | RB | `components/scroll-stack.md` | framer-motion | Cards or sections that stack on top of each other as the user scrolls. Each c... |
| ShimmerButton | MU | `components/shimmer-button.md` | none | Button with a sweeping shimmer/shine animation that glides across the surface... |
| ShinyButton | MU | `components/shiny-button.md` | none | Button with a glossy animated shine effect that sweeps across on hover, creat... |
| SpotlightCard | RB | `components/spotlight-card.md` | none | A card with a radial light effect that follows the mouse cursor. Creates a sp... |
| Stack | RB | `components/stack.md` | framer-motion | A stacked element container with visual depth effect. Multiple cards or eleme... |
| StackedCards | RB | `components/stacked-cards.md` | framer-motion | Cards stacked on top of each other that can be swiped or clicked through like... |
| StaggeredMenu | RB | `components/staggered-menu.md` | framer-motion | A menu where items enter with staggered animation, each appearing slightly af... |
| StatefulButton | AU | `components/stateful-button.md` | framer-motion | Button with animated loading, success, and error state transitions, providing... |
| StickyBanner | AU | `components/sticky-banner.md` | none | Sticky top announcement or notification banner that stays visible as the user... |
| StickyScrollReveal | AU | `components/sticky-scroll-reveal.md` | framer-motion | Pinned content panel with a scrolling side panel that reveals different secti... |
| Tabs | RB | `components/tabs.md` | framer-motion | Animated tab navigation with a sliding active indicator and smooth content tr... |
| Terminal | MU | `components/terminal.md` | none | Animated terminal/CLI display with typing animation, perfect for showcasing c... |
| TextRevealCard | AU | `components/text-reveal-card.md` | framer-motion | Card where cursor movement reveals hidden text underneath, like wiping away a... |
| TiltedCard | RB | `components/tilted-card.md` | framer-motion | A card that responds to mouse movement with a 3D tilt effect. Creates depth a... |
| Timeline | AU | `components/timeline.md` | framer-motion | Vertical timeline with sticky headers and an animated connecting beam that tr... |
| Tooltip | RB | `components/tooltip.md` | framer-motion | Animated tooltip that appears on hover with spring physics. Supports multiple... |
| TweetCard | MU | `components/tweet-card.md` | none | Embedded tweet/X post card component for displaying social proof or testimoni... |
| WobbleCard | AU | `components/wobble-card.md` | framer-motion | Card with a playful wobble/tilt effect on hover, adding personality and engag... |
| WorldMap | AU | `components/world-map.md` | none | World map visualization with animated dot connections between locations, show... |

### Navigation (6)

| Component | Source | File | Dependencies | Best For |
|-----------|--------|------|-------------|----------|
| BubbleMenu | RB | `navigation/bubble-menu.md` | framer-motion | A floating circular menu that expands from a single button into radial option... |
| Dock | RB | `navigation/dock.md` | framer-motion | A macOS-style dock navigation bar with icon magnification on hover. Items sca... |
| FloatingNavbar | AU | `navigation/floating-navbar.md` | framer-motion | Navbar that shrinks and floats as the user scrolls down, transitioning from f... |
| InfiniteMenu | RB | `navigation/infinite-menu.md` | framer-motion | A fullscreen menu with items arranged in a continuous scrolling loop. Items r... |
| Sidebar | AU | `navigation/sidebar.md` | framer-motion | Animated slide-out sidebar navigation panel with smooth open/close transition... |
| Stepper | RB | `navigation/stepper.md` | framer-motion | An animated step indicator showing progress through a multi-step process. Ste... |

### Backgrounds (55)

| Component | Source | File | Dependencies | Best For |
|-----------|--------|------|-------------|----------|
| Aurora | RB | `backgrounds/aurora.md` | none | An animated aurora borealis background effect with flowing, organic gradient ... |
| BackgroundBeamsWithCollision | AU | `backgrounds/background-beams-with-collision.md` | framer-motion | Animated light beams that travel across the screen and scatter on collision w... |
| BackgroundGradientAnimation | AU | `backgrounds/background-gradient-animation.md` | none | Moving and morphing gradient background animation with multiple color blobs t... |
| BackgroundGradient | AU | `backgrounds/background-gradient.md` | none | Animated mesh gradient background with smooth color transitions, providing am... |
| BackgroundLines | AU | `backgrounds/background-lines.md` | none | Minimal vertical lines background pattern that adds subtle texture and depth ... |
| Balatro | RB | `backgrounds/balatro.md` | none | A psychedelic warped stripe background inspired by the card game Balatro, cre... |
| Ballpit | RB | `backgrounds/ballpit.md` | three.js, cannon-es | 3D physics-based ball pit with realistic collision. Balls bounce, stack, and ... |
| Beams | RB | `backgrounds/beams.md` | none | Animated light beams that sweep across a dark background. Creates a dramatic,... |
| ColorBends | RB | `backgrounds/color-bends.md` | none | Bent and curved color gradient bands that create smooth, flowing color transi... |
| DarkVeil | RB | `backgrounds/dark-veil.md` | none | A dark translucent overlay/veil effect that dims and adds depth to any sectio... |
| Dither | RB | `backgrounds/dither.md` | none | A dithered gradient/pattern background that creates a retro pixel-art texture... |
| DotGrid | RB | `backgrounds/dot-grid.md` | none | An animated dot grid pattern background that creates a clean, minimal geometr... |
| DottedGlowBackground | AU | `backgrounds/dotted-glow-background.md` | none | Dotted pattern background with a radial glow accent, creating depth with a gr... |
| EvilEye | RB | `backgrounds/evil-eye.md` | none | An animated eye/iris that follows the user's cursor, creating an unsettling "... |
| FaultyTerminal | RB | `backgrounds/faulty-terminal.md` | none | A glitchy CRT terminal screen effect with scan lines, flicker, and text corru... |
| FloatingLines | RB | `backgrounds/floating-lines.md` | none | Thin animated lines that drift lazily across the background, creating an eleg... |
| Galaxy | RB | `backgrounds/galaxy.md` | ogl | An interactive star field with twinkling stars, glow effects, and mouse-respo... |
| GlowingStarsBackground | AU | `backgrounds/glowing-stars-background.md` | none | Night sky background with animated glowing stars that pulse and shimmer, crea... |
| GradientBlinds | RB | `backgrounds/gradient-blinds.md` | none | Venetian blind strips with gradient animation that open and close to reveal c... |
| Grainient | RB | `backgrounds/grainient.md` | none | A gradient background with a film grain/noise texture overlay, combining smoo... |
| GridDistortion | RB | `backgrounds/grid-distortion.md` | three.js | A flat grid that warps and distorts where the mouse hovers. Creates a fabric-... |
| GridMotion | RB | `backgrounds/grid-motion.md` | gsap | An animated grid of tiles that shift, scale, and rearrange with smooth motion... |
| GridScan | RB | `backgrounds/grid-scan.md` | none | A grid pattern background with a scanning line that sweeps across it, creatin... |
| Hyperspeed | RB | `backgrounds/hyperspeed.md` | three.js | A star-field warp speed effect. Particles streak toward the camera creating a... |
| Iridescence | RB | `backgrounds/iridescence.md` | none | A holographic, iridescent surface effect that shifts colors based on mouse po... |
| LetterGlitch | RB | `backgrounds/letter-glitch.md` | none | A background filled with randomly glitching characters that shift and change.... |
| LightPillar | RB | `backgrounds/light-pillar.md` | none | A vertical light pillar/beam that rises from the bottom of the section, creat... |
| LightRays | RB | `backgrounds/light-rays.md` | none | Radiating light rays emanating from a focal point, creating a sunburst or div... |
| Lightning | RB | `backgrounds/lightning.md` | none | Animated lightning bolts that arc across a dark background. Electric, high-en... |
| LineWaves | RB | `backgrounds/line-waves.md` | none | Animated wavy lines flowing across the background in organic, undulating patt... |
| LiquidChrome | RB | `backgrounds/liquid-chrome.md` | none | A liquid metallic chrome flowing effect that creates a premium, hyper-realist... |
| LiquidEther | RB | `backgrounds/liquid-ether.md` | none | An ethereal liquid flowing ambient background with soft, dreamy color transit... |
| Orb | RB | `backgrounds/orb.md` | none | A glowing, blurred orb/sphere that serves as an ambient background element. T... |
| ParallaxGridScroll | AU | `backgrounds/parallax-grid-scroll.md` | framer-motion | 3D grid background with parallax depth effect on scroll, creating a receding ... |
| Particles | RB | `backgrounds/particles.md` | none | An animated particle field with floating dots that connect with lines when ne... |
| PixelBlast | RB | `backgrounds/pixel-blast.md` | none | An exploding pixel burst background effect where pixels scatter outward from ... |
| PixelSnow | RB | `backgrounds/pixel-snow.md` | none | Falling pixel-art snow particles that drift down the screen, creating a calm,... |
| Plasma | RB | `backgrounds/plasma.md` | none | An animated plasma/lava-lamp fluid effect with vibrant, shifting color blobs.... |
| Prism | RB | `backgrounds/prism.md` | none | A prismatic light refraction effect that splits light into a subtle rainbow s... |
| PrismaticBurst | RB | `backgrounds/prismatic-burst.md` | none | An intense burst of prismatic light rays radiating outward with spectral colo... |
| Radar | RB | `backgrounds/radar.md` | none | A rotating radar sweep scan animation with concentric rings and a sweeping be... |
| RetroGrid | MU | `backgrounds/retro-grid.md` | none | Perspective vanishing-point retro floor grid with a vaporwave/synthwave aesth... |
| Ribbons | RB | `backgrounds/ribbons.md` | none | Flowing 3D ribbon strands that weave across the screen with smooth, organic m... |
| RippleGrid | RB | `backgrounds/ripple-grid.md` | none | A grid pattern with ripple distortion waves that spread from cursor position ... |
| Ripple | RB | `backgrounds/ripple.md` | none | Concentric ripple rings that emanate from click or cursor position. Creates a... |
| ShapeBlur | RB | `backgrounds/shape-blur.md` | none | Large blurred gradient shapes (circles, blobs) floating and slowly drifting i... |
| ShapeGrid | RB | `backgrounds/shape-grid.md` | none | A grid of animated geometric shapes (circles, squares, triangles) that rotate... |
| ShootingStarsBackground | AU | `backgrounds/shooting-stars-background.md` | none | Animated shooting stars that streak across the background at random intervals... |
| Silk | RB | `backgrounds/silk.md` | none | A smooth, silky fabric flowing background that creates an elegant, luxurious ... |
| SoftAurora | RB | `backgrounds/soft-aurora.md` | none | A softer, subtler version of the aurora background with gentler color transit... |
| Squares | RB | `backgrounds/squares.md` | none | A subtle animated grid of squares that pulse, fade, or shift in opacity. The ... |
| Threads | RB | `backgrounds/threads.md` | none | Thin animated lines that weave and flow across the background like fabric thr... |
| VortexBackground | AU | `backgrounds/vortex-background.md` | none | Swirling vortex or spiral animated background with particles being drawn into... |
| WarpBackground | MU | `backgrounds/warp-background.md` | none | Warped, distorted flowing organic background with animated mesh-like gradients. |
| Waves | RB | `backgrounds/waves.md` | none | Animated SVG wave layers that flow across the bottom or top of a section. Mul... |

## Tier System

- **Tier 1 (Core):** Use on most builds. Bread-and-butter components.
- **Tier 2 (Situational):** Use when the design specifically calls for it.
- **Tier 3 (Showcase):** Reserved for hero builds where maximum visual impact is the goal.

## Standard Build Recipes

### Recipe: Premium Hero Section
```
Aurora (background) + BlurText (headline) + AnimatedContent (subtext + CTA) + Magnet (CTA button)
```

### Recipe: Tech-Forward Hero
```
Particles (background) + SplitText (headline) + NumberTicker (inline stat) + ShimmerButton (CTA)
```

### Recipe: Immersive Hero
```
Galaxy (background) + ScrollFloat (headline) + GradualBlur (content reveal) + SplashCursor (cursor effect)
```

### Recipe: Luxury/Premium Hero
```
Silk (background) + BlurText (headline) + FluidGlass (content panel) + PulsatingButton (CTA)
```

### Recipe: Linear-Style Section Header
```
LampEffect (glow header) + TextAnimate (headline) + AnimatedContent (content below)
```

### Recipe: SaaS Product Showcase
```
MacbookScroll or ContainerScrollAnimation (device reveal) + AnimatedBeam (integrations) + NumberTicker (stats)
```

### Recipe: Feature Grid Section
```
AnimatedContent (section wrapper) + SpotlightCard or MagicCard (per card) + GradientText (card titles)
```

### Recipe: Premium Bento Layout
```
MagicBento (grid) + GlassSurface (panels) + CountUp (stats) + GradientText (labels)
```

### Recipe: Stats / Social Proof
```
Beams (background) + AnimatedContent (wrapper) + NumberTicker (per stat) + AvatarCircles (user proof)
```

### Recipe: Service Showcase
```
AnimatedContent (scroll reveal) + TiltedCard or 3DCardEffect (per service) + BlurText (section headline)
```

### Recipe: Premium Card Grid
```
FadeContent (reveal) + GlowCard or MagicCard (per card) + ShinyText (labels) + StarBorder (featured)
```

### Recipe: Interactive Portfolio
```
HeroParallax (hero) + Marquee (client logos) + CircularGallery (projects) + ImageTrail (hover detail)
```

### Recipe: Glass Dashboard
```
SoftAurora (background) + FluidGlass (panels) + GlassIcons (nav) + PillNav (tabs) + NumberTicker (metrics)
```

### Recipe: Integrations / Partners Page
```
AnimatedBeam (connections) + OrbitingCircles (tech stack) + IconCloud (partner logos) + Globe (global reach)
```

### Recipe: Timeline / History Page
```
Timeline (main layout) + TracingBeam (scroll indicator) + AnimatedContent (entry reveals) + StickyScrollReveal (details)
```

### Recipe: Full-Page Single-Scroll Site
```
Aurora (hero bg) + BlurText (hero text) + FloatingNavbar (navigation) + AnimatedContent (all sections) + SpotlightCard (features) + TiltedCard (portfolio) + NumberTicker (stats) + ShimmerButton (CTAs)
```

## Lyfework Build Standards (Apply to All Components)

1. **Typography:** Manrope 800 for headlines, 700 for subheads, 400 for body
2. **Colors:** Brand gradient `#ff642a` to `#ff0301` for accents. Dark bg `#0a0a0a`.
3. **Glass effect:** `lyf-glass` class on cards and panels
4. **Border radius:** 12px cards, 8px buttons, 16px glass panels
5. **Animation timing:** 0.5-0.7s duration, ease-out. Never bouncy. Never slow.
6. **Mobile:** All components must degrade gracefully. Test hover states on touch.
7. **GHL compatibility:** Test canvas elements and IntersectionObserver inside GHL iframe.

## Skipped Components (Known Broken/Excluded)

- **ReactBits Buttons** (8) - All return placeholder code
- **ReactBits Forms** (3) - Incomplete implementations
- **ReactBits Loaders** (9) - Incomplete implementations
- **Aceternity Forms** (signup-form, gooey-input, file-upload) - Form components, build custom
- **Aceternity Loaders** - Incomplete
- **Aceternity Code Block** - Utility, not visual component
