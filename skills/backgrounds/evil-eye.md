---
name: evil-eye
source: ReactBits
source_url: https://reactbits.dev/backgrounds/evil-eye
category: backgrounds
tags: background, eye, iris, watching, cursor, interactive, dramatic
dependencies: none
variants: both
license: MIT+Commons
tier: 3
added: 2026-03-25
---

# EvilEye

> An animated eye/iris that follows the user's cursor, creating an unsettling "being watched" interactive background. A dramatic statement piece for creative and experimental pages.

## When to Use

- Creative portfolio hero sections where you want to make a bold impression
- Agency "about" pages to show personality and irreverence
- Halloween, horror, or themed event landing pages
- Interactive art installations or experimental web projects
- 404 pages or easter egg sections for memorable micro-interactions

## When NOT to Use

- Any client-facing professional site (medical, legal, finance)
- E-commerce or conversion-focused pages (distracts from CTA)
- Accessibility-critical pages (cursor tracking can be disorienting)
- Mobile-primary designs (no cursor to follow on touch devices)

## Pairs Well With

- `blur-text` - Text blurring in next to the watching eye creates an eerie hero
- `gradient-text` - Gradient text near the eye draws the viewer's attention to copy
- `animated-content` - Content appearing as if "revealed" by the watching eye
- `faulty-terminal` - Combine with terminal glitch for a full surveillance/hacker aesthetic

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| irisColor | string | "#ff0000" | Color of the iris |
| pupilColor | string | "#000000" | Color of the pupil |
| scleraColor | string | "#ffffff" | Color of the sclera (white of eye) |
| size | number | 200 | Diameter of the eye in pixels |
| followSpeed | number | 0.1 | How quickly the iris tracks the cursor (0-1) |
| blinkInterval | number | 5000 | Milliseconds between blinks (0 to disable) |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/EvilEye-TS-TW
```

## Usage Example

```jsx
import EvilEye from '@/components/ui/EvilEye';
import BlurText from '@/components/ui/BlurText';

function CreativeAboutHero() {
  return (
    <section className="relative min-h-screen flex items-center justify-center overflow-hidden bg-[#0a0a0a]">
      <div className="absolute inset-0 z-0 flex items-center justify-center">
        <EvilEye
          irisColor="#ff642a"
          pupilColor="#0a0a0a"
          scleraColor="#1a1a1a"
          size={300}
          followSpeed={0.08}
          blinkInterval={4000}
        />
      </div>

      <div className="relative z-10 text-center px-8">
        <BlurText
          text="We See Everything."
          delay={200}
          animateBy="words"
          className="text-5xl md:text-7xl font-extrabold text-white font-[Manrope]"
        />
        <p className="mt-6 text-lg text-gray-500 font-[Manrope]">
          Nothing escapes our attention to detail.
        </p>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Lyfework iris color: `#ff642a` with pupil `#0a0a0a` for brand alignment
- Keep `followSpeed` at 0.05-0.1 for smooth, unsettling tracking. Above 0.3 feels twitchy.
- `blinkInterval` of 3000-6000ms keeps it alive without being distracting
- Only use for Lyfework's own creative pages or portfolio showcases, never for client builds
- For GHL: not recommended. Cursor tracking requires JavaScript that GHL's custom code blocks handle poorly.
- On mobile, consider replacing with a static eye or removing entirely since there is no cursor

## Performance Notes

- Uses requestAnimationFrame for smooth cursor tracking
- Single canvas element, lightweight rendering
- The blink animation is CSS-driven, no extra JS cost
- Disable cursor tracking on mobile to save resources
- Consider `will-change: transform` on the iris element for GPU acceleration
