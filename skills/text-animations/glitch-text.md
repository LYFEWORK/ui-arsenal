---
name: glitch-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/glitch-text
category: text-animations
tags: text, glitch, distortion, digital, error, edgy, cyberpunk
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# GlitchText

> Digital glitch and distortion effect on text using layered pseudo-elements with color channel splitting and random clip-path slicing.

## When to Use

- Edgy or disruptive brand hero headlines (tech, gaming, creative agencies)
- Error state or 404 page text that leans into the "broken" aesthetic
- Hover effect on bold CTAs to convey energy and urgency
- Event or launch countdown text that feels high-energy
- Portfolio headers for developers, designers, or creative technologists

## When NOT to Use

- Healthcare, wellness, or clinic sites where trust and calm matter
- Body text or anything longer than a short headline
- Corporate or enterprise pages where professionalism is the priority
- Accessibility-sensitive contexts (the visual noise can trigger discomfort)

## Pairs Well With

- `click-spark` - Glitch headline with spark effects on the CTA button below
- `animated-content` - Glitch the title, then smoothly reveal the body content
- `particles` - Glitch text over a particle field for a full cyberpunk aesthetic
- `spotlight-card` - Glitch effect on card titles inside spotlight-lit containers

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text content to display with glitch effect |
| intensity | "low" \| "medium" \| "high" | "medium" | How aggressive the glitch distortion is |
| speed | number | 3 | Glitch cycle duration in seconds |
| trigger | "hover" \| "always" \| "scroll" | "always" | When the glitch effect is active |
| colors | [string, string] | ["#ff0000", "#0000ff"] | RGB split channel colors |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/GlitchText-TS-TW
```

## Usage Example

```jsx
import GlitchText from '@/components/ui/GlitchText';

function CreativeAgencyHero() {
  return (
    <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a] relative overflow-hidden">
      <div className="text-center z-10">
        <GlitchText
          text="BREAK THE MOLD"
          intensity="medium"
          speed={4}
          trigger="always"
          colors={["#ff642a", "#ff0301"]}
          className="text-6xl md:text-8xl font-extrabold text-white uppercase tracking-tight"
          style={{ fontFamily: 'Manrope, sans-serif' }}
        />
        <p className="mt-6 text-lg text-gray-400 font-normal max-w-lg mx-auto">
          We build brands that refuse to blend in.
        </p>
        <button className="mt-8 px-8 py-3 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
          Start Your Project
        </button>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use the Lyfework gradient colors (`#ff642a`, `#ff0301`) as the RGB split channels for on-brand glitching
- Manrope 800 uppercase with tight tracking creates the boldest glitch canvas
- Set `trigger="hover"` for subtlety on client sites; `trigger="always"` only for high-energy agency pages
- `intensity="low"` is usually sufficient for professional contexts; "high" is for pure creative expression
- On #0a0a0a backgrounds, the color channel split pops vividly against the dark
- For GHL: implement with pure CSS `@keyframes` and `clip-path` rather than JS to ensure iframe compatibility

## Performance Notes

- Pure CSS implementation using pseudo-elements `::before` and `::after`
- Keyframe animations run on the compositor thread, no main thread blocking
- Clip-path changes are GPU-accelerated in modern browsers
- No external dependencies, total footprint is just the CSS keyframes
- Disable on `prefers-reduced-motion` to respect accessibility preferences
