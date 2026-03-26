# Component Sources

Tracked list of all libraries and sources the UI Arsenal pulls from.

## Active Sources

### ReactBits
- **URL:** https://reactbits.dev
- **GitHub:** https://github.com/DavidHDev/react-bits
- **License:** MIT + Commons Clause (free for personal and commercial use)
- **Total Components:** 135+ (free library)
- **Components Extracted:** 142
- **Date Added:** 2026-03-25
- **Quality Rating:** High (35k+ GitHub stars, actively maintained)
- **Install Method:** `npx shadcn@latest add @react-bits/{ComponentName}-TS-TW`
- **Notes:** Four variants per component (JS-CSS, JS-TW, TS-CSS, TS-TW). Buttons (8), Forms (3), and Loaders (9) are excluded due to placeholder/incomplete code.

### Magic UI
- **URL:** https://magicui.design
- **GitHub:** https://github.com/magicuidesign/magicui
- **License:** MIT (free for personal and commercial use)
- **Total Components:** 70+ (free library)
- **Components Extracted:** 36
- **Date Added:** 2026-03-25
- **Quality Rating:** High (15k+ GitHub stars, actively maintained)
- **Install Method:** `npx shadcn@latest add "https://magicui.design/r/{component-name}"`
- **Notes:** Built on shadcn/ui patterns. Tailwind + Motion. Excellent for landing pages and marketing sites. Provides device mockups (Safari, iPhone), premium buttons (Shimmer, Rainbow, Pulsating), and unique components like AnimatedBeam, Globe, and NumberTicker.

**Key Unique Components:**
- AnimatedBeam, Globe, NumberTicker, OrbitingCircles, IconCloud
- Safari/iPhone device mockups, HeroVideoDialog
- ShimmerButton, PulsatingButton, RainbowButton, ShinyButton, RippleButton
- Terminal, FileTree, CodeComparison, DottedMap
- MagicCard, NeonGradientCard, Lens, Confetti

### Aceternity UI
- **URL:** https://ui.aceternity.com
- **GitHub:** https://github.com/aceternity/aceternity-ui
- **License:** Free for commercial use (free components)
- **Total Components:** 100+ (free tier)
- **Components Extracted:** 47
- **Date Added:** 2026-03-25
- **Quality Rating:** High (popular, widely used, Tailwind-native)
- **Install Method:** `npx aceternity-ui@latest add {component-name}`
- **Notes:** Premium animated components, many inspired by Linear/Stripe/Vercel design. Excellent for SaaS landing pages. Provides unique section-level components like LampEffect, StickyScrollReveal, HeroParallax, ContainerScrollAnimation, and MacbookScroll.

**Key Unique Components:**
- LampEffect, HeroParallax, HeroHighlight, MacbookScroll
- ContainerScrollAnimation, StickyScrollReveal, Timeline, TracingBeam
- 3DCardEffect, EvervaultCard, WobbleCard, DirectionAwareHover
- FloatingNavbar, Sidebar, AnimatedModal, AnimatedTestimonials
- SVGMaskEffect, CanvasRevealEffect, GoogleGeminiEffect
- WorldMap, BackgroundGradientAnimation

### Cult UI
- **URL:** https://www.cult-ui.com
- **GitHub:** https://github.com/nolly-studio/cult-ui
- **License:** MIT (free for personal and commercial use)
- **Total Components:** 67+ (free library)
- **Components Extracted:** 43
- **Date Added:** 2026-03-26
- **Quality Rating:** High (actively maintained, shadcn-compatible)
- **Install Method:** `npx shadcn@latest add "https://cult-ui.com/r/{name}"`
- **Notes:** Creative components crafted for design engineers. Excellent for marketing pages, guided experiences, and textured/neumorphic designs. Unique offerings include Dynamic Island, fractal grids, shader effects, expandable patterns, and textured surfaces.

**Key Unique Components:**
- DynamicIsland, Lightboard, ShaderLensBlur, FractalGrid
- ExpandableCard, ExpandableScreen, ShiftCard, DistortedGlass
- LogoCarousel, FeatureCarousel, TweetGrid, BgMediaHero
- Family Button/Drawer, DirectionAwareTabs, ToolbarExpandable
- HeroDithering, HeroLiquidMetal, HeroHeatmap, CosmicButton
- PixelHeading, PixelParagraph, TextGif, GradientHeading

### Luxe
- **URL:** https://www.luxeui.com
- **GitHub:** https://github.com/guhrodrrigues/luxe
- **License:** MIT (free for personal and commercial use)
- **Total Components:** 13 (v2.0, consolidated variant-based)
- **Components Extracted:** 12
- **Date Added:** 2026-03-26
- **Quality Rating:** High (elegant, polished, Radix-based)
- **Install Method:** `npx shadcn@latest add "https://www.luxeui.com/r/{name}"`
- **Notes:** Focuses on elegant, sophisticated base components with beautiful animations. Built on Radix UI primitives. V2.0 consolidated 34+ components into variant-based architecture. Provides polished form elements (inputs, checkboxes, switches) that complement the visual components from other sources.

**Key Unique Components:**
- ButtonMagnetic, ButtonShine, ButtonRotateBorder
- MultiStepModal, AnimatedTabs, LuxeCard
- LuxeInput, LuxeCheckbox, LuxeSwitch, LuxeBadge

### Animate UI
- **URL:** https://animate-ui.com
- **GitHub:** https://github.com/Animate-UI/animate-ui
- **License:** MIT (free for personal and commercial use)
- **Total Components:** 50+ (growing, community-driven)
- **Components Extracted:** 21
- **Date Added:** 2026-03-26
- **Quality Rating:** High (shadcn CLI native, TypeScript, Motion)
- **Install Method:** `npx shadcn@latest add "https://animate-ui.com/r/{name}"`
- **Notes:** Fully animated component distribution built with React, TypeScript, Tailwind CSS, and Motion. Native shadcn CLI compatibility. Includes community-contributed components. Provides unique backgrounds (bubbles, fireworks, hexagons), radial navigation patterns, and animated utility components.

**Key Unique Components:**
- AvatarGroup, NotificationList, MotionCarousel
- LiquidButton, FlipButton, CopyButton, ShareButton
- BubbleBackground, FireworksBackground, HexagonBackground
- RadialMenu, RadialNav, RadialIntro, CursorFollow

## Prospective Sources (To Evaluate)

| Source | URL | Notes |
|--------|-----|-------|
| Framer Motion | https://motion.dev | Animation primitives, already used internally |
| shadcn/ui | https://ui.shadcn.com | Base component library, Tailwind + Radix |

## Rejected Sources

| Source | Reason |
|--------|--------|
| (none yet) | |

## Arsenal Summary

| Source | Components | License | Primary Strength |
|--------|-----------|---------|-----------------|
| ReactBits | 142 | MIT+Commons | Animations, backgrounds, cursor effects |
| Magic UI | 36 | MIT | Buttons, device mockups, landing page elements |
| Aceternity UI | 47 | Free commercial | Section-level effects, SaaS patterns, parallax |
| Cult UI | 43 | MIT | Marketing pages, textures, guided experiences |
| Luxe | 12 | MIT | Elegant form elements, polished base components |
| Animate UI | 21 | MIT | Radial navigation, backgrounds, community components |
| **Total** | **301** | | |
