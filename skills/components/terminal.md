---
name: terminal
source: Magic UI
source_url: https://magicui.design/docs/components/terminal
category: components
tags: terminal, cli, code, typing, developer
dependencies: none
variants: both
license: MIT
tier: 2
added: 2026-03-25
---

# Terminal

> Animated terminal/CLI display with typing animation, perfect for showcasing commands or installation steps.

## When to Use
- "Quick start" installation sections on developer product pages
- CLI tool showcases with animated command output
- Technical documentation with interactive code examples
- Developer onboarding "getting started" sections
- AI product demos showing terminal/prompt interactions

## When NOT to Use
- Non-technical audiences who do not use terminals
- Long code blocks that are better served by a static code viewer
- Mobile-first pages where terminal UX feels alien
- When code-comparison component is more appropriate for diffs

## Pairs Well With
- `animated-content` - Scroll-reveal the terminal component
- `spotlight-card` - Terminal inside a spotlight-glow card
- `gradient-text` - "Get started in seconds" heading with gradient
- `blur-text` - Blur-reveal the section heading

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| children | ReactNode | required | Terminal content/lines |
| className | string | "" | Additional CSS classes |

## Installation
```bash
npx shadcn@latest add "https://magicui.design/r/terminal"
```

## Usage Example
```jsx
import { Terminal } from "@/components/magicui/terminal";

export function QuickStartSection() {
  return (
    <section className="bg-[#0a0a0a] py-24">
      <h2 className="text-center font-manrope font-800 text-3xl text-white mb-4">
        Up and running in{" "}
        <span className="bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          60 seconds
        </span>
      </h2>
      <p className="text-center font-manrope font-400 text-white/60 mb-12">
        Install the Lyfework SDK and start building.
      </p>
      <div className="mx-auto max-w-2xl">
        <Terminal className="rounded-[12px]">
          <span className="text-green-400">$</span> npx create-lyfework-app my-clinic
          <br />
          <span className="text-white/50">Creating project...</span>
          <br />
          <span className="text-green-400">$</span> cd my-clinic && npm run dev
          <br />
          <span className="text-white/50">Ready on http://localhost:3000</span>
        </Terminal>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes
- Terminal background should remain dark to blend with `#0a0a0a` page background
- Add `rounded-[12px]` for card styling consistency
- Use green accent for prompts (`text-green-400`) and white/50 for output
- Title bar dots can be customized with brand colors if desired
- GHL compatible — standard HTML pre/code rendering with CSS styling

## Performance Notes
- Typing animation uses CSS keyframes — no JavaScript interval loops
- Static content renders instantly, animation is decorative only
- No syntax highlighting overhead — text is manually styled
- Lightweight component — minimal DOM nodes
- Consider intersection observer to start typing animation only when visible
