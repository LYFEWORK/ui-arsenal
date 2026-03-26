---
name: radial-intro
source: Animate UI
source_url: https://animate-ui.com/docs/components/animations/radial-intro
category: animations
tags: radial, intro, splash, reveal, expanding, entrance
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# RadialIntro

> Radial expanding intro/splash animation that reveals page content from a center point outward in a circular expansion.

## When to Use
- Page load splash screens for premium brand landing pages
- Section entrance animations triggered by scroll-into-view
- App launch screens with branded reveal animation
- Portfolio project page transitions with radial wipe
- Event or launch countdown pages with dramatic reveal at zero

## When NOT to Use
- Content that needs to be immediately visible for SEO crawlers
- Pages with fast return visitors who don't want repeated intros
- Mobile contexts where splash animations delay content access
- Sites requiring sub-second time-to-interactive metrics
- Multi-page apps where repeated intro animations are annoying

## Pairs Well With
- `hole-background` - radial intro followed by hole-background reveal for layered drama
- `gradient-text` - text appears after radial intro completes for staged reveal
- `aurora` - aurora background revealed through the radial expansion
- `blur-text` - text blur-reveals after the radial intro finishes

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| duration | number | 1.2 | Total animation duration in seconds |
| delay | number | 0 | Delay before animation starts |
| color | string | "#0a0a0a" | Overlay color that expands/reveals |
| origin | { x: string; y: string } | { x: "50%", y: "50%" } | Radial expansion center point |
| className | string | — | Container CSS classes |
| onComplete | () => void | — | Callback when animation finishes |
| easing | string | "easeInOut" | Animation easing curve |
| children | ReactNode | — | Content to reveal |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/radial-intro"
```

## Usage Example
```jsx
import { RadialIntro } from "@/components/ui/radial-intro";

export function BrandedLanding() {
  return (
    <RadialIntro
      duration={1.5}
      delay={0.3}
      color="#0a0a0a"
      easing="easeInOut"
      onComplete={() => console.log("Intro complete")}
    >
      <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a]">
        <div className="text-center space-y-8">
          <div className="w-16 h-16 mx-auto rounded-full bg-gradient-to-r from-[#ff642a] to-[#ff0301]" />
          <h1 className="font-manrope font-800 text-6xl text-white">
            Lyfework
          </h1>
          <p className="font-manrope font-400 text-gray-400 text-xl">
            Practice Growth, Automated
          </p>
          <button className="px-8 py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white">
            Get Started
          </button>
        </div>
      </section>
    </RadialIntro>
  );
}
```

## Lyfework Customization Notes
- Overlay color: `"#0a0a0a"` matching the dark background for seamless reveal
- Set `delay={0.3}` to allow fonts and images to load before revealing
- Brand logo can be the origin point — set `origin` to logo's position
- Use `onComplete` to trigger subsequent animations (text reveals, button entrances)
- GHL compatible — CSS clip-path animation, no DOM conflicts
- Consider sessionStorage check to skip intro on return visits

## Performance Notes
- CSS clip-path circle animation — GPU-accelerated, 60fps
- Single overlay element — removed from DOM after animation completes
- No content re-render — children are mounted immediately, just visually hidden
- Animation runs once — no continuous computation
- Framer-motion handles the interpolation with configurable easing
