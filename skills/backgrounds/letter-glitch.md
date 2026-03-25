---
name: letter-glitch
source: ReactBits
source_url: https://reactbits.dev/backgrounds/letter-glitch
category: backgrounds
tags: background, glitch, text, matrix, code, digital, hacker
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# LetterGlitch

> A background filled with randomly glitching characters that shift and change. Creates a digital rain / Matrix-style ambient effect. Characters flicker and swap continuously.

## When to Use

- Tech, AI, or cybersecurity brand hero backgrounds
- Developer tool or API product pages
- "Under construction" or maintenance pages
- Backgrounds for code/terminal-themed sections
- Any build targeting developer or hacker audiences

## When NOT to Use

- Warm, human, or organic brand aesthetics
- Client-facing business sites in non-tech verticals
- Behind important readable content (characters compete visually)
- Mobile-first designs (character grid gets too dense)

## Pairs Well With

- `text-scramble` - Scramble text over a glitching character background
- `split-text` - GSAP text reveal piercing through the glitch field
- `pixel-card` - Pixel cards over glitching characters
- `particles` - Choose one or the other, not both

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| glitchSpeed | number | 50 | Speed of character changes in ms |
| characters | string | "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789" | Character set |
| glitchColor | string | "rgba(255,100,42,0.3)" | Color of glitching characters |
| baseColor | string | "rgba(255,255,255,0.05)" | Color of static characters |
| fontSize | number | 16 | Character size in px |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/LetterGlitch-TS-TW
```

## Usage Example

```jsx
import LetterGlitch from '@/components/ui/LetterGlitch';

function DevHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden">
      <div className="absolute inset-0 z-0">
        <LetterGlitch glitchSpeed={60} glitchColor="rgba(255,100,42,0.2)" baseColor="rgba(255,255,255,0.03)" />
      </div>
      <div className="relative z-10 text-center">
        <h1 className="text-6xl font-extrabold text-white">Built by Engineers.</h1>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Glitch color: `rgba(255,100,42,0.15)` for Lyfework brand tint
- Base characters should be very low opacity (0.03-0.06) so they're atmospheric, not loud
- `glitchSpeed` of 40-80ms. Faster = more chaotic. Slower = more ambient.
- Great for Guildeon brand builds (developer tool aesthetic)
- Works in GHL (Canvas-based character rendering)

## Performance Notes

- Canvas-based text rendering
- Character updates are batched per frame
- Keep `glitchSpeed` above 30ms to avoid excessive redraws
- Reduce font size on mobile for better grid density
