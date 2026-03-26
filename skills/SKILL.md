---
name: ui-arsenal
description: >
  Lyfework UI Arsenal - 301 premium animated React components from
  ReactBits, Magic UI, Aceternity UI, Cult UI, Luxe, and Animate UI.
  Use this skill whenever building websites, landing pages, or web apps
  for Lyfework or Lyfework clients. Contains text animations, scroll reveals,
  interactive cards, animated backgrounds, cursor effects, navigation patterns,
  device mockups, buttons, and form elements. Always reference this skill
  before building UI to check if a pre-built premium component exists.
---

# Lyfework UI Arsenal

301 premium animated React components for building $30k+ websites.

## Sources

- **Aceternity UI**: 47 components
- **Animate UI**: 21 components
- **Cult UI**: 43 components
- **Luxe**: 12 components
- **Magic UI**: 36 components
- **ReactBits**: 142 components

Source badges: **RB** = ReactBits, **MU** = Magic UI, **AU** = Aceternity UI, **CU** = Cult UI, **LX** = Luxe, **AN** = Animate UI

## How to Use This Skill Library

1. **Identify what you're building** (hero section, feature grid, navigation, etc.)
2. **Check this index** for matching components
3. **Read the component's skill file** for props, usage examples, and pairing recommendations
4. **Implement using the documented code** with Lyfework customization notes applied
5. **Combine components** using the "Pairs Well With" recommendations

### When to Use Arsenal Components

- Hero sections (BlurText + Aurora/Particles/LampEffect)
- Scroll reveals (AnimatedContent, FadeContent, ScrollReveal, TracingBeam)
- Card grids (TiltedCard, SpotlightCard, MagicCard, 3DCardEffect, WobbleCard, ExpandableCard)
- Stats/metrics (CountUp, Counter, NumberTicker)
- Navigation (Dock, FloatingNavbar, Sidebar, SidePanel, RadialMenu, DynamicIsland)
- Cursor effects (BlobCursor, SplashCursor, FollowCursor, CursorFollow)
- Glass/premium surfaces (FluidGlass, GlassSurface, DistortedGlass)
- Galleries (CircularGallery, HeroParallax, FocusCards, MotionCarousel, 3DCarouselCult)
- Device mockups (Safari, iPhone, MacbookScroll, ContainerScrollAnimation)
- Buttons (ShimmerButton, PulsatingButton, RainbowButton, CosmicButton, LiquidButton, ButtonMagnetic)
- Video (HeroVideoDialog, BgMediaHero, VideoText)
- Maps/globes (Globe, DottedMap, WorldMap)
- Testimonials (AnimatedTestimonials, TweetGrid, LogoCarousel)
- Onboarding (Onboarding, IntroDisclosure, MultiStepModal)
- Notifications (NotificationList, DynamicIsland, StickyBanner)

## Component Index

### Text Animations (41)

| Component | Src | File | Deps | Best For |
|-----------|-----|------|------|----------|
| AsciiText | RB | `text-animations/ascii-text.md` | none | Renders text as ASCII art characters. Large block-letter text built from... |
| AuroraText | MU | `text-animations/aurora-text.md` | framer-motion | Text with an animated aurora/gradient color effect that smoothly shifts ... |
| BlurText | RB | `text-animations/blur-text.md` | framer-motion | Text that reveals itself by animating from blurred to sharp, word by wor... |
| CircularText | RB | `text-animations/circular-text.md` | none | Text arranged in a circle that rotates continuously. Characters are plac... |
| ColourfulText | AU | `text-animations/colourful-text.md` | framer-motion | Text with per-character rainbow color animation that cycles through vibr... |
| ComicText | MU | `text-animations/comic-text.md` | none | Bold comic/pop-art style text with exaggerated shadows and vibrant treat... |
| ContainerTextFlip | AU | `text-animations/container-text-flip.md` | framer-motion | Text that flips or rotates within a fixed container, cycling through mul... |
| CountUp | RB | `text-animations/count-up.md` | framer-motion | Animates a number from 0 to a target value with easing. Triggers on scro... |
| CurvedLoop | RB | `text-animations/curved-loop.md` | none | Text that curves along a circular or custom SVG path and loops continuou... |
| DecryptedText | RB | `text-animations/decrypted-text.md` | none | Text decryption reveal effect where characters scramble through random g... |
| FallingText | RB | `text-animations/falling-text.md` | none | Text characters that fall from their positions with gravity physics, the... |
| FuzzyText | RB | `text-animations/fuzzy-text.md` | none | Text rendered with fuzzy, blurred edges that sharpens into focus on hove... |
| GlitchText | RB | `text-animations/glitch-text.md` | none | Digital glitch and distortion effect on text using layered pseudo-elemen... |
| GradientText | RB | `text-animations/gradient-text.md` | none | Applies an animated gradient color sweep across text. The gradient shift... |
| LayoutTextFlip | AU | `text-animations/layout-text-flip.md` | framer-motion | Full layout text flip transition that animates the entire text block wit... |
| LineShadowText | MU | `text-animations/line-shadow-text.md` | none | Text with a cascading line shadow depth effect creating an elegant layer... |
| LuxeText | LX | `text-animations/luxe-text.md` | framer-motion | Elegant text component with animated gradient coloring and character-by-... |
| MorphingText | MU | `text-animations/morphing-text.md` | framer-motion | Text that smoothly morphs between different words or phrases with fluid ... |
| NumberTicker | MU | `text-animations/number-ticker.md` | framer-motion | Rolling digit counter animation that ticks up to a target number, perfec... |
| PixelHeading | CU | `text-animations/pixel-heading.md` | none | Pixel-art style heading with character-by-character animation from pixel... |
| PixelParagraph | CU | `text-animations/pixel-paragraph.md` | none | Pixel-dissolve paragraph text effect that assembles or dissolves body te... |
| RotatingText | RB | `text-animations/rotating-text.md` | framer-motion | A text element that cycles through multiple strings with animated transi... |
| ScrollFloat | RB | `text-animations/scroll-float.md` | gsap | Text characters that float up from below with individual parallax timing... |
| ScrollReveal | RB | `text-animations/scroll-reveal.md` | framer-motion | Text revealed progressively as the user scrolls, with each word or line ... |
| ScrollVelocity | RB | `text-animations/scroll-velocity.md` | framer-motion | Text that scrolls horizontally at a speed proportional to the user's scr... |
| ShinyText | RB | `text-animations/shiny-text.md` | none | A glossy shimmer sweep that passes across text on a loop. Like a light r... |
| Shuffle | RB | `text-animations/shuffle.md` | none | Text characters or words shuffle through random positions before settlin... |
| SparklesText | MU | `text-animations/sparkles-text.md` | none | Text with floating sparkle/glitter particles that twinkle around the cha... |
| SplitText | RB | `text-animations/split-text.md` | gsap, @gsap/react | Splits text into individual characters or words and animates each one wi... |
| TextAnimate | MU | `text-animations/text-animate.md` | framer-motion | Character-by-character or word-by-word entrance animation wrapper for te... |
| TextCursor | RB | `text-animations/text-cursor.md` | none | Custom animated text cursor/caret that blinks alongside typed or static ... |
| TextGif | CU | `text-animations/text-gif.md` | none | Text filled with an animated GIF as a clipping mask, creating motion-fil... |
| TextHighlighter | MU | `text-animations/text-highlighter.md` | none | Text with an animated highlight/marker underline effect that draws acros... |
| TextHoverEffect | AU | `text-animations/text-hover-effect.md` | none | SVG-based text with a mask/reveal effect on hover, creating a gradient o... |
| TextPressure | RB | `text-animations/text-pressure.md` | none | Text that deforms and squeezes under cursor pressure. Characters compres... |
| TextReveal | MU | `text-animations/text-reveal.md` | framer-motion | Text revealed progressively by scroll position, where each word highligh... |
| TextScramble | RB | `text-animations/text-scramble.md` | none | Text that decodes from random characters into the final message. Charact... |
| TrueFocus | RB | `text-animations/true-focus.md` | framer-motion | A text component where a focus border moves from word to word, highlight... |
| TypingAnimation | RB | `text-animations/typing-animation.md` | none | Classic typewriter effect. Text appears character by character with a bl... |
| VariableProximity | RB | `text-animations/variable-proximity.md` | none | Text that changes font weight, size, or style based on cursor proximity.... |
| VideoText | MU | `text-animations/video-text.md` | none | Text filled with video content using the text as a clipping mask, creati... |

### Animations & Effects (44)

| Component | Src | File | Deps | Best For |
|-----------|-----|------|------|----------|
| 3dMarquee | AU | `animations/3d-marquee.md` | framer-motion | 3D perspective scrolling marquee with depth effect, creating an infinite... |
| AnimatedBorder | RB | `animations/animated-border.md` | none | A gradient border that rotates around an element continuously. Different... |
| AnimatedContent | RB | `animations/animated-content.md` | framer-motion | A wrapper component that animates its children into view on scroll. The ... |
| Antigravity | RB | `animations/antigravity.md` | framer-motion | Elements float upward defying gravity on hover or scroll trigger, creati... |
| BlobCursor | RB | `animations/blob-cursor.md` | none | Replaces the cursor with a morphing organic blob that follows mouse move... |
| CanvasRevealEffect | AU | `animations/canvas-reveal-effect.md` | framer-motion | Canvas-based paint/brush reveal effect on hover, where dots or particles... |
| ClickSpark | RB | `animations/click-spark.md` | none | Emits a burst of sparks from the click point on any element. A subtle mi... |
| Confetti | MU | `animations/confetti.md` | canvas-confetti | Celebration confetti burst effect triggered by user actions like form su... |
| Crosshair | RB | `animations/crosshair.md` | none | Adds a crosshair overlay that follows the cursor. Horizontal and vertica... |
| Cubes | RB | `animations/cubes.md` | none | A 3D rotating cube animation built with pure CSS transforms, ideal for l... |
| CursorFollow | AN | `animations/cursor-follow.md` | framer-motion | Custom animated cursor element that follows the mouse pointer with sprin... |
| ElectricBorder | RB | `animations/electric-border.md` | none | An animated crackling electric border effect that wraps any element, per... |
| FadeContent | RB | `animations/fade-content.md` | framer-motion | Simple opacity fade-in on scroll. No slide, no transform, just clean opa... |
| FollowCursor | RB | `animations/follow-cursor.md` | none | An element (typically eyes, an icon, or a pointer) that tracks and follo... |
| GhostCursor | RB | `animations/ghost-cursor.md` | none | A ghostly cursor trail that follows the user's mouse with fading opacity... |
| GlareHover | RB | `animations/glare-hover.md` | none | A cursor-tracking glare/shine effect that sweeps across an element on ho... |
| GoogleGeminiEffect | AU | `animations/google-gemini-effect.md` | framer-motion | Google Gemini-style animated SVG beam hero with flowing, undulating line... |
| GradualBlur | RB | `animations/gradual-blur.md` | framer-motion | Content progressively blurs or unblurs as the user scrolls. Creates a de... |
| ImageTrail | RB | `animations/image-trail.md` | none | Images spawn and trail behind the cursor as it moves across a container.... |
| LaserFlow | RB | `animations/laser-flow.md` | none | An animated laser beam that flows along paths or borders of elements, cr... |
| LogoLoop | RB | `animations/logo-loop.md` | framer-motion | A continuous logo animation that cycles through client or partner logos ... |
| MagicRings | RB | `animations/magic-rings.md` | none | Concentric animated rings that expand and pulse outward from a center po... |
| MagnetLines | RB | `animations/magnet-lines.md` | none | Lines that dynamically attract toward or repel from the cursor like a ma... |
| Magnet | RB | `animations/magnet.md` | framer-motion | Makes an element magnetically attracted to the cursor on hover. The elem... |
| Marquee | RB | `animations/marquee.md` | none | Infinite horizontal scrolling content strip. Logos, testimonials, badges... |
| MetaBalls | RB | `animations/meta-balls.md` | none | Organic metaball blobs that merge and separate with smooth gooey transit... |
| MetallicPaint | RB | `animations/metallic-paint.md` | none | A metallic chrome paint shader effect that coats elements in a reflectiv... |
| MorphingBlob | RB | `animations/morphing-blob.md` | none | An SVG blob shape that continuously morphs between organic forms. Smooth... |
| Noise | RB | `animations/noise.md` | none | A film grain / noise texture overlay that adds analog warmth and depth t... |
| OrbitImages | RB | `animations/orbit-images.md` | framer-motion | Images orbiting around a central point in a 3D circular path, creating a... |
| OrbitingCircles | MU | `animations/orbiting-circles.md` | none | Icons or elements that orbit around a central point in smooth circular m... |
| PixelTrail | RB | `animations/pixel-trail.md` | none | A pixelated trail effect that follows cursor movement, rendering blocky ... |
| PixelTransition | RB | `animations/pixel-transition.md` | none | A full-screen pixel dissolve transition between two states. Content brea... |
| PointerHighlight | AU | `animations/pointer-highlight.md` | framer-motion | Cursor-following highlight or glow effect that tracks the mouse pointer ... |
| RadialIntro | AN | `animations/radial-intro.md` | framer-motion | Radial expanding intro/splash animation that reveals page content from a... |
| ScrollProgress | MU | `animations/scroll-progress.md` | framer-motion | Reading progress bar that fills based on scroll position, typically fixe... |
| ShaderLensBlur | CU | `animations/shader-lens-blur.md` | none | GPU shader-based lens blur effect with bokeh simulation and depth-of-fie... |
| SmoothScroll | RB | `animations/smooth-scroll.md` | none | Wraps the page in a smooth, momentum-based scroll container. Replaces na... |
| SplashCursor | RB | `animations/splash-cursor.md` | none | Replaces the default cursor with a fluid splash effect that trails behin... |
| StarBorder | RB | `animations/star-border.md` | none | An animated border with a glowing dot that travels around the element's ... |
| StickerPeel | RB | `animations/sticker-peel.md` | framer-motion | A sticker peel-off reveal animation that lifts a cover element like peel... |
| SvgMaskEffect | AU | `animations/svg-mask-effect.md` | framer-motion | SVG mask that reveals content underneath as the cursor moves, creating a... |
| TargetCursor | RB | `animations/target-cursor.md` | none | A target/crosshair scope overlay that follows the mouse cursor, replacin... |
| TracingBeam | AU | `animations/tracing-beam.md` | framer-motion | SVG beam that traces scroll progress along the side of content, creating... |

### Interactive Components (138)

| Component | Src | File | Deps | Best For |
|-----------|-----|------|------|----------|
| 3dAnimatedPin | AU | `components/3d-animated-pin.md` | framer-motion | 3D elevated pin popup that rises on hover, ideal for maps, location mark... |
| 3dCardEffect | AU | `components/3d-card-effect.md` | framer-motion | Perspective tilt card with elevated floating children that respond to mo... |
| 3dCarouselCult | CU | `components/3d-carousel-cult.md` | framer-motion | 3D perspective carousel with depth, rotation, and parallax effects for i... |
| Accordion | RB | `components/accordion.md` | framer-motion | Animated expandable/collapsible content sections. Smooth spring-based he... |
| AnimatedBeam | MU | `components/animated-beam.md` | framer-motion | Animated SVG light beam that visually connects two elements, ideal for i... |
| AnimatedList | RB | `components/animated-list.md` | framer-motion | A list component where items animate in sequentially with staggered entr... |
| AnimatedModal | AU | `components/animated-modal.md` | framer-motion | Spring-animated modal/dialog with smooth open/close transitions, backdro... |
| AnimatedTabs | LX | `components/animated-tabs.md` | framer-motion | Tabs component with a smooth animated indicator that slides between acti... |
| AnimatedTestimonials | AU | `components/animated-testimonials.md` | framer-motion | Auto-rotating testimonial carousel with smooth cross-fade animations, av... |
| AvatarCircles | MU | `components/avatar-circles.md` | none | Overlapping stacked avatar circles for displaying users, team members, o... |
| AvatarGroup | AN | `components/avatar-group.md` | framer-motion | Animated stacked avatar group that expands on hover to reveal individual... |
| BgAnimateButton | CU | `components/bg-animate-button.md` | none | Button with animated background gradient that shifts and flows on hover/... |
| BgMediaHero | CU | `components/bg-media-hero.md` | none | Full-bleed background media hero with video or image support and overlay... |
| BorderGlow | RB | `components/border-glow.md` | none | An animated glowing border effect for cards and containers. A luminous g... |
| BounceCards | RB | `components/bounce-cards.md` | framer-motion | Cards that bounce into view with spring physics animation. Each card ent... |
| ButtonMagnetic | LX | `components/button-magnetic.md` | framer-motion | Button that magnetically attracts toward the cursor on hover, creating a... |
| ButtonRotateBorder | LX | `components/button-rotate-border.md` | none | Button with a continuously rotating animated gradient border, creating a... |
| ButtonShine | LX | `components/button-shine.md` | none | Button with an animated light shine sweep that glides across on hover, c... |
| CardHoverEffect | AU | `components/card-hover-effect.md` | framer-motion | Card grid with gradient glow hover animation that highlights the active ... |
| CardNav | RB | `components/card-nav.md` | framer-motion | Card-based navigation with animated transitions between items. Each nav ... |
| CardSwap | RB | `components/card-swap.md` | framer-motion | Cards that swap and shuffle positions with smooth animation. Users can c... |
| Carousel | RB | `components/carousel.md` | framer-motion | A smooth, gesture-enabled carousel with momentum scrolling. Supports swi... |
| ChromaGrid | RB | `components/chroma-grid.md` | none | A chromatic, colorful animated grid layout where cells shift colors, rev... |
| CircularGallery | RB | `components/circular-gallery.md` | framer-motion | A 3D circular carousel gallery where images are arranged in a ring and r... |
| CodeComparison | MU | `components/code-comparison.md` | none | Side-by-side code diff comparison component for showcasing before/after ... |
| CometCard | AU | `components/comet-card.md` | none | Card with animated comet streak/trail effect along the border, creating ... |
| ComparisonSlider | RB | `components/comparison-slider.md` | none | A drag-to-reveal before/after image comparison. Two images overlaid with... |
| ContainerScrollAnimation | AU | `components/container-scroll-animation.md` | framer-motion | MacBook-style scroll reveal animation for product showcases, with a devi... |
| CopyButton | AN | `components/copy-button.md` | framer-motion | Button with animated copy-to-clipboard feedback that transitions between... |
| CosmicButton | CU | `components/cosmic-button.md` | none | Button with cosmic space particle animation, starfield effects, and nebu... |
| Counter | RB | `components/counter.md` | framer-motion | An animated increment/decrement counter with spring physics. Number chan... |
| Cover | AU | `components/cover.md` | framer-motion | Text or element wrapper with an animated beam reveal effect on hover, cr... |
| DecayCard | RB | `components/decay-card.md` | none | A card that distorts, warps, or "decays" on hover. The card image or con... |
| DirectionAwareHover | AU | `components/direction-aware-hover.md` | framer-motion | Card with an overlay that enters from the direction the cursor approache... |
| DirectionAwareTabs | CU | `components/direction-aware-tabs.md` | framer-motion | Tabs with direction-aware sliding indicator that tracks from the previou... |
| DistortedGlass | CU | `components/distorted-glass.md` | none | Distorted frosted glass effect panel with chromatic aberration and refra... |
| DomeGallery | RB | `components/dome-gallery.md` | three.js, @react-three/fiber, @react-three/drei | A dome-shaped 3D gallery layout rendered with WebGL. Images or cards are... |
| DottedMap | MU | `components/dotted-map.md` | none | Animated world map composed of dots with highlighted location pins for s... |
| DraggableCard | AU | `components/draggable-card.md` | framer-motion | Drag-to-move interactive card with spring physics, inertia, and boundary... |
| DynamicIsland | CU | `components/dynamic-island.md` | framer-motion | Apple Dynamic Island-inspired adaptive notification component that morph... |
| ElasticSlider | RB | `components/elastic-slider.md` | framer-motion | A slider/range input with elastic spring physics. The thumb stretches an... |
| EvervaultCard | AU | `components/evervault-card.md` | framer-motion | Card with encrypted matrix text effect that reveals readable content on ... |
| ExpandableCard | CU | `components/expandable-card.md` | framer-motion | Card that expands inline to reveal more content with smooth height anima... |
| ExpandableScreen | CU | `components/expandable-screen.md` | framer-motion | Full-screen expandable card overlay that transitions from inline card to... |
| FamilyButton | CU | `components/family-button.md` | framer-motion | Expandable button group that fans out additional action options on inter... |
| FamilyDrawer | CU | `components/family-drawer.md` | framer-motion | Bottom drawer with expandable sections and nested content groups. |
| FeatureCarousel | CU | `components/feature-carousel.md` | framer-motion | Animated feature showcase carousel with auto-play, drag, and keyboard na... |
| FileTree | MU | `components/file-tree.md` | none | Animated file explorer directory tree component for displaying project s... |
| FlipButton | AN | `components/flip-button.md` | framer-motion | Button that performs a 3D flip animation to reveal a confirmation state ... |
| FlipCard | RB | `components/flip-card.md` | none | A card that flips to reveal back content on hover or click. Full 3D CSS ... |
| FloatingPanel | CU | `components/floating-panel.md` | framer-motion | Floating draggable panel overlay for secondary content, tools, or contex... |
| FlowingMenu | RB | `components/flowing-menu.md` | framer-motion | A navigation menu with flowing, liquid-style hover transitions. When the... |
| FluidGlass | RB | `components/fluid-glass.md` | none | A fluid glassmorphism card/panel effect with dynamic blur that responds ... |
| FlyingPosters | RB | `components/flying-posters.md` | framer-motion | Posters and cards that fly in from different directions with 3D rotation... |
| FocusCards | AU | `components/focus-cards.md` | framer-motion | Cards that expand and come into focus when hovered, while dimming the re... |
| Folder | RB | `components/folder.md` | framer-motion | An animated folder UI component that opens and closes with a realistic p... |
| GithubStarsButton | AN | `components/github-stars-button.md` | none | GitHub star count button that displays a live repository star count with... |
| GithubStarsWheel | AN | `components/github-stars-wheel.md` | none | Animated wheel/odometer display showing GitHub star count with rolling d... |
| GlassIcons | RB | `components/glass-icons.md` | none | Glassmorphism-styled icon containers with frosted backgrounds, subtle bo... |
| GlassSurface | RB | `components/glass-surface.md` | none | A frosted glass surface panel/card with configurable blur, opacity, and ... |
| Globe | MU | `components/globe.md` | cobe | Interactive 3D rotating globe rendered on canvas, perfect for showcasing... |
| GlowCard | RB | `components/glow-card.md` | none | A card with a glowing animated border that pulses or shifts color. The g... |
| GooeyNav | RB | `components/gooey-nav.md` | none | A gooey, sticky liquid navigation where menu items blend and merge with ... |
| GradientButtonGroup | CU | `components/gradient-button-group.md` | none | Grouped buttons with a shared gradient that flows across the entire group. |
| HeroHighlight | AU | `components/hero-highlight.md` | framer-motion | Hero section with animated gradient highlight that follows the cursor, p... |
| HeroParallax | AU | `components/hero-parallax.md` | framer-motion | Full-page parallax image gallery hero with multi-row scrolling images th... |
| HeroVideoDialog | MU | `components/hero-video-dialog.md` | framer-motion | Video modal with an animated thumbnail trigger — click to expand into a ... |
| IconCloud | MU | `components/icon-cloud.md` | none | Floating cloud of tech/brand icons with interactive 3D rotation and hove... |
| ImagesBadge | AU | `components/images-badge.md` | none | Floating avatar or image badges scattered as decorative elements around ... |
| InteractiveHoverButton | MU | `components/interactive-hover-button.md` | none | Button with an animated fill effect on hover that slides in from the edg... |
| IntroDisclosure | CU | `components/intro-disclosure.md` | framer-motion | Progressive disclosure intro/tutorial pattern that reveals content in di... |
| Iphone | MU | `components/iphone.md` | none | iPhone device mockup frame for displaying app screenshots, mobile previe... |
| LampEffect | AU | `components/lamp-effect.md` | framer-motion | Linear-style glowing lamp accent for section headers, creating a dramati... |
| Lanyard | RB | `components/lanyard.md` | three.js, react-three-fiber | A 3D badge/card hanging from a lanyard string with physics-based swingin... |
| LayoutGrid | AU | `components/layout-grid.md` | framer-motion | Animated expanding grid layout where cards grow to reveal detailed conte... |
| Lens | MU | `components/lens.md` | framer-motion | Magnifying lens effect that follows the cursor on hover over images, rev... |
| Lightboard | CU | `components/lightboard.md` | none | Interactive LED lightboard text display with clickable pixels and scroll... |
| LinkPreview | AU | `components/link-preview.md` | framer-motion | Hover preview tooltip that shows a thumbnail or preview card of the link... |
| LiquidButton | AN | `components/liquid-button.md` | framer-motion | Button with a liquid/fluid morphing animation that makes the button shap... |
| LoadingCarousel | CU | `components/loading-carousel.md` | framer-motion | Animated loading state with rotating carousel content to keep users enga... |
| LogoCarousel | CU | `components/logo-carousel.md` | framer-motion | Animated logo carousel for client, partner, or integration showcase sect... |
| LuxeBadge | LX | `components/luxe-badge.md` | none | Animated badge component with smooth entrance animation and optional pul... |
| LuxeCard | LX | `components/luxe-card.md` | framer-motion | Elegant card component with animated hover glow effect, subtle lift tran... |
| LuxeCheckbox | LX | `components/luxe-checkbox.md` | framer-motion | Checkbox with a satisfying spring-animated checkmark that bounces into p... |
| LuxeInput | LX | `components/luxe-input.md` | none | Input field with a smoothly animated floating label and elegant focus ri... |
| LuxeSwitch | LX | `components/luxe-switch.md` | framer-motion | Toggle switch with satisfying spring physics animation and smooth thumb ... |
| LuxeTooltip | LX | `components/luxe-tooltip.md` | framer-motion | Tooltip with smooth spring-animated enter and exit transitions, supporti... |
| MacbookScroll | AU | `components/macbook-scroll.md` | framer-motion | MacBook lid-opening scroll animation that reveals a product screenshot o... |
| MagicBento | RB | `components/magic-bento.md` | framer-motion | An animated bento grid layout with interactive hover effects. Each cell ... |
| MagicCard | MU | `components/magic-card.md` | framer-motion | Card with a radial gradient that follows the cursor on hover, creating a... |
| ManagementBar | AN | `components/management-bar.md` | framer-motion | Animated action management toolbar that slides in when items are selecte... |
| Masonry | RB | `components/masonry.md` | framer-motion | An animated masonry/Pinterest-style grid layout that arranges items in c... |
| MinimalCard | CU | `components/minimal-card.md` | none | Clean minimal card with subtle hover effects, ideal for content grids an... |
| ModelViewer | RB | `components/model-viewer.md` | three.js, @react-three/fiber, @react-three/drei | A 3D model viewer component for displaying and interacting with GLTF/GLB... |
| MorphSurface | CU | `components/morph-surface.md` | framer-motion | Surface that morphs shape between states using smooth border-radius and ... |
| MotionCarousel | AN | `components/motion-carousel.md` | framer-motion | Physics-based carousel with momentum scrolling, snap points, and smooth ... |
| MultiStepModal | LX | `components/multi-step-modal.md` | framer-motion | Multi-step animated modal wizard with smooth slide transitions between s... |
| NeonGradientCard | MU | `components/neon-gradient-card.md` | none | Card with an animated neon gradient border glow that shifts colors conti... |
| NeumorphButton | CU | `components/neumorph-button.md` | none | Neumorphic soft-shadow button with pressed/unpressed states and tactile ... |
| NeumorphEyebrow | CU | `components/neumorph-eyebrow.md` | none | Neumorphic eyebrow badge/label with soft inset shadow for section headin... |
| NotificationList | AN | `components/notification-list.md` | framer-motion | Animated notification stack with smooth enter/exit transitions, supporti... |
| Onboarding | CU | `components/onboarding.md` | framer-motion | Multi-step onboarding flow with animated transitions, progress tracking,... |
| PillNav | RB | `components/pill-nav.md` | framer-motion | A pill-shaped sliding indicator navigation where a rounded highlight sli... |
| PinList | AN | `components/pin-list.md` | framer-motion | Pinnable list items with reorder animation, allowing users to pin import... |
| PixelCard | RB | `components/pixel-card.md` | none | A card that pixelates or dissolves into pixel fragments on hover. Create... |
| ProfileCard | RB | `components/profile-card.md` | framer-motion | An animated profile/team member card with hover effects that reveal addi... |
| PulsatingButton | MU | `components/pulsating-button.md` | none | Button with a continuous pulsing glow ring animation that draws attentio... |
| RainbowButton | MU | `components/rainbow-button.md` | none | Button with an animated rainbow gradient border that continuously shifts... |
| ReflectiveCard | RB | `components/reflective-card.md` | none | A card with a reflective, mirror-like surface effect that responds to mo... |
| RippleButton | MU | `components/ripple-button.md` | none | Button with a material-design-style ripple effect that emanates from the... |
| Safari | MU | `components/safari.md` | none | Safari browser device mockup frame for displaying web app screenshots in... |
| ScrollStack | RB | `components/scroll-stack.md` | framer-motion | Cards or sections that stack on top of each other as the user scrolls. E... |
| ShareButton | AN | `components/share-button.md` | framer-motion | Share button with animated social icon fan-out that reveals sharing opti... |
| ShiftCard | CU | `components/shift-card.md` | framer-motion | Card that shifts and reveals additional detail content on hover with smo... |
| ShimmerButton | MU | `components/shimmer-button.md` | none | Button with a sweeping shimmer/shine animation that glides across the su... |
| ShinyButton | MU | `components/shiny-button.md` | none | Button with a glossy animated shine effect that sweeps across on hover, ... |
| SpotlightCard | RB | `components/spotlight-card.md` | none | A card with a radial light effect that follows the mouse cursor. Creates... |
| Stack | RB | `components/stack.md` | framer-motion | A stacked element container with visual depth effect. Multiple cards or ... |
| StackedCards | RB | `components/stacked-cards.md` | framer-motion | Cards stacked on top of each other that can be swiped or clicked through... |
| StaggeredMenu | RB | `components/staggered-menu.md` | framer-motion | A menu where items enter with staggered animation, each appearing slight... |
| StatefulButton | AU | `components/stateful-button.md` | framer-motion | Button with animated loading, success, and error state transitions, prov... |
| StickyBanner | AU | `components/sticky-banner.md` | none | Sticky top announcement or notification banner that stays visible as the... |
| StickyScrollReveal | AU | `components/sticky-scroll-reveal.md` | framer-motion | Pinned content panel with a scrolling side panel that reveals different ... |
| Tabs | RB | `components/tabs.md` | framer-motion | Animated tab navigation with a sliding active indicator and smooth conte... |
| Terminal | MU | `components/terminal.md` | none | Animated terminal/CLI display with typing animation, perfect for showcas... |
| TextRevealCard | AU | `components/text-reveal-card.md` | framer-motion | Card where cursor movement reveals hidden text underneath, like wiping a... |
| TextureButton | CU | `components/texture-button.md` | none | Button with textured surface pattern for tactile visual depth and unique... |
| TextureCard | CU | `components/texture-card.md` | none | Card with textured background surface for tactile visual depth and mater... |
| TextureOverlay | CU | `components/texture-overlay.md` | none | Texture overlay effect for images, sections, or any container element. |
| TiltedCard | RB | `components/tilted-card.md` | framer-motion | A card that responds to mouse movement with a 3D tilt effect. Creates de... |
| Timeline | AU | `components/timeline.md` | framer-motion | Vertical timeline with sticky headers and an animated connecting beam th... |
| ToolbarExpandable | CU | `components/toolbar-expandable.md` | framer-motion | Expandable toolbar with animated items that collapse and expand to revea... |
| Tooltip | RB | `components/tooltip.md` | framer-motion | Animated tooltip that appears on hover with spring physics. Supports mul... |
| TweetCard | MU | `components/tweet-card.md` | none | Embedded tweet/X post card component for displaying social proof or test... |
| TweetGrid | CU | `components/tweet-grid.md` | none | Grid layout for embedding social proof tweets and testimonials with maso... |
| UserPresenceAvatar | AN | `components/user-presence-avatar.md` | framer-motion | Avatar component with animated online presence indicator showing real-ti... |
| WobbleCard | AU | `components/wobble-card.md` | framer-motion | Card with a playful wobble/tilt effect on hover, adding personality and ... |
| WorldMap | AU | `components/world-map.md` | none | World map visualization with animated dot connections between locations,... |

### Navigation (9)

| Component | Src | File | Deps | Best For |
|-----------|-----|------|------|----------|
| BubbleMenu | RB | `navigation/bubble-menu.md` | framer-motion | A floating circular menu that expands from a single button into radial o... |
| Dock | RB | `navigation/dock.md` | framer-motion | A macOS-style dock navigation bar with icon magnification on hover. Item... |
| FloatingNavbar | AU | `navigation/floating-navbar.md` | framer-motion | Navbar that shrinks and floats as the user scrolls down, transitioning f... |
| InfiniteMenu | RB | `navigation/infinite-menu.md` | framer-motion | A fullscreen menu with items arranged in a continuous scrolling loop. It... |
| RadialMenu | AN | `navigation/radial-menu.md` | framer-motion | Circular radial menu with animated expansion that fans out action items ... |
| RadialNav | AN | `navigation/radial-nav.md` | framer-motion | Radial navigation component with animated spoke layout, positioning navi... |
| SidePanel | CU | `navigation/side-panel.md` | framer-motion | Animated side panel for secondary content, navigation, or contextual inf... |
| Sidebar | AU | `navigation/sidebar.md` | framer-motion | Animated slide-out sidebar navigation panel with smooth open/close trans... |
| Stepper | RB | `navigation/stepper.md` | framer-motion | An animated step indicator showing progress through a multi-step process... |

### Backgrounds (69)

| Component | Src | File | Deps | Best For |
|-----------|-----|------|------|----------|
| Aurora | RB | `backgrounds/aurora.md` | none | An animated aurora borealis background effect with flowing, organic grad... |
| BackgroundBeamsWithCollision | AU | `backgrounds/background-beams-with-collision.md` | framer-motion | Animated light beams that travel across the screen and scatter on collis... |
| BackgroundGradientAnimation | AU | `backgrounds/background-gradient-animation.md` | none | Moving and morphing gradient background animation with multiple color bl... |
| BackgroundGradient | AU | `backgrounds/background-gradient.md` | none | Animated mesh gradient background with smooth color transitions, providi... |
| BackgroundLines | AU | `backgrounds/background-lines.md` | none | Minimal vertical lines background pattern that adds subtle texture and d... |
| BackgroundTexture | CU | `backgrounds/background-texture.md` | none | Customizable background texture patterns including noise, grain, dots, a... |
| Balatro | RB | `backgrounds/balatro.md` | none | A psychedelic warped stripe background inspired by the card game Balatro... |
| Ballpit | RB | `backgrounds/ballpit.md` | three.js, cannon-es | 3D physics-based ball pit with realistic collision. Balls bounce, stack,... |
| Beams | RB | `backgrounds/beams.md` | none | Animated light beams that sweep across a dark background. Creates a dram... |
| BubbleBackground | AN | `backgrounds/bubble-background.md` | none | Floating bubble particles creating a soft ambient background with organi... |
| CanvasFractalGrid | CU | `backgrounds/canvas-fractal-grid.md` | none | Canvas-rendered fractal grid animation with higher performance than DOM-... |
| ColorBends | RB | `backgrounds/color-bends.md` | none | Bent and curved color gradient bands that create smooth, flowing color t... |
| DarkVeil | RB | `backgrounds/dark-veil.md` | none | A dark translucent overlay/veil effect that dims and adds depth to any s... |
| Dither | RB | `backgrounds/dither.md` | none | A dithered gradient/pattern background that creates a retro pixel-art te... |
| DotGrid | RB | `backgrounds/dot-grid.md` | none | An animated dot grid pattern background that creates a clean, minimal ge... |
| DottedGlowBackground | AU | `backgrounds/dotted-glow-background.md` | none | Dotted pattern background with a radial glow accent, creating depth with... |
| EvilEye | RB | `backgrounds/evil-eye.md` | none | An animated eye/iris that follows the user's cursor, creating an unsettl... |
| FaultyTerminal | RB | `backgrounds/faulty-terminal.md` | none | A glitchy CRT terminal screen effect with scan lines, flicker, and text ... |
| FireworksBackground | AN | `backgrounds/fireworks-background.md` | none | Animated fireworks burst celebration background with colorful particle e... |
| FloatingLines | RB | `backgrounds/floating-lines.md` | none | Thin animated lines that drift lazily across the background, creating an... |
| FractalGrid | CU | `backgrounds/fractal-grid.md` | none | Animated fractal pattern grid background with recursive geometric subdiv... |
| Galaxy | RB | `backgrounds/galaxy.md` | ogl | An interactive star field with twinkling stars, glow effects, and mouse-... |
| GlowingStarsBackground | AU | `backgrounds/glowing-stars-background.md` | none | Night sky background with animated glowing stars that pulse and shimmer,... |
| GradientBlinds | RB | `backgrounds/gradient-blinds.md` | none | Venetian blind strips with gradient animation that open and close to rev... |
| Grainient | RB | `backgrounds/grainient.md` | none | A gradient background with a film grain/noise texture overlay, combining... |
| GravityStarsBackground | AN | `backgrounds/gravity-stars-background.md` | none | Star field background with gravity physics where stars are pulled toward... |
| GridDistortion | RB | `backgrounds/grid-distortion.md` | three.js | A flat grid that warps and distorts where the mouse hovers. Creates a fa... |
| GridMotion | RB | `backgrounds/grid-motion.md` | gsap | An animated grid of tiles that shift, scale, and rearrange with smooth m... |
| GridScan | RB | `backgrounds/grid-scan.md` | none | A grid pattern background with a scanning line that sweeps across it, cr... |
| HeroColorPanels | CU | `backgrounds/hero-color-panels.md` | none | Multi-panel color block hero background with animated panel transitions. |
| HeroDithering | CU | `backgrounds/hero-dithering.md` | none | Dithered gradient hero background with retro pixel pattern effect for te... |
| HeroHeatmap | CU | `backgrounds/hero-heatmap.md` | none | Interactive heatmap-style hero background that responds to mouse movemen... |
| HeroLiquidMetal | CU | `backgrounds/hero-liquid-metal.md` | none | Liquid metal flowing hero background effect with chrome-like reflections... |
| HeroStaticRadial | CU | `backgrounds/hero-static-radial.md` | none | Static radial gradient hero background with customizable center, colors,... |
| HexagonBackground | AN | `backgrounds/hexagon-background.md` | none | Animated hexagonal grid pattern background with hover illumination and s... |
| HoleBackground | AN | `backgrounds/hole-background.md` | none | Background with an expanding hole/portal reveal effect that opens from a... |
| Hyperspeed | RB | `backgrounds/hyperspeed.md` | three.js | A star-field warp speed effect. Particles streak toward the camera creat... |
| Iridescence | RB | `backgrounds/iridescence.md` | none | A holographic, iridescent surface effect that shifts colors based on mou... |
| LetterGlitch | RB | `backgrounds/letter-glitch.md` | none | A background filled with randomly glitching characters that shift and ch... |
| LightPillar | RB | `backgrounds/light-pillar.md` | none | A vertical light pillar/beam that rises from the bottom of the section, ... |
| LightRays | RB | `backgrounds/light-rays.md` | none | Radiating light rays emanating from a focal point, creating a sunburst o... |
| Lightning | RB | `backgrounds/lightning.md` | none | Animated lightning bolts that arc across a dark background. Electric, hi... |
| LineWaves | RB | `backgrounds/line-waves.md` | none | Animated wavy lines flowing across the background in organic, undulating... |
| LiquidChrome | RB | `backgrounds/liquid-chrome.md` | none | A liquid metallic chrome flowing effect that creates a premium, hyper-re... |
| LiquidEther | RB | `backgrounds/liquid-ether.md` | none | An ethereal liquid flowing ambient background with soft, dreamy color tr... |
| Orb | RB | `backgrounds/orb.md` | none | A glowing, blurred orb/sphere that serves as an ambient background eleme... |
| ParallaxGridScroll | AU | `backgrounds/parallax-grid-scroll.md` | framer-motion | 3D grid background with parallax depth effect on scroll, creating a rece... |
| Particles | RB | `backgrounds/particles.md` | none | An animated particle field with floating dots that connect with lines wh... |
| PixelBlast | RB | `backgrounds/pixel-blast.md` | none | An exploding pixel burst background effect where pixels scatter outward ... |
| PixelSnow | RB | `backgrounds/pixel-snow.md` | none | Falling pixel-art snow particles that drift down the screen, creating a ... |
| Plasma | RB | `backgrounds/plasma.md` | none | An animated plasma/lava-lamp fluid effect with vibrant, shifting color b... |
| Prism | RB | `backgrounds/prism.md` | none | A prismatic light refraction effect that splits light into a subtle rain... |
| PrismaticBurst | RB | `backgrounds/prismatic-burst.md` | none | An intense burst of prismatic light rays radiating outward with spectral... |
| Radar | RB | `backgrounds/radar.md` | none | A rotating radar sweep scan animation with concentric rings and a sweepi... |
| RetroGrid | MU | `backgrounds/retro-grid.md` | none | Perspective vanishing-point retro floor grid with a vaporwave/synthwave ... |
| Ribbons | RB | `backgrounds/ribbons.md` | none | Flowing 3D ribbon strands that weave across the screen with smooth, orga... |
| RippleGrid | RB | `backgrounds/ripple-grid.md` | none | A grid pattern with ripple distortion waves that spread from cursor posi... |
| Ripple | RB | `backgrounds/ripple.md` | none | Concentric ripple rings that emanate from click or cursor position. Crea... |
| ShapeBlur | RB | `backgrounds/shape-blur.md` | none | Large blurred gradient shapes (circles, blobs) floating and slowly drift... |
| ShapeGrid | RB | `backgrounds/shape-grid.md` | none | A grid of animated geometric shapes (circles, squares, triangles) that r... |
| ShootingStarsBackground | AU | `backgrounds/shooting-stars-background.md` | none | Animated shooting stars that streak across the background at random inte... |
| Silk | RB | `backgrounds/silk.md` | none | A smooth, silky fabric flowing background that creates an elegant, luxur... |
| SoftAurora | RB | `backgrounds/soft-aurora.md` | none | A softer, subtler version of the aurora background with gentler color tr... |
| Squares | RB | `backgrounds/squares.md` | none | A subtle animated grid of squares that pulse, fade, or shift in opacity.... |
| StripeBgGuides | CU | `backgrounds/stripe-bg-guides.md` | none | Stripe-style vertical guide lines background for clean, structured page ... |
| Threads | RB | `backgrounds/threads.md` | none | Thin animated lines that weave and flow across the background like fabri... |
| VortexBackground | AU | `backgrounds/vortex-background.md` | none | Swirling vortex or spiral animated background with particles being drawn... |
| WarpBackground | MU | `backgrounds/warp-background.md` | none | Warped, distorted flowing organic background with animated mesh-like gra... |
| Waves | RB | `backgrounds/waves.md` | none | Animated SVG wave layers that flow across the bottom or top of a section... |

## Tier System

- **Tier 1 (Core):** Use on most builds. Bread-and-butter components.
- **Tier 2 (Situational):** Use when the design specifically calls for it.
- **Tier 3 (Showcase):** Reserved for hero builds where maximum visual impact is the goal.

## Standard Build Recipes

### Premium Hero
```
Aurora + BlurText + AnimatedContent + ShimmerButton
```

### Tech-Forward Hero
```
Particles + SplitText + NumberTicker + PulsatingButton
```

### Linear-Style Section
```
LampEffect + TextAnimate + AnimatedContent
```

### SaaS Product Showcase
```
MacbookScroll + AnimatedBeam + NumberTicker + LogoCarousel
```

### Feature Grid
```
AnimatedContent + SpotlightCard/MagicCard + GradientText
```

### Premium Card Grid
```
FadeContent + ExpandableCard/ShiftCard + ShinyText + StarBorder
```

### Integrations Page
```
AnimatedBeam + OrbitingCircles + IconCloud + Globe
```

### Timeline / History
```
Timeline + TracingBeam + AnimatedContent + StickyScrollReveal
```

### Glass Dashboard
```
SoftAurora + FluidGlass/DistortedGlass + GlassIcons + DirectionAwareTabs + NumberTicker
```

### Full-Page Scroll Site
```
Aurora + BlurText + FloatingNavbar + AnimatedContent + SpotlightCard + TiltedCard + NumberTicker + ShimmerButton
```

### Onboarding Flow
```
Onboarding + MultiStepModal + AnimatedTabs + NotificationList + DynamicIsland
```

### Social Proof Section
```
Beams + AnimatedTestimonials + AvatarCircles/AvatarGroup + TweetGrid + LogoCarousel
```

## Lyfework Build Standards

1. **Typography:** Manrope 800 headlines, 700 subheads, 400 body
2. **Colors:** Gradient `#ff642a` → `#ff0301` for accents. Dark bg `#0a0a0a`.
3. **Glass:** `lyf-glass` class on cards and panels
4. **Radius:** 12px cards, 8px buttons, 16px glass panels
5. **Animation:** 0.5-0.7s duration, ease-out. Never bouncy. Never slow.
6. **Mobile:** All components must degrade gracefully. Test hover states on touch.
7. **GHL:** Test canvas/WebGL elements and IntersectionObserver in GHL iframe.

## Skipped Components

- **ReactBits Buttons** (8), **Forms** (3), **Loaders** (9) - Placeholder/incomplete code
- **Aceternity Forms** (signup-form, gooey-input, file-upload) - Build custom
- **Aceternity Loaders** - Incomplete
