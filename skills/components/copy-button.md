---
name: copy-button
source: Animate UI
source_url: https://animate-ui.com/docs/components/components/copy-button
category: components
tags: copy, clipboard, button, feedback, animated, utility
dependencies: framer-motion
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# CopyButton

> Button with animated copy-to-clipboard feedback that transitions between copy and check icons with smooth motion.

## When to Use
- Code snippet blocks with a copy button for easy code sharing
- Referral or promo code displays where users copy codes
- API key or configuration string displays in dashboards
- Shareable link sections on portfolio or project pages
- Contact info (email, phone) cards with quick-copy functionality

## When NOT to Use
- Long-form content where "Select All + Copy" is more appropriate
- Buttons that perform actions beyond clipboard operations
- Mobile-only contexts where long-press copy is native
- Situations where the copied content needs user confirmation first

## Pairs Well With
- `luxe-card` - copy button in a code/config display card
- `luxe-tooltip` - tooltip showing "Copied!" confirmation alongside the icon animation
- `spotlight-card` - copy button on spotlight cards displaying sharable content
- `gradient-text` - gradient referral code text with copy button beside it

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| value | string | — | Text content to copy to clipboard |
| className | string | — | Additional CSS classes |
| duration | number | 2000 | Duration of "copied" state in ms |
| onCopy | () => void | — | Callback after successful copy |
| variant | "default" \| "outline" \| "ghost" | "ghost" | Button style variant |
| size | "sm" \| "md" \| "lg" | "md" | Button size preset |

## Installation
```bash
npx shadcn@latest add "https://animate-ui.com/r/copy-button"
```

## Usage Example
```jsx
import { CopyButton } from "@/components/ui/copy-button";

export function ReferralCode() {
  return (
    <div className="lyf-glass rounded-[12px] p-6 flex items-center justify-between bg-[#0a0a0a]/80">
      <div>
        <p className="font-manrope font-400 text-gray-400 text-sm">Your referral code</p>
        <p className="font-manrope font-800 text-xl bg-gradient-to-r from-[#ff642a] to-[#ff0301] bg-clip-text text-transparent">
          LYFE2026
        </p>
      </div>
      <CopyButton
        value="LYFE2026"
        className="text-[#ff642a] hover:text-[#ff0301] rounded-[8px]"
        duration={2500}
      />
    </div>
  );
}
```

## Lyfework Customization Notes
- Icon color: `text-[#ff642a]` for resting state, transitions to green check on copy
- Container should use `lyf-glass rounded-[12px]` for brand card styling
- Copyable text display: `font-manrope font-800` with brand gradient for emphasis
- GHL compatible — uses native Clipboard API, works in embedded contexts
- On `#0a0a0a` backgrounds, the icon contrast is clear without additional styling
- Consider adding toast notification alongside the icon animation for extra feedback

## Performance Notes
- Uses native Clipboard API — no polyfill needed for modern browsers
- Icon swap animation via framer-motion AnimatePresence — minimal overhead
- Auto-resets to copy state after duration — no manual state management needed
- Single DOM element with icon swap — no additional elements rendered
- Zero idle CPU usage — animation only triggers on click
