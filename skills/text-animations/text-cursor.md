---
name: text-cursor
source: ReactBits
source_url: https://reactbits.dev/text-animations/text-cursor
category: text-animations
tags: text, cursor, caret, blinking, typing, terminal, input
dependencies: none
variants: both
license: MIT+Commons
tier: 2
added: 2026-03-25
---

# TextCursor

> Custom animated text cursor/caret that blinks alongside typed or static text, evoking a terminal, command-line, or live-typing aesthetic.

## When to Use

- Terminal or command-line themed hero sections for developer tools
- Typing animation endpoints where a blinking cursor signals completion
- Search input placeholders that simulate live typing with a custom caret
- Code snippet displays or CLI instruction blocks
- SaaS product demos showing text being "entered" in real time

## When NOT to Use

- Inside actual input fields where the native cursor is expected
- Warm, human, or organic brand tones where a terminal vibe clashes
- Multiple blinking cursors on the same page (visually noisy)
- Anywhere the blinking would compete with real interactive elements

## Pairs Well With

- `decrypted-text` - Decrypted text reveal followed by a blinking cursor at the end
- `blur-text` - BlurText entrance for the headline, TextCursor on a typed subtitle below
- `animated-content` - AnimatedContent wrapper with a terminal-style TextCursor message inside
- `gradient-text` - Gradient-colored typed text with a matching gradient cursor

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| text | string | "" | Text to display before the cursor |
| cursorChar | string | "\|" | Character used as the cursor |
| blinkSpeed | number | 530 | Blink interval in milliseconds |
| cursorColor | string | "white" | Color of the cursor character |
| typing | boolean | false | Whether to animate typing the text character by character |
| typingSpeed | number | 80 | Interval in ms between typed characters (when typing=true) |
| loop | boolean | false | Whether typing animation loops continuously |
| className | string | "" | Additional CSS classes for the text |

## Installation

```bash
npx shadcn@latest add @react-bits/TextCursor-TS-TW
```

## Usage Example

```jsx
import TextCursor from '@/components/ui/TextCursor';

function ClinicOSTerminalHero() {
  return (
    <section className="min-h-screen flex items-center justify-center bg-[#0a0a0a] px-6">
      <div className="max-w-2xl w-full">
        <div className="lyf-glass rounded-2xl p-8 border border-white/10">
          <div className="flex items-center gap-2 mb-6">
            <span className="w-3 h-3 rounded-full bg-red-500" />
            <span className="w-3 h-3 rounded-full bg-yellow-500" />
            <span className="w-3 h-3 rounded-full bg-green-500" />
          </div>
          <div className="font-mono text-sm text-gray-500 mb-2">
            $ clinicos deploy --production
          </div>
          <TextCursor
            text="Deploying your clinic automation..."
            cursorChar="|"
            blinkSpeed={500}
            cursorColor="#ff642a"
            typing={true}
            typingSpeed={60}
            loop={false}
            className="text-xl font-bold text-white"
            style={{ fontFamily: 'Manrope, sans-serif' }}
          />
          <div className="mt-4 text-sm text-green-400 font-mono">
            Ready in 2.3s
          </div>
        </div>
      </div>
    </section>
  );
}
```

## Lyfework Customization Notes

- Use `cursorColor="#ff642a"` to match the Lyfework brand gradient start color
- Manrope 700 for the typed text keeps it readable while the cursor blinks
- `blinkSpeed={500}` matches the standard terminal cadence; 300ms feels frantic, 800ms feels sluggish
- For typing mode, `typingSpeed={50-80}` simulates a fast, confident typist
- On #0a0a0a backgrounds inside a `lyf-glass` container, the terminal aesthetic feels premium
- For GHL: implement with CSS `@keyframes` for the blink and vanilla JS `setInterval` for typing

## Performance Notes

- Zero dependencies, cursor blink is a pure CSS `@keyframes` opacity toggle
- Typing animation uses a single `setInterval` cleared on completion or unmount
- No layout shift, cursor is inline and does not affect surrounding elements
- Blink animation runs on the compositor thread, zero main thread cost
- Total JS footprint is under 1kb for the typing logic
