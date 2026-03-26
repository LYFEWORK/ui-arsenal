---
name: scroll-progress
source: Magic UI
source_url: https://magicui.design/docs/components/scroll-progress
category: animations
tags: scroll, progress, bar, reading, indicator
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-25
---

# ScrollProgress

> Reading progress bar that fills based on scroll position, typically fixed at the top of the page.

## When to Use
- Blog posts and long-form article pages
- Documentation pages with extended content
- Case study or portfolio detail pages
- Any long-scroll page where reading progress helps orientation
- Landing pages with many sections to scroll through

## When NOT to Use
- Short pages where the progress bar fills too quickly
- App-like interfaces without a clear reading flow
- Pages with horizontal scroll or complex scroll patterns
- When a table of contents sidebar is already present

## Pairs Well With
- `animated-content` - Content sections revealed as progress advances
- `dock` - Navigation dock paired with scroll progress indicator
- `blur-text` - Section headings that blur-reveal on scroll
- `text-reveal` - Scroll-linked text reveal with progress indicator

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| className | string | "" | Additional CSS classes for the progress bar |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/scroll-progress"
```

## Usage Example
```jsx
import { ScrollProgress } from "@/components/magicui/scroll-progress";

export function CaseStudyPage() {
  return (
    <>
      <ScrollProgress className="fixed top-0 left-0 right-0 z-50 h-1 bg-gradient-to-r from-[#ff642a] to-[#ff0301]" />
      <main className="bg-[#0a0a0a]">
        <section className="py-24 max-w-3xl mx-auto">
          <h1 className="font-manrope font-800 text-4xl text-white mb-8">
            How{" "}
            <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
              Bright Smile Dental
            </span>{" "}
            cut no-shows by 45%
          </h1>
          <p className="font-manrope font-400 text-white/70 text-lg leading-relaxed">
            {/* Long-form case study content */}
            A detailed case study about implementing Lyfework's AI scheduling system...
          </p>
        </section>
      </main>
    </>
  );
}
```

## Lyfework Customization Notes
- Apply `bg-gradient-to-r from-[#ff642a] to-[#ff0301]` for brand gradient progress bar
- Set height to `h-1` (4px) for subtle presence or `h-0.5` (2px) for ultra-minimal
- Position `fixed top-0` with `z-50` to stay above all content
- Use on case study, blog, and documentation pages within the Lyfework ecosystem
- GHL compatible — Framer Motion scroll listener with standard DOM element

## Performance Notes
- Framer Motion `useScroll` hook — optimized scroll listener with throttling
- Progress bar uses `scaleX` transform — GPU composited, no layout recalculation
- Single DOM element with transform animation — negligible overhead
- No intersection observer overhead — reads scroll position directly
- Works with any scroll container, not just window scroll
