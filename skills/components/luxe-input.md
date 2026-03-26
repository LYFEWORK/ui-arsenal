---
name: luxe-input
source: Luxe
source_url: https://www.luxeui.com/ui/luxe-input
category: components
tags: input, form, animated label, focus, text field
dependencies: none
variants: both
license: MIT
tier: 1
added: 2026-03-26
---

# LuxeInput

> Input field with a smoothly animated floating label and elegant focus ring transition.

## When to Use
- Contact forms on clinic or agency landing pages
- Lead capture forms embedded in GHL funnels
- Login and signup flows where polished inputs signal quality
- Multi-step modal forms (pairs with multi-step-modal)
- Any form where the floating label pattern improves clarity

## When NOT to Use
- Search bars where a placeholder-only pattern is more appropriate
- Inline editing fields in tables or spreadsheets
- Forms with very short labels that don't benefit from animation
- Contexts requiring native input behavior without custom styling

## Pairs Well With
- `multi-step-modal` - use luxe-input inside each modal step for polished form UX
- `shimmer-button` - pair with shimmer submit button for a premium form experience
- `luxe-checkbox` - consistent Luxe form family for checkboxes alongside inputs
- `blur-text` - blur-reveal the form heading while inputs are pristine

## Props / Configuration
| Prop | Type | Default | Description |
|------|------|---------|-------------|
| label | string | — | Floating label text |
| value | string | — | Controlled input value |
| onChange | (e: ChangeEvent) => void | — | Change handler |
| type | string | "text" | Input type (text, email, password, etc.) |
| className | string | — | Additional CSS classes |
| error | string | — | Error message to display |
| disabled | boolean | false | Disable the input |
| required | boolean | false | Mark as required |

## Installation
```bash
npx shadcn@latest add "https://www.luxeui.com/r/luxe-input"
```

## Usage Example
```jsx
import { LuxeInput } from "@/components/ui/luxe-input";

export function ClinicContactForm() {
  return (
    <form className="lyf-glass rounded-[12px] p-8 space-y-6 max-w-md mx-auto bg-[#0a0a0a]/80">
      <h2 className="font-manrope font-800 text-2xl text-white">Get in Touch</h2>
      <LuxeInput
        label="Full Name"
        type="text"
        required
        className="font-manrope font-400 text-white border-white/10 focus:border-[#ff642a]"
      />
      <LuxeInput
        label="Email Address"
        type="email"
        required
        className="font-manrope font-400 text-white border-white/10 focus:border-[#ff642a]"
      />
      <LuxeInput
        label="Phone Number"
        type="tel"
        className="font-manrope font-400 text-white border-white/10 focus:border-[#ff642a]"
      />
      <button className="w-full py-3 rounded-[8px] bg-gradient-to-r from-[#ff642a] to-[#ff0301] font-manrope font-700 text-white">
        Send Message
      </button>
    </form>
  );
}
```

## Lyfework Customization Notes
- Focus border color: `focus:border-[#ff642a]` for brand orange accent
- Floating label should use `font-manrope font-400` at rest, transitions up on focus
- Wrap forms in `lyf-glass rounded-[12px]` container for brand consistency
- Resting border: `border-white/10` on dark backgrounds
- GHL form integration — luxe-input maps to standard input elements, works with GHL form handlers
- Error state should use `text-[#ff0301]` for the error message

## Performance Notes
- Pure CSS transitions for label animation — no JavaScript overhead
- No dependencies — lightest possible animated input solution
- Label position calculated via CSS transform — no layout shifts
- Focus ring uses box-shadow transition — GPU-accelerated
- Works with React Hook Form and Formik out of the box
