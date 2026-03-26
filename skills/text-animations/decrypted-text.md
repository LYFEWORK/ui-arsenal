---
name: decrypted-text
source: ReactBits
source_url: https://reactbits.dev/text-animations/decrypted-text
category: text-animations
tags: text, decrypt, decode, reveal, cipher, scramble, tech
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# DecryptedText

> Text decryption reveal effect where characters scramble through random glyphs before resolving into the final message, evoking a cipher or hacking aesthetic.

## When to Use

- SaaS hero headlines that need a tech-forward first impression
- Dashboard welcome messages or status text that feels dynamic
- Feature reveal sections where each benefit "decodes" on scroll
- Loading states where text resolves as data arrives
- Any headline targeting a developer or tech-savvy audience

## When NOT to Use

- Clinic or wellness sites where the tone should be warm and human
- Body paragraphs or any text longer than a short headline
- Accessibility-critical content (screen readers cannot follow the scramble)
- Pages where multiple text animations already compete for attention

## Pairs Well With

- `animated-content` - Decrypt the headline, then AnimatedContent fades in the subtext
- `spotlight-card` - Decrypted stat numbers inside spotlight-lit metric cards
- `click-spark` - Spark effect on the CTA button below a decrypted headline
- `gradient-text` - Apply gradient color after decryption resolves for a polished finish

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Final resolved text to display |
| speed | number | 50 | Interval in ms between character swaps |
| characters | string | "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*()" | Character set used for scramble |
| trigger | "hover" \| "scroll" \| "load" | "load" | When to start the decryption animation |
| revealDirection | "start" \| "end" \| "center" \| "random" | "start" | Direction characters resolve from |
| className | string | "" | Additional CSS classes |
| onComplete | function | undefined | Callback fired when decryption finishes |

## Installation

```bash
npx shadcn@latest add @react-bits/DecryptedText-TS-TW
```

## Usage Example

```jsx
import DecryptedText from '@/components/ui/DecryptedText';

function SaaSHero() {
  return (
    <section className="min-h-screen flex flex-col items-center justify-center bg-[#0a0a0a] px-6">
      <DecryptedText
        text="Automate Everything."
        speed={40}
        revealDirection="start"
        trigger="load"
        className="text-5xl md:text-7xl font-extrabold text-white tracking-tight"
        style={{ fontFamily: 'Manrope, sans-serif' }}
      />
      <p className="mt-6 text-lg text-gray-400 font-normal max-w-xl text-center">
        ClinicOS runs your ops so you can focus on patients.
      </p>
      <button className="mt-8 px-8 py-3 rounded-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] text-white font-bold">
        Get Started
      </button>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use Manrope 800 for the decrypted headline to maximize visual weight
- Set `speed={40}` for a brisk, confident decode; `speed={80}` feels more dramatic but slower
- `revealDirection="start"` reads most naturally in English (left to right)
- On #0a0a0a backgrounds, use pure white text so the scramble characters are clearly visible
- For GHL pages: trigger on scroll-into-view rather than load to avoid animation playing off-screen
- Keep text under 5 words for maximum impact; long sentences dilute the effect

## Performance Notes

- Zero dependencies, uses `requestAnimationFrame` and basic DOM updates
- Minimal memory footprint, only manipulates a single text node
- No layout shift since the element dimensions are set from the final text
- Safe for mobile, animation completes in under 2 seconds by default
- No GPU layers needed, runs on the main thread without jank
