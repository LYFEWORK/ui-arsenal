---
name: accordion
source: ReactBits
source_url: https://reactbits.dev/components/accordion
category: components
tags: accordion, expand, collapse, FAQ, toggle, content
dependencies: framer-motion
variants: both
license: MIT+Commons
tier: 1
added: 2026-03-25
---

# Accordion

> Animated expandable/collapsible content sections. Smooth spring-based height animation when opening and closing. The standard FAQ and detail-reveal pattern done premium.

## When to Use

- FAQ sections on landing pages and service pages
- Feature detail reveals ("Click to learn more")
- Settings or configuration panels in web apps
- Process steps that expand to show details
- Any content that benefits from progressive disclosure

## When NOT to Use

- Content that should always be visible (don't hide critical info)
- Single items (accordion pattern implies multiple collapsible sections)
- Very short content where expansion feels unnecessary

## Pairs Well With

- `animated-content` - Scroll reveal the accordion section, then items expand on click
- `blur-text` - Section headline animates, accordion items appear below
- `spotlight-card` - Accordion inside a spotlight card for a premium FAQ panel
- `star-border` - Active/open accordion item gets an animated border

## Props / Configuration

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| items | AccordionItem[] | [] | Array of title/content pairs |
| allowMultiple | boolean | false | Allow multiple items open at once |
| defaultOpen | number | -1 | Index of item open by default |
| className | string | "" | Additional CSS classes |

## Installation

```bash
npx shadcn@latest add @react-bits/Accordion-TS-TW
```

## Usage Example

```jsx
import Accordion from '@/components/ui/Accordion';

function FAQSection() {
  const faqs = [
    { title: 'How long does the install take?', content: '30 days from signed agreement to fully live system.' },
    { title: 'Do I need to change my existing software?', content: 'No. Lyfework IO replaces or integrates with your current tools.' },
    { title: 'What happens after the install?', content: 'You choose: self-manage with the Software Plan ($297/mo) or we run everything with the Managed Plan ($997/mo).' },
  ];

  return (
    <section className="py-24 px-8 max-w-3xl mx-auto">
      <h2 className="text-3xl font-extrabold text-white text-center mb-12">Common Questions</h2>
      <Accordion items={faqs} allowMultiple={false} className="space-y-3" />
    </section>
  );
}
```

## Lyfework Customization Notes

- Item background: `lyf-glass` with `rounded-xl`
- Active item: add left border with Lyfework gradient or subtle glow
- Title text: Manrope 700, white. Content: Manrope 400, gray-400.
- `allowMultiple={false}` for FAQ sections. `true` for settings panels.
- The expand animation should use framer-motion spring, not CSS transitions (smoother)
- Works in GHL with React embeds

## Performance Notes

- framer-motion AnimatePresence for smooth height transitions
- Content is rendered but hidden (no lazy loading needed for text)
- Lightweight, no performance concerns
