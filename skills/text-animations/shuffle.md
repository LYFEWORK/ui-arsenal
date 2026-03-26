---
name: shuffle
source: ReactBits
source_url: https://reactbits.dev/text-animations/shuffle
category: text-animations
tags: text, shuffle, random, settle, playful, transition, reveal
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# Shuffle

> Text characters or words shuffle through random positions before settling into the correct order, creating a slot-machine or card-shuffle reveal.

## When to Use

- Stat counters or metric labels that shuffle in alongside animated numbers
- Tab or category switching where the new label shuffles into place
- Hover effects on navigation items or card titles for playful interaction
- Loading or transitional states where text changes dynamically
- Tagline rotators that shuffle between multiple messages

## When NOT to Use

- Long paragraphs or body copy (animation becomes disorienting)
- Accessibility-critical text where the shuffling creates confusion
- Multiple simultaneous shuffle animations on the same viewport
- Static content that does not change or respond to interaction

## Pairs Well With

- `animated-content` - Shuffle the headline text, AnimatedContent reveals the section body
- `click-spark` - Shuffle text on a button hover paired with spark on click
- `spotlight-card` - Shuffling stat labels inside spotlight-lit metric cards
- `split-text` - SplitText for the main headline, Shuffle for a rotating subtitle below

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Final text to display after shuffle completes |
| shuffleBy | "characters" \| "words" | "characters" | Whether to shuffle individual characters or whole words |
| speed | number | 30 | Interval in ms between shuffle frames |
| iterations | number | 10 | Number of shuffle cycles before settling |
| trigger | "hover" \| "scroll" \| "load" | "load" | When to trigger the shuffle animation |
| sequential | boolean | false | Whether characters settle left-to-right or all at once |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Shuffle-TS-TW
```

## Usage Example

```jsx
import Shuffle from '@/components/ui/Shuffle';

function ClinicDashboardHeader() {
  return (
    <header className="px-8 py-6 bg-[#0a0a0a] border-b border-white/10">
      <div className="flex items-center justify-between">
        <div>
          <Shuffle
            text="Good morning, Dr. Reyes"
            shuffleBy="characters"
            speed={25}
            iterations={8}
            trigger="load"
            sequential={true}
            className="text-2xl font-extrabold text-white"
            style={{ fontFamily: 'Manrope, sans-serif' }}
          />
          <p className="mt-1 text-sm text-gray-500 font-normal">
            You have 14 appointments today
          </p>
        </div>
        <div className="lyf-glass rounded-xl px-4 py-2">
          <Shuffle
            text="Revenue: $12,450"
            shuffleBy="characters"
            speed={20}
            iterations={12}
            trigger="scroll"
            sequential={true}
            className="text-lg font-bold bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent"
          />
        </div>
      </div>
    </header>
  );
}
```

## Lyfework Customization Notes

- Use Manrope 700/800 for shuffled text so each character frame is legible during the animation
- `sequential={true}` with `speed={25}` gives a satisfying left-to-right typewriter-shuffle feel
- For stat labels, use `shuffleBy="characters"` so numbers visually tumble into place
- Apply the Lyfework gradient (`from-[#ff642a] to-[#ff0301]`) to settled text using `bg-clip-text`
- On #0a0a0a backgrounds, white shuffle characters against dark create strong contrast
- For GHL: use a simple interval-based vanilla JS version since the effect is purely cosmetic

## Performance Notes

- Zero dependencies, uses `setInterval` with `requestAnimationFrame` for smooth updates
- Only updates `textContent` on a single DOM node, no re-renders or layout recalculations
- Cleans up intervals on unmount to prevent memory leaks
- Total animation duration is `speed * iterations` ms, keep under 1 second for snappy results
- No GPU layers needed, main thread cost is negligible for single elements
