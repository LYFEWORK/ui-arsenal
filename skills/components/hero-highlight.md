---
name: hero-highlight
source: Aceternity UI
source_url: https://ui.aceternity.com/components/hero-highlight
category: components
tags: hero, highlight, gradient, cursor, interactive, landing, header
dependencies: framer-motion
variants: both
license: Free for commercial use
tier: 1
added: 2026-03-25
---

# HeroHighlight

> Hero section with animated gradient highlight that follows the cursor, plus an inline text highlight component.

## When to Use
- Primary hero section on SaaS or agency landing pages
- Above-the-fold sections that need subtle interactivity
- Product launch announcements with emphasized key phrases
- Clinic website hero with cursor-responsive visual feedback
- Any full-width header section needing ambient motion

## When NOT to Use
- On pages with multiple competing cursor-tracking effects
- For secondary content sections that do not need hero treatment
- When the hero already uses heavy background effects like particles or aurora

## Pairs Well With
- `blur-text` - Animate hero headline text entrance
- `gradient-text` - Double emphasis on key words in the hero
- `animated-content` - Stagger hero content elements on load
- `dock` - Floating navigation dock below the hero

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | - | Hero content |
| className | string | - | Classes for the hero container |
| containerClassName | string | - | Classes for the outer wrapper |

## Installation
```bash
npx aceternity-ui@latest add hero-highlight
```

## Usage Example
```jsx
import { HeroHighlight, Highlight } from "@/components/ui/hero-highlight";

export function LandingHero() {
  return (
    <HeroHighlight containerClassName="bg-[#0a0a0a]">
      <div className="text-center max-w-4xl mx-auto px-6">
        <h1 className="font-[Manrope] font-800 text-5xl md:text-7xl text-white leading-tight">
          We Build Websites That{" "}
          <Highlight className="from-[#ff642a] to-[#ff0301]">
            Convert Patients
          </Highlight>
        </h1>
        <p className="font-[Manrope] font-400 text-neutral-400 text-xl mt-6 max-w-2xl mx-auto">
          AI-powered clinic websites with automated scheduling, HIPAA compliance, and GHL integration.
        </p>
        <button className="mt-10 bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-[Manrope] font-700 px-10 py-4 rounded-[8px] text-lg">
          Start Your Project
        </button>
      </div>
    </HeroHighlight>
  );
}
```

## Lyfework Customization Notes
- Set `containerClassName="bg-[#0a0a0a]"` for dark theme hero background
- Highlight gradient uses `from-[#ff642a] to-[#ff0301]` for brand consistency
- Manrope 800 at 5xl-7xl for hero headlines, 400 for subtext
- CTA button uses `rounded-[8px]` with gradient background
- Cursor gradient effect works well in standard pages; test visibility in GHL iframes

## Performance Notes
- Cursor tracking uses `onMouseMove` with throttled updates for smooth 60fps
- Gradient effect is a single radial gradient repositioned via CSS custom properties
- No canvas or WebGL; pure CSS gradient means minimal GPU overhead
- Mobile fallback renders a static gradient glow, no performance cost
- Single instance per page recommended; stacking hero highlights degrades experience
