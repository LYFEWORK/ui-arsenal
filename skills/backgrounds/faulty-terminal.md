---
name: faulty-terminal
source: ReactBits
source_url: https://reactbits.dev/backgrounds/faulty-terminal
category: backgrounds
tags: background, terminal, glitch, crt, retro, code, hacker
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# FaultyTerminal

> A glitchy CRT terminal screen effect with scan lines, flicker, and text corruption. Creates a hacker/retro-computing aesthetic for tech-forward pages.

## When to Use

- Dev tool or developer-focused SaaS landing pages
- Cybersecurity or hacker-themed product pages
- Creative 404 or error pages with personality
- Portfolio "skills" or "tech stack" sections for developers
- Retro-themed event or launch countdown pages

## When NOT to Use

- Professional client sites (medical, legal, finance)
- E-commerce pages where trust and clarity matter
- Content-heavy pages where the glitch effect hurts readability
- Accessibility-critical applications (flicker can trigger photosensitive users)

## Pairs Well With

- `blur-text` - Text revealing through the glitch static creates a dramatic entrance
- `split-text` - Character-by-character reveal feels like terminal output
- `gradient-text` - Green or amber gradient text reinforces the terminal aesthetic
- `count-up` - Counting numbers over a terminal background feels like a system boot sequence

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| scanLineOpacity | number | 0.3 | Opacity of CRT scan lines |
| flickerIntensity | number | 0.5 | How much the screen flickers (0-1) |
| glitchFrequency | number | 3 | Glitch events per second |
| textColor | string | "#00ff00" | Color of terminal text elements |
| backgroundColor | string | "#000000" | Terminal background color |
| showText | boolean | true | Whether to show scrolling terminal text |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/FaultyTerminal-TS-TW
```

## Usage Example

```jsx
import FaultyTerminal from '@/components/ui/FaultyTerminal';
import SplitText from '@/components/ui/SplitText';

function DevToolHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <FaultyTerminal
          scanLineOpacity={0.2}
          flickerIntensity={0.3}
          glitchFrequency={2}
          textColor="#ff642a"
          backgroundColor="#0a0a0a"
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <SplitText
          text="SYSTEM INITIALIZED"
          className="text-4xl md:text-6xl font-mono font-bold text-white"
          delay={50}
        />
        <p className="mt-6 text-lg text-[#ff642a] font-mono">
          &gt; Deploying infrastructure in 3... 2... 1...
        </p>
        <button className="mt-10 px-8 py-4 rounded-lg bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold font-[Manrope]">
          Launch Console
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework terminal: `textColor="#ff642a"` with `backgroundColor="#0a0a0a"` for brand alignment
- Keep `flickerIntensity` at 0.2-0.4 for style without causing eye strain
- Reduce `glitchFrequency` to 1-2 for a more controlled, premium feel
- The CRT scan lines work best with `scanLineOpacity` of 0.15-0.25 on dark backgrounds
- For GHL: the scan line effect can be replicated with a CSS `repeating-linear-gradient` overlay
- Always provide a `prefers-reduced-motion` fallback that disables flicker and glitch

## Performance Notes

- CSS-based scan lines and flicker have minimal performance impact
- The glitch effect uses occasional DOM manipulation which can cause repaints
- Keep `glitchFrequency` low (1-3) to minimize repaint overhead
- The scrolling text element can be disabled with `showText={false}` to reduce DOM nodes
- Test with screen readers as the visual noise should be aria-hidden
