---
name: expandable-screen
source: Cult UI
source_url: https://www.cult-ui.com/docs/components/expandable-screen
category: components
tags: expandable, fullscreen, overlay, modal, card, transition
dependencies: framer-motion
variants: both
license: MIT
tier: 2
added: 2026-03-26
---

# ExpandableScreen

> Full-screen expandable card overlay that transitions from inline card to immersive full-screen view.

## When to Use
- Project showcases that expand to full detail views
- Portfolio items transitioning from grid to full-screen
- Product feature deep-dives expanding from card previews
- Image galleries with expand-to-full interactions
- Case study cards expanding to full presentations

## When NOT to Use
- Standard modal dialogs (use a modal component)
- Pages where full-screen takeover disrupts navigation flow
- Mobile experiences where back-navigation becomes confusing
- Content that doesn't benefit from the inline-to-fullscreen transition

## Pairs Well With
- `tilted-card` - Tilted card that expands to full-screen on click
- `spotlight-card` - Spotlight preview cards that expand to immersive views
- `animated-content` - Content animating within the expanded screen
- `blur-text` - Text reveals within expanded full-screen overlay

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| trigger | ReactNode | - | Inline card/trigger element |
| children | ReactNode | - | Expanded full-screen content |
| open | boolean | false | Controlled open state |
| onOpenChange | (open: boolean) => void | - | Open state handler |
| duration | number | 0.5 | Transition duration in seconds |
| overlay | boolean | true | Show background overlay |
| className | string | '' | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://cult-ui.com/r/expandable-screen"
```

## Usage Example
```jsx
import { ExpandableScreen } from "@/components/ui/expandable-screen";

export function ProjectShowcase() {
  return (
    <div className="bg-[#0a0a0a] py-24 px-6">
      <div className="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-5xl mx-auto">
        <ExpandableScreen
          trigger={
            <div className="lyf-glass rounded-[12px] p-6 cursor-pointer hover:border-[#ff642a]/30 border border-white/10 transition-colors">
              <h3 className="font-manrope font-700 text-xl text-white">Clinic Redesign</h3>
              <p className="font-manrope font-400 text-white/60 mt-2">Full brand & web overhaul</p>
            </div>
          }
          duration={0.6}
        >
          <div className="bg-[#0a0a0a] min-h-screen p-12">
            <h1 className="font-manrope font-800 text-5xl text-white">Clinic Redesign</h1>
            <p className="font-manrope font-400 text-white/70 mt-6 max-w-2xl">
              Complete brand transformation including website, booking system, and patient portal...
            </p>
          </div>
        </ExpandableScreen>
      </div>
    </div>
  );
}
```

## Lyfework Customization Notes
- Trigger cards: lyf-glass, 12px radius, border-white/10 on #0a0a0a
- Hover state: border transitions to brand orange #ff642a/30
- Expanded view: full #0a0a0a background with Manrope 800 headings
- Close button: absolute top-right with white/40 hover white/80
- Not ideal for GHL pages due to full-screen overlay conflicts

## Performance Notes
- Framer Motion layoutId provides smooth FLIP animation
- Overlay uses CSS backdrop-filter for native blur
- Body scroll is locked during expansion (scroll restoration on close)
- Only expanded content is rendered when open
- Transition uses GPU-accelerated scale/opacity transforms
